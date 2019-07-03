---
layout: default
title: Motivation
parent: 'Data Vizualization'
nav_order: 1
---
# Motivation
**Date:** 16.04.2019

**Team:** Data Visualization

**Author:** [Katharina Müller](https://github.com/Lianm123), [Abdullah Barhoum](https://github.com/AbdBarho), [Vitalij Krotov](https://github.com/vmk1vmk)

***
Our team is responsible for the visualization of the bibliographical data, one of our resources was Scholia, an open source tool that was built by Finn Arup Nielsen, Daniel Mietchen, and Egon Willighagen.

Scholia was built from the ground up around Wikidata, and its Query Service. It is written mainly in Python, and uses Flask internally to host a server that shows the resulting content.

Scholia has a set of pre-defined queries for the Wikidata Query Service, these queries are requested and the resulting visualizations are displayed in the browser. Users also have the option of interacting and modifying these queries so that they can display the data they want and how they want.

While Scholia defines the queries sent to the Wikidata Query Service, it does not visualize the data itself, but rather uses the visualizations already provided by the Query Service.

In general, Scholia is more of a demo project to show the Wikidata Query Service and how to interact with it.

Another important resource is the Wikidata Query Service, which is an online service that accepts SPARQL queries from the user, and returns the corresponding data, the client part of the service provides a group of visualizations that are rendered in the browser.

Because Scholia does not visualize the data itself, we unfortunately cannot use Scholia as a base to build upon, it might be more reasonable to start with our own tool, using the knowledge we take from Scholia.

 
It is possible to implement a small prototype to showcase the feasibility of the implementation of such project as a proof of concept. This prototype will help us discover the limitations and try to familiarize ourselves with the tools and concepts that we will be using later.
 
The prototype would consist of some mocked up data which we will visualize using the D3.js library, we are also considering using React to create the elements.
Each possible visualization consists of a data transformation step and a render step. These visualizations can be added or modified easily, guaranteeing the expandability of the UI.

 
Our end goal is an extensible data visualization tool with user-friendly design, many options/customizations which accepts data from different sources.

We have some visualizations in mind that seem applicable to almost all data types, such as: Histograms, bar charts and graphs.

We have already sketched some ‘concept’ for this prototype, which can be seen here:

<img src="https://user-images.githubusercontent.com/49868259/57782259-27b5c100-772c-11e9-91f3-a07295067108.jpg" width="700" height="900" />


