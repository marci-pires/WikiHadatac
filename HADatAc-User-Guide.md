# 1. Installing HADatAc

HADatAc can be installed for _development_ purposes, or for _production_ purposes. When installed for development, HADatAc does not require the setting of an email service since just one user with full access to the system is created. When installed for production, HADatAc requires access to an email service so that new users and access levels can be created and users can be authenticated through an email verification process.

## 1.1. On Linux (Production)

Use these [installation instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Installing-for-Linux-(Production)) install a production HADatAc on Linux.

## 1.2. On Linux (Development)

Use these [installation instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Installing-for-Linux-(Developer)) to install a development HADatAc on Linux.

## 1.3. On MacOS (Development)

Use these [installation instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Installing-for-MacOS-(OSX)) to install a development HADatAc on MacOs.

## 1.4. Using Docker

Use these installation instructions to install a virtual machine with a development HADatAc.

***

# 2. Setting Up HADatAc

HADatAc need to be configured so that it can access its corresponding repositories. Lets assume that "/data/hadatac/" is the folder where HADatAc is installed, in this case, configuration files are located at "/data/hadatac/conf". 

Use these [configuration instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Setting-up-HADatAc-Configuration)  to set up HADatAc.

***

# 3. Using HADatAC

## 3.1. Data Upload

We call _data uploading_  the process of adding content into the data repository, and _data ingestion_ the process of collecting, organizing, indexing content's metadata, and as important, the process of connecting the newly organized metadata to the content. 

Using traditional databases developers are requires to develop one very large schema to manage both the data content and its associated metadata, and to make sure that content identifiers and corresponding metadata are properly connected.	 
The use of ontologies to guide the process of organizing metadata alleviates the task of organizing the metadata since the data becomes self-organizing when values are tagged with terms from a common set of ontologies. Furthermore, ontologies also help the process of logically connecting data to newly created graphs inside of the metadata repository.

The screenshot above shows how data files can be uploaded into HADatAc in ways very similar to other well established cloud-based online repositories like Dropbox and Google drive. For instance, the “DA-CBIS-Feb-2017-DMG-B-3.csv” file, which is a data file, was uploaded into the infrastructure and now it is assigned to a user who can leave the datafile there or may decide to share, download or even delete the file. 

Once files are uploaded, they can either be automatically ingested in case the infrastructure’s knowledge base knows how to process the file, or may guide scientists in the process of telling the system how to ingest the data. 

## 3.2. Data Preparation and Ingestion

The green button next to the file above indicates that HADatAc does not know how to ingest this specific file, and that more information is needed from the data owner to move the data content and its metadata content inside of this particular file into HADatAc repositories.  

The screenshot below shows the workflow for the infrastructure to ingest the data. For instance, under the current configuration of this specific repository, an image may be associated with the following:

* A Study identification provides a high level contextual justification for the image to be. For instance, a given image or image collection may be the result of a formal observational or experimental study, or may be the exam results during the process of assessing a patient  

* Semantic Object Collections (SOCs) identify how entities involved with a study are organized as collections of tangible objects (e.g., subjects, samples) and collections of contextual objects (e.g., categories, time events, locations). The figure below shows how SOCs are defined and managed in our infrastructure.
 
* Scoping semantic objects identify which of the SOCs of a study may be associated with the image being loaded. In this case, the scoping objects may be an entire collection requiring the file to contain some form of identifier.   

  * Deployments identify how Instruments used to collect data are deployed at a given Platform. The platform may be a 
    laboratory that gives an instrument its necessary operational conditions, and it can also be a person wearing some 
    sensor. It is relevant to note that we consider a very broad notion of instrument since we see Questionnaires and 
    Computer Simulation Models as forms of instruments. Traditional instruments like an MRI machine are instances of 
    Physical Instrument.  

  * Semantic Data Dictionaries (SDDs) are use to specify both the meaning of the content of an image as well as to identify 
    how the file is organized. The figure below shows the  example of an SDD where each field of the data dictionary is 
    assigned to a collection of ontological terms identifying what is the type of entity behind of the image, what is the 
    attribute of the entity being measured, what is the unit of measurement, when, where, and at which accuracy the 
    measurement is made. 

The following screenshot provides more details about how each one of the SDD fields is edit according to terms coming from an integrated knowledge graph. The tabs on the right allow SDD developers to browse and select terms from the hierarchy of entities, attributes and units. Additional contextual knowledge such as the association of the current field to other temporal and spatial fields is done in the form on the left side of the image.

## 3.3. Data Search

The screenshot above shows HADatAc’s Data Faceted Search where users go to select interactively select and download HADatAc content for analysis, including the possibility of data owners sharing their data with other users. 

We observe that scientific images would take central stage in the faceted search with image metadata being used to play multiple roles during the process of selecting and downloading images from the image repository. 

