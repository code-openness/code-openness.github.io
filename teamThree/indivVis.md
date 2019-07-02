---
layout: default
title: Change Graph Colors
parent: 'Team 3: Data Vizualization' 
nav_order: 6
---

**Date:** 20.05.2019

**Team:** Data Visualization

**Author:** [Viktoria Sorgalla](https://github.com/Tory94)

---

## Add an individual color
For adding a individual color in a graph, you could use `?rgb`. With the HTML color code, you could define your color.

### Some examples
source code from: https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples#Overall_causes_of_death_ranking

```SPARQL
#defaultView:Graph
SELECT ?char ?charLabel ?group ?groupLabel ("7FFF00" as ?rgb)
WHERE {
	?group wdt:P31 wd:Q14514600 ;  # group of fictional characters
          wdt:P1080 wd:Q931597.  # from Marvel universe
 ?char wdt:P463 ?group # member of group
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en".}
```

```SPARQL
#added before 2016-10
#defaultView:Graph
SELECT DISTINCT ?item ?itemLabel ?rgb ?link
WHERE
{
  VALUES ?toggle { true false }
  ?disease wdt:P699 ?doid;
           wdt:P279+ wd:Q18123741;
           wdt:P2176 ?drug.
  ?drug rdfs:label ?drugLabel.
		FILTER(LANG(?drugLabel) = "en").
  ?disease rdfs:label ?diseaseLabel.
		FILTER(LANG(?diseaseLabel) = "en").
  BIND(IF(?toggle,?disease,?drug) AS ?item).
  BIND(IF(?toggle,?diseaseLabel,?drugLabel) AS ?itemLabel).
  BIND(IF(?toggle,"FFA500","7FFF00") AS ?rgb).
  BIND(IF(?toggle,"",?disease) AS ?link).
}

``` 

### Some Colores
aqua	`00ffff`\
blue	`0000ff`\
chocolate `d2691e`\
cyan	 `00ffff`\
deeppink `ff1493`\
indigo	`4b0082 `\
black	`000000`\
white	`ffffff`


https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/Wikidata_Query_Help/Result_Views