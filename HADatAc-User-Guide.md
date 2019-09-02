# Getting Started

This page provides a set of instruction and links on how to use HADatAc once the infrastructure. This set of instructions progress from installing and setting up the infrastructure to understanding its initial page, to uploading data and metadata, to searching the data, and to eventually selecting and downloading the data. 

## Installing HADatAc

We strongly recommend starting with a development version of HADatAc that can run on either Linux (as described in [Section 1.2](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#12-on-linux-development)) or MacOS (as described in [Section 1.3.](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#13-on-macos-development)).

## Setting Up HADatAc

Correct configuration is required for HADatAc to access its repositories, the ontology repository, to connect to users through email, to adjust to operating system requirements, etc. [Section 2.1.](https://github.com/paulopinheiro1234/hadatac/wiki/2.1.-Software-Configuration) describes the many configuration files of HADatAc and how they may be used.

HADatAc's Knowledge Graph (KG) is the main element allowing the app to manage files and their content. [Section 2.2.](https://github.com/paulopinheiro1234/hadatac/wiki/2.2.-Knowledge-Graph-Bootstrap) describes the KG's boostrapping process required to initiate the KG. 

HADatAc should be ready to be used after its software components have been installed, the main software components has been configured, and its knowledge graph has been bootstrapped.

***

# Using HADatAc

## Getting Data and Metadata In

Data files (i.e., files starting with a **DA-** prefix), data messages (i.e., broadcasted over the web through an IP adress), and metadata files (files with names starting with any of the following prefixes: **DPL**, **STD**, **SSD**, **SDD** or **STR**) are used to fed content inside HADatAc. [Section 3.2.](https://github.com/paulopinheiro1234/hadatac/wiki/3.2.-File-Upload) describes a basic way of manually submit files for ingestion. 

As already described above, there are many distinct types of content that can be submitted for ingestion into HADatAc. However, when submitting content for ingestion, the content needs to follow a partial order of file types specified in the __ingestion workflow__, which is described in [Section 3.4.](https://github.com/paulopinheiro1234/hadatac/wiki/3.4.-Metadata-Ingest).

Once study content has been ingested into the knowledge graph, the infrastructure can be use to search and browse the content of the knowledge graph as described in the next section.

## Searching and Browsing the Knowledge Graph

HADatAc's data faceted search is a main mechanism to inspect the actual overall content of the infrastructure, and of selecting this content across studies and instruments. [Section 3.5.](https://github.com/paulopinheiro1234/hadatac/wiki/3.5.-Data-Search) describes how to understand available content, and to select the content for eventual downloads. Data faceted search is described in [Section 3.5.1.](https://github.com/paulopinheiro1234/hadatac/wiki/3.5.1-Data-Faceted-Search). Data spatial search is also available when ingested data is semantically annotated with spatial properties. Data spatial search is described in [Section 3.5.2.](https://github.com/paulopinheiro1234/hadatac/wiki/3.5.2.-Data-Spatial-Search).  

Metadata stored in HADatAc can be browsed and searched through the app. [Section 3.6.](https://github.com/paulopinheiro1234/hadatac/wiki/3.6.-Metadata-Browser-and-Search) describes these capabilities. 

The actual knowledge graph of the infrastructure can be graphically inspected using the Browse Knowledge Graph capability described in [Section](). 

## Getting Data and Metadata Out

At any moment during the use of a faceted search, users are allowed to download the content related to the current search. [Section 3.8.](https://github.com/paulopinheiro1234/hadatac/wiki/3.8.-Data-Download) describes the many options on how to download the data selected under the current search.

Data and metadata stored in HADAtAc can also be retrieved programmatically. [Section 3.7.](https://github.com/paulopinheiro1234/hadatac/wiki/3.7.-API) describes a list of RESTful services. Data visualization frameworks, visual analytical frameworks and dashboards with a back end HADatAc support are expected to use the API to retrieve content from the app.  

***

# Further reading: 

## Software Architecture and Knowledge Specification

HADatAc is implemented as a web application. [Section 4.1.](https://github.com/paulopinheiro1234/hadatac/wiki/4.1.-Software-Components) describe how the main website is built in terms of software components. The section also describe what data repositories are used for managing data and metadata content, and what infrastructure(s) is/are used to manage evolving ontologies.  

HADatAc's knowledge graph is composed by a collection of ontologies, a knowledge base with many instances of concepts defined in the ontologies. A collection of foundational ontologies along with the definition of key concepts that are used to align key concepts of the combined vocabulary of these ontologies is embedded into the Human-Aware Science Ontology described in [Section 4.2.](https://github.com/paulopinheiro1234/hadatac/wiki/4.2.-The-Human-Aware-Science-Ontology-(HAScO)).  

## Metadata Files

[Section 5](https://github.com/paulopinheiro1234/hadatac/wiki/5.-Metadata-Files) describes the five kinds of semantic metadata specifications used to describe a study's data content: 
* Deployment Description (DPL); 
* Study Description (STD);
* Semantic Study Design (SSD); 
* Semantic Data Dictionary (SDD); and 
* Stream Specification (STR).


