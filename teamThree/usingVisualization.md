---
layout: default
title: How to use sparkl_visualizer? 
parent: 'Data Vizualization'
nav_order: 4
---
# How to use sparkl_visualizer? 

## Usage

1. Write all your visualization elements down in the html file using the shape below.

    ```html
    <div data-visualization="__VISUALIZATION-TYPE__">
        <script type="text/plain" data-content="Query">
            __SPARQL-QUERY__
        </script>
    </div>
    ```

    - `__SPARQL-QUERY__` = A valid sparql query, validate your queries [here](https://query.wikidata.org).
    - `__VISUALIZATION-TYPE__` = Type of the graphic or tabular visualization (e.g. `'BubbleChart'`)

2. Include the `sparql-visualizer.js` at the end of your body.

    ```html
    <script src="PATH_TO_THE_SPARQL_VISUALIZER_JS_FILE" type="text/javascript"></script>
    <script>
        // Use the library here below the import
    </script>
    ```

3. Construct a serializer object, configure it as you like and call `serialize`.

    ```js
    const { Serializer } = SparqlVisualizer;
    const serializer = new Serializer();

    // bellow is an example with the standard endpoint configuration
    serializer.withEndpoint({ httpProtocol: 'https', host: 'wikidata.org' });

    await serializer.serialize();
    ```

    **or in one go**

    ```js
    const { Serializer } = SparqlVisualizer;

    await new Serializer()
        .withEndpoint({
            httpProtocol: 'https',
            host: 'wikidata.org'
        })
        .serialize();
    ```


## Example 1: iFrame Visualization:

```javascript
<div class="visualisation-wrapper" data-visualization="LineChart">
                <script type="text/plain" data-content="Configuration">
                    SELECT ?year (COUNT(?work) AS ?number_of_works) ?organization ?organizationLabel
                    WHERE {
                      {
                        SELECT DISTINCT ?year ?work ?organization WHERE {
                          hint:Query hint:optimizer "None".
                          VALUES ?organization {   wd:Q1269766  wd:Q193196   }
                          ?author wdt:P108 | wdt:P463 | (wdt:P1416/wdt:P361*) ?organization .
                          ?work wdt:P50 ?author .
                          ?work wdt:P577 ?publication_date .
                          BIND(STR(YEAR(?publication_date)) AS ?year)
                        }
                        GROUP BY ?work ?year ?organization
                      }
                      SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
                    }
                    GROUP BY ?year ?organization ?organizationLabel
                    ORDER BY ?year
                </script>
            </div>
```

## Example 2: HTML Table Visualization:

```javascript
 <div class="" data-visualization="Table">
                <script type="application/json" data-content="Configuration">
                    SELECT ?year (COUNT(?work) AS ?number_of_works) ?organization ?organizationLabel
                    WHERE {
                      {
                        SELECT DISTINCT ?year ?work ?organization WHERE {
                          hint:Query hint:optimizer "None".
                          VALUES ?organization {   wd:Q1269766  wd:Q193196   }
                          ?author wdt:P108 | wdt:P463 | (wdt:P1416/wdt:P361*) ?organization .
                          ?work wdt:P50 ?author .
                          ?work wdt:P577 ?publication_date .
                          BIND(STR(YEAR(?publication_date)) AS ?year)
                        }
                        GROUP BY ?work ?year ?organization
                      }
                      SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
                    }
                    GROUP BY ?year ?organization ?organizationLabel
                    ORDER BY ?year
                    LIMIT 10
                </script>
            </div>
```

[View Dev Playground Code](https://github.com/code-openness/sparql-visualizer/tree/master/playground){: .btn .btn-green }