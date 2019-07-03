---
layout: default
title: 'Scholia SPARQL Querries'
parent: Scholia Background
grand_parent: 'Data Vizualization'
nav_order: 2
---
# Using Scholia SPARQL Queries
**Date:** 11.05.2019

**Team:** Data Visualization

**Author:** [Katharina Müller](https://github.com/Lianm123)

***

## How Scholia accesses information from Wikidata:
**In general Wikidata contains many items, each item contains properties and each property contains statements, which are values. **


### Let's take a look at the Scholia page for [Jens Nielsen](https://tools.wmflabs.org/scholia/author/Q16733372):
Here we see that he has the Wikidata item id: Q16733372. 

#### Example 1: Venues
One possibility is to show the venue statistics for his works, as seen [here](https://w.wiki/4G2). As you can see, it shows a weighted account of venues, for example "Biotechnology and Bioengineering" or "Applied Microbiology".
If we follow Jens' Id to the [Wikidata page](https://www.wikidata.org/wiki/Q16733372) we see that he has information under properties, such as: 
* instance of (value is human)
* image (value is the image) 
* sex or gender (value is male) 

However, we can't find information about his works, thus no information about venues. To get those we have to do a SPRQL query. The code for it is:

```SPARQL 
#defaultView:BubbleChart
SELECT ?count ?venue (SAMPLE(?venue_label_) AS ?venue_label) 
WITH {
  SELECT (COUNT(?work) as ?count) ?venue WHERE {
    ?work wdt:P50 wd:Q16733372 .
    ?work wdt:P1433 ?venue .
  }
  GROUP BY ?venue
} AS %counts
WHERE {
  INCLUDE %counts
  ?venue rdfs:label ?long_venue_label FILTER(LANG(?long_venue_label) = 'en')
  OPTIONAL { ?venue wdt:P1813 ?short_name . }
  BIND(COALESCE(?short_name, ?long_venue_label) AS ?venue_label_)
}
GROUP BY ?venue ?count
ORDER BY DESC(?count) 
```

Here we see that it actually looks at items of the property "work". In the list of these, it searches for: "work has author Jens Nielsen" or "all work items with property P50(Author) equal to Q16733372(Jens Nielsen's Wikidata ID)". 

The second step is to then take one of these works and check for the statement wdt:P1433, which means "published in". 

As such, the found value in that statement is then saved as a venue and can later be counted. For example: "Biotechnology and Bioengineering" occurred 69 times in Prof. Nielsen's works. 

#### Example 2: Topics
looks at authors property/statement wdt:P101 (Arbeitsgebiet), "Themenkreis, auf dem eine Person oder Institution ihre Haupttätigkeit (Property:P106) entfaltet". As well as, the property wdt:P921 (Schlagwort), "zentrales Thema des Werks", in terms of the authors list of works. 
```SPARQL 
#defaultView:BubbleChart
SELECT ?score ?topic ?topicLabel
WITH {
  SELECT
    (SUM(?score_) AS ?score)
    ?topic
  WHERE {
    { 
      wd:Q16733372 wdt:P101 ?topic .
      BIND(20 AS ?score_)
    }
    UNION
    {
      SELECT (3 AS ?score_) ?topic WHERE {
        ?work wdt:P50 wd:Q16733372 ;
              wdt:P921 ?topic . 
      }
    }
    UNION
    {
      SELECT (1 AS ?score_) ?topic WHERE {
        ?work wdt:P50 wd:Q16733372 .
        ?citing_work wdt:P2860 ?work .
        ?citing_work wdt:P921 ?topic . 
      }
    }
  }
  GROUP BY ?topic
} AS %results 
WHERE {
  INCLUDE %results
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en,da,de,es,jp,no,ru,sv,zh". }
}
ORDER BY DESC(?score)
LIMIT 200
```


#### Example 3: Themes
looks at work items for given author and searches for the statement/property wdt:P921, which means Schlagwort. Meaning: "das zentrale Thema des Werks". 
```SPARQL 
#defaultView:Table
SELECT ?count ?theme ?themeLabel ?example_work ?example_workLabel
WITH {
  SELECT (COUNT(?work) AS ?count) ?theme (SAMPLE(?work) AS ?example_work)
  WHERE {
    ?work wdt:P50 wd:Q16733372 .
    ?work wdt:P921 ?theme .
  }
  GROUP BY ?theme
} AS %result
WHERE {
  INCLUDE %result
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en,da,de,es,fr,jp,nl,no,ru,sv,zh" . } 
}
ORDER BY DESC(?count) 
```

### Some important links are: 
* [How does Wikidata work?](https://www.wikidata.org/wiki/Wikidata:Introduction)
* [Wikidata Items](https://www.wikidata.org/wiki/Help:Items)
* [Wikidata Properties](https://www.wikidata.org/wiki/Help:Properties)
* [Wikidata Statements](https://www.wikidata.org/wiki/Help:Statements)

### Links to all Wikidata Proprties:
* [Special List of Properties](https://www.wikidata.org/wiki/Special:ListProperties)
* [List of All Properties](https://www.wikidata.org/wiki/Wikidata:Database_reports/List_of_properties/all)

### SPARQL Tutorial:
* [Wikidata SPARQL Introduction](https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial)
