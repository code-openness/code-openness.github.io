---
layout: default
title: 'Team 3: Data Vizualization' 
nav_order: 3
has_children: true
permalink: /teamThree
---
Within this Software project, we worked on the vizualisation of a Bibliographic Dataset received from [PIK](https://www.pik-potsdam.de/pik-frontpage) on their research and publications over the past few years. As such, we quickly came upon the Open Source Project, [SCHOLIA](https://tools.wmflabs.org/scholia/). A tool perfectly suited to visualize the dataset, offering a veriety of visualization possibilities and infrastructure in connection with Wikidata. 
Thus, we created a standalone refactoring module, usable as a library for SCHOLIA. The module allows for the dynamic visualization of tables and iFrame graphs. As such, all that is needed to generate a new graph is the necessary query. The query will then be normalized to achieve a standardized format, thus avoiding URL encoding problems. As such, even if the query is not perfectly formatted it will still generate the correct visualization. 
In addition, the SCHOLIA endpoint can also be dynamically changed. This is useful to visualize bibliographic data from other databases beyond Wikidata, such as the PIK dataset provided for this projekt. 

So far the module allows for three types of visualizations: 
- Using HTML Table
- Using iFrame Graphs
- Manual
It also contains a dev-playgorund, which demonstrates the use of these visualization methods and allows the active viewing of changes before pushing them.

[View on GitHub](https://github.com/code-openness/sparql-visualizer){: .btn .btn-purple }
[Further Internal Project Documentation](https://github.com/code-openness/Documentation/wiki){: .btn .btn-purple }
