---
layout: default
title: Data model
parent: 'Data Context' 
nav_order: 2
---

### Data model
The data must have a specific structure so that the data can be uploaded to the database and the people from the visualization can do something with it. We have reworked our data model several times and finally opted for this model:

<img src="https://user-images.githubusercontent.com/46645533/59503820-ade73380-8ea1-11e9-904f-e635717fcf41.jpg"  />

Why exactly this model? In the long run, we wanted to adapt our model to the structure of Wikidata and our previous models did not correspond at all to the data model of Wikidata. We created this data model based on Wikidata's data structure. We also had other options to use the data after the cleanup of the data set. This model now also fits better to the cleansed data set. The graphic shows how the data types in Wikidata are connected and which subclasses exist for a class. Parallel we have written down the Wikidata properties for each class or subclass. For example, the class "book" has the subclasses "title", "chapter" and "place of publication". The dataset was adapted using this data model and passed on to the next group.




[first ideas/data model](https://github.com/code-openness/Documentation/wiki/Concrete-Example-of-our-Model){: .btn .btn-blue }
[redesigned data model ](https://github.com/code-openness/Data/issues/19){: .btn .btn-blue }
