---
layout: default
title: Scholia's Grant Proposal
parent: 'Team 3: Data Vizualization' 
nav_order: 7
---

**Date:** 22.05.2019

**Team:** Data Visualization

**Author:** [Ulrike Bath](https://github.com/ulibath)

---

Grant Proposal: [https://riojournal.com/article/35820/](https://riojournal.com/article/35820/)

## Main Goal:
* Back-end: make its infrastructure stable, well designed, well documented, and orderly for others to test and examine
* Front-end: priority is conforming to Wikimedia standards for accessibility and internationalization

## What is the approach being taken?
### 1. Back-end development and testing with pilot corpora
* requires systematic testing of Scholia performance across possible use cases or usage scenarios
* optimize the infrastructure

### 2. Redesign of the Scholia user interface for better usability, e.g. site navigation and internationalization
* requires integration with Wikimedia standards of high usability at a global scale and using accessible design whenever possible
* Wikimedia projects already have multilingual infrastructure into which we can integrate Scholia to share its language interface with other Wikimedia translation efforts, particularly through Wikidata

### 3. Improving integration with WikiCite curation workflows, e.g. around missing data
* Wikimedia: "citation needed" invite users to contribute, enrich, and critique the available information
* WikiCite project has tools for data curation on Wikidata: Author Disambiguation tool (Smith 2019), SourceMD tool (Manske 2019)    
* integrate such tools more closely with Scholia, so that as with Wikipedia, anyone who is reading the information gets an invitation to add or modify content.

### 4. Enhancing Wikidata-based reference management for scholarly writing workflows
* Scholia has a number of additional functionalities e.g. regarding entity recognition or reference management
** due to a Python library that processes BibTeX and thereby provides the ability to cite references in TeX/LaTeX documents through their Wikidata identifier or DOI, such that the citation is generated based on the reference’s metadata as available from Wikidata
* needs to be made more comprehensive and robust 
* If that is achieved and its usage scaled up, this would provide a compelling way for the community of BibTeX users to share the curation of their metadata through Wikidata

### 5. Establishing metrics to generate usage stats for Scholia pages and key bibliographic properties and items
* currently: basic metrics for usage statistics of Scholia-related Wikidata properties
* goal: routine availability of metrics
** support contributors and partners with the media metrics that institutions use to demonstrate the value they get from engagement

### 6. Improving documentation of corpus, code, queries, workflows, examples and related resources, as well as limits of Scholia
* documentation priorities include routine usage instructions, lay and accessible interpretations of visualizations, notes on the underlying queries and data sources, and statements about gaps and biases