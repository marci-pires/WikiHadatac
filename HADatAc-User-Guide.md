# Getting Started

[Section 3](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#3-using-hadatac) provides a set instruction on how to use HADatAc once HADatAc is ready to be use. This set of instructions progress from understanding its initial page to uploading data and metadata to searching the data to eventually selecting and downloading the data. But before one can actually use the app, one needs to install HADatAc, according to [Section 1](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#1-installing-hadatac), and set it up, according to [Section 2](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#2-setting-up-hadatac).

We strongly recommend starting with a development version of HADatAc that can run on either [Linux](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#12-on-linux-development) or [MacOS](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#13-on-macos-development).

# Installing HADatAc 

HADatAc can be installed for _development_ purposes, or for _production_ purposes. When installed for development, HADatAc does not require the setting of an email service since just one user with full access to the system is created. When installed for production, HADatAc requires access to an email service so that new users and access levels can be created and users can be authenticated through an email verification process.

## On Linux (Production) <img src="https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec1/linux.jpeg" width="38">

[Section 1.1.](https://github.com/paulopinheiro1234/hadatac/wiki/1.1.-Installing-for-Linux-(Production)) provides the installation instructions for HADatAc on Linux. This PRODUCTION installation is based on a distribution package and requires comprehensive configuration of the app including connection to an emailer. Production installation is required when the installation is expected to be **used by multiple users**, and the app is **regularly upgraded** by an upgrade script.

## On Linux (Development) <img src="https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec1/linux.jpeg" width="42">

[Section 1.2.](https://github.com/paulopinheiro1234/hadatac/wiki/1.2.-Installing-for-Linux-(Developer)) provides installation instructions for HADatAc on Linux. This DEVELOPMENT installation is much simpler than the production installation but is designed to allow just one main user to use the system. In this version, you work from a folder in your local filesystem that is connected to git.  

## On MacOS (Development) <img src="https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec1/macos.png" width="38">

[Section 1.3.](https://github.com/paulopinheiro1234/hadatac/wiki/1.3.-Installing-for-MacOS-(OSX)) provides installation instructions for HADatAc on MacOS (OSX). This DEVELOPMENT installation is designed to allow just one main user to use the system. In this version, you work from a folder in your local filesystem that is connected to git.  

## Deploying on Docker 

[Section 1.4.](https://github.com/paulopinheiro1234/hadatac/wiki/1.4.-Deploying-on-Docker) provides deployment instructions for HADatAc on a Docker container. 

***

# Setting Up HADatAc

## Software Configuration

Correct configuration is required for HADatAc to access its repositories, the ontology repository, to connect to users through email, to adjust to operating system requirements, etc. [Section 2.1.](https://github.com/paulopinheiro1234/hadatac/wiki/2.1.-Software-Configuration) describes the many configuration files of HADatAc and how they may be used.

## Knowledge Graph Bootstrap

HADatAc's Knowledge Graph (KG) is the main element allowing the app to manage files and their content. [Section 2.2.](https://github.com/paulopinheiro1234/hadatac/wiki/2.2.-Knowledge-Graph-Bootstrap) describes the KG's boostrapping process required to initiate the KG. HADatAc should be ready to be used after its software components have been installed (Section 1), the main software components has been configured (Section 2.1), and its knowledge graph has been bootstrapped (Section 2.2).

## Config Verification

A "version" link is available at the bottom of HADatAc's homepage. This link provides information about the current installation including version of the deployed code and properties of the base ontology. [Section 2.3.](https://github.com/paulopinheiro1234/hadatac/wiki/2.3.-Config-Verification) provides more details about the information shown in the link.

***

# Using HADatAc

## Getting Data and Metadata In

Data files (i.e., files starting with a **DA-** prefix), data messages (i.e., broadcasted over the web through an IP adress), and metadata files (files with names starting with any of the following prefixes: **DPL**, **STD**, **SSD**, **SDD** or **STR**) are used to fed content inside HADatAc. [Section 3.2.](https://github.com/paulopinheiro1234/hadatac/wiki/3.2.-File-Upload) describes a basic way of manually submit files for ingestion. 

## Searching and Browsing the Knowledge Graph

HADatAc's data faceted search is a main mechanism to inspect the actual overall content of the infrastructure, and of selecting this content across studies and instruments. [Section 3.5.](https://github.com/paulopinheiro1234/hadatac/wiki/3.5.-Data-Search) describes how to understand available content, and to select the content for eventual downloads.

Metadata stored in HADatAc can be browsed and searched through the app. [Section 3.6.](https://github.com/paulopinheiro1234/hadatac/wiki/3.6.-Metadata-Browser-and-Search) describes these capabilities. 

## Getting Data and Metadata Out

At any moment during the use of a faceted search, users are allowed to download the content related to the current search. [Section 3.8.](https://github.com/paulopinheiro1234/hadatac/wiki/3.8.-Data-Download) describes the many options on how to download the data selected under the current search.

Data and metadata stored in HADAtAc can also be retrieved programmatically. [Section 3.7.](https://github.com/paulopinheiro1234/hadatac/wiki/3.7.-API) describes a list of RESTful services. Data visualization frameworks, visual analytical frameworks and dashboards with a back end HADatAc support are expected to use the API to retrieve content from the app.  

## Further reading: 

### Software Architecture and Knowledge Specification

HADatAc is implemented as a web application. [Section 4.1.](https://github.com/paulopinheiro1234/hadatac/wiki/4.1.-Software-Components) describe how the main website is built in terms of software components. The section also describe what data repositories are used for managing data and metadata content, and what infrastructure(s) is/are used to manage evolving ontologies.  

HADatAc's knowledge graph is composed by a collection of ontologies, a knowledge base with many instances of concepts defined in the ontologies. A collection of foundational ontologies along with the definition of key concepts that are used to align key concepts of the combined vocabulary of these ontologies is embedded into the Human-Aware Science Ontology described in [Section 4.2.](https://github.com/paulopinheiro1234/hadatac/wiki/4.2.-The-Human-Aware-Science-Ontology-(HAScO)).  

### Metadata Files

[Section 5](https://github.com/paulopinheiro1234/hadatac/wiki/5.-Metadata-Files) describes the five kinds of semantic metadata specifications used to describe a study's data content: 
* Deployment Description (DPL); 
* Study Description (STD);
* Semantic Study Design (SSD); 
* Semantic Data Dictionary (SDD); and 
* Stream Specification (STR).