**Facet Panel**: Each property of images can be used as facets, where the actual selection of a facet is the selection of one or more possible values for each image. For instance, images may be selected by its source (a study, an image collection), by physical characteristics of the entities the image is from (part of a body, presence of some feature, known disease), by the instruments generating the images (e.g., MRI, CAT Scan), and so on.

**Scientific Data Panel**: It provides a preview of the images to be downloaded providing some contextual data like the IDs of the subjects and/or samples, temporal and spatial information.

**Detail Panels**: It provides more in-depth explanation about information that can be found on the facets and in the Scientific Data Panel, and such detailed information may contain links to actual external documents that enable a quick investigation from users on whether the current selection of the search corresponds to the actual data to downloaded from the repository of if further refinement/relaxation of the selection criteria is necessary.
Data Faceted Search

[Metadata Browser](https://github.com/paulopinheiro1234/hadatac/wiki/HADataC-User-Guide:--Metadata-Browser)
 
Metadata management including HASNetO-Loader (also available for batch execution)


## 3.4. Data Download

***

# 4. Architecture

## 4.1. Overview

HADatAc has a web-based application and an underlying content repository infrastructure. The web-based application is used to manage data security and privacy, to delete and archive existing repository content, to upload new content into the repository, and to provide multiple ways of searching for data and metadata with the use of a collection of faceted searches.  

HADatAc content repository infrastructure is organized as follows:

* Data are stored in Apache SOLR instances, which are highly-scalable no-SQL solutions for managing unstructured, semi-structured and structured data;  

* Metadata are stored in SOLR instances as a knowledge graph, and managed with the use of a Apache JENA-based API. HADatAc may also be based on any other SPARQL-based knowledge graph repository since RESTful SPARQL queries are the way for the web application to communicate with the underlying RDF repository.  
Metadata stored in HADatAc is composed of concepts and instances, also known as objects. Concepts come from ontologies published on the web and objects, which are concept instances, come from LabKey, which is an open-source, web-based Laboratory Information Management System (LIMS). A combination of concepts and instances related to some scientific activities, e.g., a study, can be described as the knowledge graph of those activities, Thus, HADatAc uses LabKey as its preferred way of inputting and editing knowledge graphs.

After respecting security and privacy policies in place, HADatAc allows advanced users to access data in SOLR with the use of Lucene queries, and to access metadata in SOLR with the use of SPARQL queries. 

## 4.2. Interactive Web Console functionalities


## 4.3. Batch automated functionalities

[Data management](https://github.com/paulopinheiro1234/hadatac/wiki/HADataC-User-Guide:--Data-Management) including HADataC-Loader (also available for batch execution)

***

# 5. Data Governance

## 5.1. User Categories and Console Permission Functionalities

Users are either _unregistered_, _pre-registered_, or _registered_. A registered user is one who went through the process of signing up for HADatAc and confirming the authenticity of her/his email address. A registered user is capable of logging into the system and owning data. An admin user has the permission of granting admin permission to any registered user. A user can only sign up to become registered if the user was previously pre-registered into the system by an admin user. 
 
**Administration (admin) user**: One default administration user is automatically created during a HADataC installation. This is the admin user who can pre-register new users and grant admin status to other registered users. A user is said to be a pre-registered if the user is included into the HADataC metadata repository and has not yet signed up.   

**Data owner**: Every registered user is considered a data owner, whether the user actually owns or not any data in the data repository. A data owner is capable of the following: uploading data and metadata into the system; recording deployment metadata; annotating data with metadata; setting the permission of who has the right of accessing their data; deleting their data from the system.  

**Guest user**: Every user is considered unregistered until the user logs into the system. Unregistered users can access and download publicly available data. Unregistered users cannot upload and own data in the HADataC system.

### 5.1.1. User Registration

#### Pre-Registration

Admin users should fill out the HASNetO agent's spreadsheet with the relevant information about HADataC users including the list of organizations associated with users and relationship between associated organizations. An admin user should upload the spreadsheet into the system by using the metadata loader, which will transfer all the agent information into the knowledge base. Agent information added into the system includes all the relevant user pre-registration information.

#### Full Registration

#### User Graph and Authentication Backup and Recovery
Users having admin privilege can easily perform backup and recovery operations on user graph (e.g. user profiles, access levels, etc) and authentication (e.g. accounts, encrypted passwords, security roles, etc) when system upgrade necessitates this. To backup, go to the **Manage Users** page and then you will see an button called **Backup User Authentication** for exporting a **.json** file containing required information for recovering later, and another button called **Backup User Graph** for exporting a **.ttl** file containing the whole user graph. To recover, in the same page, use the file upload panel called **Load User Graph from turtle** first to upload the previously saved **.ttl** file for recovering the user graph and then use another file upload panel called **Load User Authentication from json** to upload the previously saved **.json** file for recovering the user authentication.

## 5.2. Data and Metadata Privacy

## 5.3. Data and Metadata Preservation

***

# 6. Using Other HADataC Products

MOCCASN

