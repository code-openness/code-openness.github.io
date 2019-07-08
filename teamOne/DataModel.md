---
layout: default
title: Data model
parent: 'Data Context' 
nav_order: 2
---

### Data model
One of the goals was the preparation of the received and processed data set, for the data context team, as such, it had to be correctly structured. This was due to the need of uploading the data into a database, which could then be used as the basis for its visualization. Consequently, the data model was reworked several times, finally resulting in the version illustrated in the diagram below:
<img src="https://user-images.githubusercontent.com/46645533/59503820-ade73380-8ea1-11e9-904f-e635717fcf41.jpg"  />

Why exactly this model? It was imperative to consider the model's longevity, as such, the model had to be adapted, as previous incarnations did not correspond with the structure dictated by Wikidatas data model. 
The above data model was developed, entierly based on Wikidata's data structure. Resulting, in further applications for the data, after its cleanup and a better match between the cleansed data set and data model. The graphic shows the connections and relations between the data types in Wikidata and which subclasses exist for a class. 
In parallel, it depicts the Wikidata properties for each class and subclass. For example, the class "book" has the subclasses "title", "chapter" and "place of publication". The dataset was adapted using this data model and passed on to the Data Mapping Team.

[first ideas/data model](https://github.com/code-openness/Documentation/wiki/Concrete-Example-of-our-Model){: .btn .btn-blue }
[redesigned data model ](https://github.com/code-openness/Data/issues/19){: .btn .btn-blue }
