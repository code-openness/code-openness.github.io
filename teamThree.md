---
layout: default
title: 'Data Vizualization'
nav_order: 4
has_children: true
permalink: /teamThree
---
# Data Vizualisation
Our Goal for this software project was the visualization of a bibliographic dataset received from [PIK](https://www.pik-potsdam.de/pik-frontpage). It contained information on their research and publications over the past few years. 

Within the field of bibliographical data, Wikidata is one of the biggest freely accessible sources of infromation and inspired the creation of a multitude of vizualisation tools. One of the most prominent open source tools being [SCHOLIA](https://tools.wmflabs.org/scholia/). A tool offering a veriety of visualization possibilities and infrastructure in connection with Wikidata. Due to it's open source nature and functionalities it was our primary choice.

## Challanges:
It quickly became apparent that using Scholia was not directly possible when considering our dataset. Due to the need four a local input source Scholia needed to be adjusted, allowing for the dynamic changing of the endpoint. This led us onto the path of creating a standalone library module accomplishing this and also improving on the existing visualization tools by removing the need for hardcoded elements as much as possible. 

## Results:
The created module  now allows for the dynamic adjustment of the endpoint, as well as the dynamic visualization of: 
- HTML Table
- iFrame Graphs
- Manually defined

As such, all that is needed to generate a new graph is the necessary query. The query will then be normalized to achieve a standardized format, thus avoiding URL encoding problems. Consequently, even if the query is not perfectly formatted it will still generate the correct visualization. 

[View on GitHub](https://github.com/code-openness/sparql-visualizer){: .btn .btn-purple }
[Further Internal Project Documentation](https://github.com/code-openness/Documentation/wiki){: .btn .btn-purple }
