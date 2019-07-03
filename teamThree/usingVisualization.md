---
layout: default
title: How to use sparkl_visualizer? 
parent: 'Data Vizualization'
nav_order: 3
---
# How to use sparkl_visualizer? 

## iFrame Visualization:

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

## HTML Table Visualization:

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