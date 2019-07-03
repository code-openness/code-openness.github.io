---
layout: default
title: Scholia Background
parent: Data Vizualization
nav_order: 3
---
**Date:** 23.04.2019

**Team:** Data Visualization

**Author:** [Katharina Müller](https://github.com/Lianm123), [Abdullah Barhoum](https://github.com/AbdBarho), [Vitalij Krotov](https://github.com/vmk1vmk), [Viktoria Sorgalla](https://github.com/Tory94), [Celina Loeper](https://github.com/loepec), [Ulrike Bath](https://github.com/ulibath)

***

Scholia is a python package and webapp for interaction with scholarly information in Wikidata.

Internally, Scholia uses mainly Python as server-side programming language, based on Flask, a minimalistic Python server with its own templating engine. This engine is put to good use in Scholia, since it can take any parameter from the request URL, create a matching query, request the data from the Wikimedia Query Service and embed the results.

## Features

### Routing

These are the available routing options:

* `/` \
Main page, returns a list of available visualizations in Scholia

* `/<Q-Pattern>` \
Redirects to the page corresponding to the item identified by the Q-Pattern given in the request URL.
Scholia internally has a group of possible items such as: 'author', 'venue', 'organization' … (see upcoming items)
If the requested item is not in this group, a redirect to a 404 page will occur.

* `/<P-Pattern>` \
Same as above the Q-Pattern, but with properties instead of items.

* `/arxiv/<arxiv>` \
Takes an arxiv identifier and converts it to a Wikidata Item, then redirects to corresponding page.

* `/arxiv-to-quickstatements` \
Takes the arxiv identifier given as an URL query parameter and converts it to a Wikidata Q-identifier (for example: 1703.06103 → Q30005091).

* `/author` \
Redirects to a page with a list of example queries on authors.

* `/author/<Q-Pattern>` \
Redirect to a set of pre-defined visualizations for the author identified by the Q-Pattern.

* `/author/<Q-Pattern>/latest-works/rss` \
Returns an RSS feed of the author's latest work.

* `/author/<Q-Pattern>/missing` \
Redirects to a page containing any missing information about the author, such as missing citations, topics, ...

* `/author/random` \
Request a random author from the Wikimedia Query Service and visualizes the results.

* `/authors/<Q-Patterns>` \
The Q-Patterns are comma-separated, visualizes the works done in collaboration between the given authors.

* ...

### Types of data

In the list above we discussed possible queries on authors, however, Scholia also has almost identical structure for visualizing other types of data, including but not limited to:

* Work
* Venue
* Series
* Catalogue
* Organization
* Publisher
* Printer
* Sponser
* Location
* Country
* Event
* Event Series
* Clinical Trial
* Project
* Award
* Topics:
    * General
    * Disease
    * Taxon
    * Gene
    * Protein
    * Pathway
    * Chemical
    * Chemical Class
    * Use
* With some other tools to request and visualize data from other sources such as EU CORDIS, InChIkey, ISSN, MeSH, ORCID, PubMed, VIAF …

### Logical structure

All available visualizations in Scholia are pre-defined under `scholia/app/templates`, these are the bases which can be manipulated through the data given by the user request to represent different data. Digging into these files reveals a set of hard-coded queries, where the only possible modification is the parameter defined by the user request to the server.

After the query modification, it is then embedded as a request to the Wikidata Query Service, leaving the responsibility of finding, formatting and visualizing the data to the aforementioned service.

In general, Scholia has a set of pre-defined queries that are partially customizable by the user, that are then visualized by the Wikidata Query Service. Scholia itself has no idea of the data or its visualizations, it only manipulates and sends requests (which can be seen as a strength or weakness, depending on the goal we want to reach)


### Weaknesses

Quickly glancing over the `scholia/app/views.py` will reveal a lot of redundancy in the code, most functions can be generalized, the documentation of each function reveals little information on the inner working of that function, naming schemes are not very developer friendly, variables are mostly global and scattered over 100 files of the project.

Scholia has more of a horizontal architecture, it tries to include as many domains as possible by sacrificing richness and depth in these domains.


## Visualization

### Examples
* (https://tools.wmflabs.org/scholia/topic/Q45340488) \
    * Co-Author-Graph
    * Co-occurring topics graph
    * Author Score

* (https://upload.wikimedia.org/wikipedia/commons/f/f3/Scholia_and_scientometrics_with_Wikidata_-_Figure_1.png) \
    * Number publications per year
    * Number of Pages per year

* (https://upload.wikimedia.org/wikipedia/commons/7/7e/Scholia_profile_for_the_topic_of_Zika_virus_-_screenshot-2018-7-4.png) \
    * Authors publishing about the topics
    * Co-occuring topics maps

### Visualization Types
* Table
* Line chart
* Bar chart
* Scatter chart
* Area chart
* Bubble chart
* Tree
* Tree map
* Timeline
* Dimensions
* Graph 

There is also the possibility to use the “graph builder” tool, provided by polestar/UW Interactive Data Lab. It functions using a GUI that allows the user to drag and drop the provided information into the  x-,y-axis and/or columns and rows. The provided data is then used to generate a plot which can be visually adjusted, e.g. the marks on the plot can look like circles(points) or lines(ticks) etc. Further adjustments can be made to size, color, shape, details and even text per mark. 
This implies that the visualizations itself are not executed using Scholia but rather other third party libraries. In the case of expanding or improving on visualizations we would have to not develop for Scholia but rather for the Wikidata Query Service or UW Interactive Data Lab. As such, it would make sense to develop the visualizations separately and ensure the compatibility/importability for Scholia. 

### Additional Tools

* edit Visualisation
* edit SPARQL
* Help
* Examples
* Link
* Download

Even though, these are provided for each graph, the functionality does not seem to be entirely implemented. The buttons/links only function when opened in a seperate tab otherwise they do not open at all. In addition, the last three links open an error page declaring the query as damaged from line 1. This indicates a possibility for improvement.

### Timelines

The possibility to create timelines is already available, however, it is limited by the provided data e.g. only dates of citation and publication are provided and visualized. Very few and isolated data points that do not give an overall view of the usefulness of the work over time. A Timeline only containing one date of publication is useless. If it can be compared to other publications around that time it might have more merit. 
Timelines are better utilized in conjunction with an author as it allows the tracking of the authors published works. This can be very useful, but is currently limited to one author at a time. 
This opens the possibility of replicating this for one topic, e.g. “Ebola” which shows all publications on “Ebola” over time. 

### Tables

* Topic scores
* Recent publications
* Proceedings publications
* Related events
* Related based on time and location
* Related based on people

These can be useful, however the visualization could be improved upon. Currently they are simply depicted in tables. Using the provided data either graphs or point clouds could be more useful. 
They also contain arbitrary scores which are not explained such as: Score	, Time score and Location score. This makes the information meaningless as it cannot be understood or used properly. (If someone knows what they mean, I could be completely wrong about this).

## Good Scholia Examples

* Authors \
https://tools.wmflabs.org/scholia/author/Q20895241 in general it seams that Scholia works best for aggregating data by author rather than by topics or themes. As such the best use cases and visualizations are for authors. As such providing overviews for general research themes or topics could be interesting. 

## Proposed Improvements
* Add / Repair the Link and Download functionalities.
* Expand on timelines to allow data beyond citation and publication dates.