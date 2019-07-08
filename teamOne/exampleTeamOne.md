---
layout: default
title: Example
parent: 'Team 1: Data Context' 
nav_order: 1
---

### Our team 


**Author:** [Mahmoud](https://github.com/kozae), [Abdullah Barhoum](https://github.com/AbdBarho), [Hannah](https://github.com/HannahMariechen),[Juliane Wundermann](https://github.com/julianewundermann), [Janina Hantke](https://github.com/Jhantke)

***

## Data context

So that the other groups do not have to deal with the data set in detail, our main goal has been to make the bibliographic data from the PIK accessible. This means that the dataset must be in reasonably good quality and compatible with the data model of Wikidata before we can give the dataset to the next group.

### Quality of the data set

The quality of the data set can be measured by its completeness and consistency. 
In some columns, many entries were missing. Because filling the missing data would take some time and we only have a limited and short project time, the completeness of the data set was neglected and the existing data were checked for consistency. For this purpose, the complete data set was examined and the inconsistencies of the individual columns were corrected.  Under inconsistencies, for example, you can imagine different spellings for the same entry, or different number systems for a column.  In other words, a column must have formatting in itself and not different ones.  An example: we found the word "Öko" in the following spellings: Oeko, oeko, Öko, öko.  Another example is the names of the authors. These were either written out in full or the first name was abbreviated.   Such and other inconsistencies were then cleaned up using self-written scripts or using OpenRefine.  OpenRefine is an open source application that allows you to determine the differences using different algorithms and thus combine the entries of a column into clusters. In addition, entries that occurred in duplicate have been deleted.  After all, columns had been checked and cleaned, the data set could be adapted to the data model. Furthermore, a guideline was written for future datasets, to what extent consistency can be taken into account when creating such datasets and what would possibly facilitate further work.


### Data model

The data must have a specific structure so that the data can be uploaded to the database and the people from the visualization can do something with it. We have reworked our data model several times and finally opted for this model:

<img src="https://user-images.githubusercontent.com/46645533/59503820-ade73380-8ea1-11e9-904f-e635717fcf41.jpg"  />

Why exactly this model? In the long run, we wanted to adapt our model to the structure of Wikidata and our previous models did not correspond at all to the data model of Wikidata. We created this data model based on Wikidata's data structure. We also had other options to use the data after the cleanup of the data set. This model now also fits better to the cleansed data set. The graphic shows how the data types in Wikidata are connected and which subclasses exist for a class. Parallel we have written down the Wikidata properties for each class or subclass. For example, the class "book" has the subclasses "title", "chapter" and "place of publication". The dataset was adapted using this data model and passed on to the next group.

The complete documentation can be found at  [Dokumentation: Data Cleansing and Model
 ](https://github.com/code-openness/Documentation/wiki/Data-Model)
