---
layout: default
title: Quality of the data set
parent: 'Data Context' 
nav_order: 2
---


### Quality of the data set

The quality of the data set can be measured by its completeness and consistency. 
In some columns, many entries were missing. Because filling the missing data would take some time and we only have a limited and short project time, the completeness of the data set was neglected and the existing data were checked for consistency. For this purpose, the complete data set was examined and the inconsistencies of the individual columns were corrected.  Under inconsistencies, for example, you can imagine different spellings for the same entry, or different number systems for a column.  In other words, a column must have formatting in itself and not different ones.  An example: we found the word "Öko" in the following spellings: Oeko, oeko, Öko, öko.  Another example is the names of the authors. These were either written out in full or the first name was abbreviated.   Such and other inconsistencies were then cleaned up using self-written scripts or using OpenRefine.  OpenRefine is an open source application that allows you to determine the differences using different algorithms and thus combine the entries of a column into clusters. In addition, entries that occurred in duplicate have been deleted.  After all, columns had been checked and cleaned, the data set could be adapted to the data model. Furthermore, a guideline was written for future datasets, to what extent consistency can be taken into account when creating such datasets and what would possibly facilitate further work.



