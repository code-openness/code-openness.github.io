---
layout: default
title: Data model
parent: 'Team 1: Data Context' 
nav_order: 3
---


The data must have a specific structure so that the data can be uploaded to the database and the people from the visualization can do something with it. We have reworked our data model several times and finally opted for this model:

(Grafik)

Why exactly this model? In the long run, we wanted to adapt our model to the structure of Wikidata and our previous models did not correspond at all to the data model of Wikidata. We created this data model based on Wikidata's data structure. We also had other options to use the data after the cleanup of the data set. This model now also fits better to the cleansed data set. The graphic shows how the data types in Wikidata are connected and which subclasses exist for a class. Parallel we have written down the Wikidata properties for each class or subclass. For example, the class "book" has the subclasses "title", "chapter" and "place of publication". The dataset was adapted using this data model and passed on to the next group.
