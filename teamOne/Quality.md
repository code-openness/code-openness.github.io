---
layout: default
title: Quality of the data set
parent: 'Data Context' 
nav_order: 1
---

# Quality of the data set
Data set quality is measured in its completeness and consistency. The tabular data set was received within a CSV file and roughly analyzed. Consequently, it was discovered that some columns lacked multiple entries. Due to the limited time available for this project, and the extensive time necessary to fill-in missing data, which was often unavailable, data completeness was omitted.  Instead, the existing data were checked for consistency by examining and correcting inconsistencies in the individual columns. Inconsistencies can include different spellings for the same entry, or different number systems for a column. In other words, a column must have one unified formatting in itself and not several.

For example, we found the word "Öko" in the following spellings: Oeko, oeko, Öko, and öko. Another example is the names of the authors. These were either written out in full or with the first name abbreviated. These inconsistencies and others were then cleaned up using self-written scripts and OpenRefine. 

OpenRefine is an open-source application that allows the determination of anomalies using different algorithms and thus combine the entries of a column into clusters. Additionally, entries that occurred in duplicate were removed. 
After all, columns had been checked and cleaned, the data set could be adapted to the data model. Furthermore, a guideline was written for future datasets describing to what extent consistency can be taken into account when creating such datasets and what would possibly facilitate further work.


[Scripts to clean up](https://github.com/code-openness/Data/tree/master/handlers){: .btn .btn-green }
[Requirement List for Dataset](https://github.com/code-openness/Documentation/wiki/Vorschläge-für-die-Qualitätssicherung-des-Datenbestandes){: .btn .btn-green }

