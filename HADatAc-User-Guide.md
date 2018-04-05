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

## 2.1. Application Configuration

HADatAc needs to have a correct configuration to access its repositories. Let assume that "/data/hadatac/" is the folder where HADatAc is installed, in this case, configuration files are located at "/data/hadatac/conf". 

Use these [configuration instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Setting-up-HADatAc-Configuration)  to set up HADatAc.

## 2.2. Knowledge Graph Bootstrap

HADatAc can only process data if its supporting knowledge graph has the correct knowledge added to its knowledge base. Use the [bootstrapping instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Bootstrapping-HADatAc's-Knowledge-Graph) to initiate HADatAc's knowledge graph.  

***

# 3. Using HADatAc

## 3.1. Initial Page

The main page is composed of two or three vertical blocks of functionalities (three blocks if the user is an administrator). The first block has the functionalities required for a user to search and retrieve content from HADatAc. The second block has the functionalities required to update and maintain content in HADatAc. The third block has the functionalities required for managing underlying knowledge as described in Section 3.6 of this User Guide.  

## 3.2. Data Upload

We call _data uploading_  the process of adding content into the data repository, and _data ingestion_ the process of collecting, organizing, indexing content's metadata, and as important, the process of connecting the newly organized metadata to the content. 

Using traditional databases developers are requires to develop one very large schema to manage both the data content and its associated metadata, and to make sure that content identifiers and corresponding metadata are properly connected.	 
The use of ontologies to guide the process of organizing metadata alleviates the task of organizing the metadata since the data becomes self-organizing when values are tagged with terms from a common set of ontologies. Furthermore, ontologies also help the process of logically connecting data to newly created graphs inside of the metadata repository.

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec3/DatafileManagement.png)

The screenshot above shows how data files can be uploaded into HADatAc in ways very similar to other well established cloud-based online repositories like Dropbox and Google drive. For instance, the “DA-CBIS-Feb-2017-DMG-B-3.csv” file, which is a data file, was uploaded into the infrastructure and now it is assigned to a user who can leave the datafile there or may decide to share, download or even delete the file. 

Once files are uploaded, they can either be automatically ingested in case the infrastructure’s knowledge base knows how to process the file, or may guide scientists in the process of telling the system how to ingest the data. 

## 3.3. Data Preparation and Ingestion

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec3/DataPreparation.png)

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

## 3.4. Metadata Ingest

Metadata content is added into HADatAc through the use of online forms or through the uploading and ingestion of content files. Content files can further be added manually or automatically.  

Name conventions are required for automated ingestion of content file. Files that do not follow name conventions can only be further processed if manual commands are issued to identify file content as well as any additional information that may be needed to enable a proper ingestion of content files.

If some anomaly occurs during the processing of any files, whether the file is supposed to be processed manually or automatically, the file will be put on hold and an error message will appear in the file log. The log is visible on-line.

### 3.4.1. Inserting Metadata Content Manually

### 3.4.2. Automated Ingestion of Metadata Content

### 3.4.2.1 Types of Metadata Content Files

**STD Files**

Used to include one or more study basic information into HADatAc. Information in STD files include things like PI's name and address. Study's aims, short description and long description.

**PID Files**

Used to add one or more human participant to an existing study. The content of this file is mainly about how many subjects are to be added to a given study, and how these subjects are identified in their corresponding studies. For HADatAc, their identification in the study is called _originalID_. Properties about these subjects are often added as study data.

**SID Files**

Used to add one or more sample to an existing study. The content of this file is mainly about how many samples are to be added to a given study, and how these samples are identified in their corresponding studies. For HADatAc, their identification in the study is called _originalID_. Properties about these samples are often added as study data although an SID file may include some information about samples.

**MAP Files**

Within the scope an study, MAP files are used to assign samples to subjects. For instance, a blood sample added through an SID file may be assigned to be a sample from a human subject added through a PID file. In case a sample included in the MAP file is not available in the study, then it is included. Therefore, MAP files may be used as SID files in case the mapping between subjects and samples is known by the time the MAP file is submitted. 

**SDD Files**

Used to guide the process of ingesting file content into HADatAc databases.

A single SDD file can be used to ingest the content from multiple files as long these files share the same content type.
DA Files
‘DA-‘ is the prefix used to identify data files, as opposed to metadata files (i.e., STD, PID, MAP files). 

**ACQ Files**

In this case, we use ACQ files to identify a common ‘prefix’ that is assigned to a given content type (data files). For instance, if File1.csv and File2.csv both can use SDD-Z.xls, then we can create an ACQ file saying that ‘DA-Z’ is the prefix for SDD-Z.xls. In this case, we could rename File1 into DA-Z-1 and File2 into DA-Z-2 enabling the use of SDD-Z on both files.

ACQ Files are also used to assign files to studies and to a given owner. Thus, we need an ACQ file for each collection of files (including collections of 1 file) that share the same properties:
* Type of data content
* Owner
* Study that it belongs to

#### 3.4.2.2. Examples of Content File Uploading for Studies

**A Simple scenario**

Let assume the following for study X: 
* X has 100 subjects
* X has 200 samples corresponding to 2 samples per subject
* A single file is submitted with the EPI data for the 100 subjects
* A single file is submitted with the Lab data for the 200 samples

This is the summary of data files for X:
* FileSubject.csv with EPI data about the 100 subjects
* FileSample.csv with Lab data about the 200 samples

In terms of type of file content:
* FileSubject.csv‘s type of content conforms to SDD-Subject
* FileSample.csv’s type of content conforms to SDD-Sample

This is what is needed: 
* Create one ACQ file (ACQ-X-Subject.csv) that maps the name ‘DA-X-subject’ to SDD-Subject and submit both SDD-Subject and ACQ-X-Subject.csv right away into HADatAc
* Create another ACQ file that maps the name ‘DA-X-sample’ to SDD-Sample and submit it right away into HADatAc
* Rename FileSubject.csv to ‘DA-X-subject.cvs’ and submit it into HADatAc after submitting its corresponding ACQ file 
* Rename FileSample.csv to ‘DA-X-sample.csv’ and submit it into HADatAc after submitting its corresponding ACQ file 

**A more complex scenario** 

Let assume the following for study Y: 
* Y has 100 subjects
* Y has 200 samples corresponding to 2 samples per subject
* A sample is collected from each subject at Visit1 and the second sample is collected from each subject at Visit2
* Y’s PI decided to submit 2 EPI files, one EPI file with demographic data about the 100 subjects, and the other EPI file with anthropometric  for the same subjects

This is the summary of data files for Y:
* FileA.csv with demographic data
* FileB.csv with anthropometric data
* FileC.csv with Lab data about 100 samples collected during Visit1 of each subject
* FileD.csv with Lab data about the other 100 samples collected during Visit2 of each subject

In terms of type of file content:
* Files A and B have different types of content, which conforms to SDD-1 and SDD-3
* Files C and D have the same type of content, which conforms to SDD-2

This is what is needed: 
* Create one ACQ file (ACQ1.csv) that maps the name ‘DA-type1’ to SDD-1 and submit both SDD-1 and ACQ1.csv right away into HADatAc
* Create another ACQ file that maps the name ‘DA-type2’ to SDD-2 and submit it right away into HADatAc
* Create another ACQ file that maps the name ‘DA-type3’ to SDD-3 and submit it right away into HADatAc
* Rename File A to ‘DA-type1-A.cvs’ and submit it into HADatAc after 
* Rename File B to ‘DA-type3-B.csv’
* Rename File C to ‘DA-type2-C.csv’
* Rename File D to ‘DA-type2-D.csv’

### 3.4.2.3 Ingestion Workflow

The exact way metadata files are fed into HADatAc may vary by application. Below, we describe a partial order of events that must be observed in automated workflows feeding metadata content into HADatAc:

* STD files can be submitted any time
* SDD files can be submitted any time
* PID files can be submitted before all the STD of studies listed in the file have been submitted and ingested (it is normally easy to have one PID file feeding PIDs of subjects from a single study) 
* SID files can be submitted before all the STD of studies listed in the file have been submitted and ingested (it is normally easy to have one SID file feeding SIDs of samples from a single study)
* MAP files can be submitted after all the PIDs and SIDs listed inside the file have been submitted and ingested
* ACQ files can be submitted after the following: STD of associated DA file have been submitted and ingested; SDD of associated DA file have been submitted and ingested
* DA files can be submitted after corresponding ACQ file have been submitted and ingested   

In the tasks above, it is said that files need to be submitted and ingested meaning that automated workflows should be able to verify that the ingestion of a given metadata file submitted into HADatAc was successful. This verification is accomplished through the use of the RESTFul service described below. 

## 3.5. Data/Metadata Search

### 3.5.1. Data Search

The screenshot above shows HADatAc’s Data Faceted Search where users go to select interactively select and download HADatAc content for analysis, including the possibility of data owners sharing their data with other users. 

**Facet Panel**: Each property of data can be used as facets, where the actual selection of a facet is the selection of one or more possible values for each data point. For instance, data may be selected by its source (a study, a data file), by physical characteristics of entities that the data is from (part of a body, presence of some feature, known disease), by the instruments generating the data (e.g., MRI, mass spectrometer, thermometer), and so on.

**Scientific Data Panel**: It provides a preview of data to be downloaded providing some contextual information like the IDs of the subjects and/or samples, temporal and spatial information.

**Detail Panels**: It provides more in-depth explanation about information that can be found on the facets and in the Scientific Data Panel, and such detailed information may contain links to actual external documents that enable a quick investigation from users on whether the current selection of the search corresponds to the actual data to downloaded from the repository of if further refinement/relaxation of the selection criteria is necessary.
Data Faceted Search

[Metadata Browser](https://github.com/paulopinheiro1234/hadatac/wiki/HADataC-User-Guide:--Metadata-Browser)
 
Metadata management including HASNetO-Loader (also available for batch execution)

### 3.5.1. Study Search

### 3.5.2. Metadata Search

## 3.6. Data Download

## 3.7. Knowledge Management

### 3.7.1. On the use of URIs

### 3.7.2. The Human-Aware Science Ontology (HAScO)

#### Supporting Ontologies

### 3.7.3. Ontology Management

### 3.7.4. Knowledge Graph Management

***

# 4. Architecture

## 4.1. Overview

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec4/architecture.png)

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

## 5.1. Access Network

Every HADatAc has one access network composed of 
* access levels and 
* users

HADatAc’s access networks are initially composed of one default access level called _public_. Every user belongs to one access level, and is an access level on its own. For instance, if the access network is brand new, it only has the access level _public_. Therefore, if a new user _User A_ is added, it is added under _public_. This means that any data added by _User A_ to HADatAc will initially belong to _User A_ who will be the only user capable of accessing that data. If _User A_ needs to share the data, _User A_ can relax the restriction on the data by moving the access to the data to _public_. 

On the same way that users are added to an access network, new access level can also be added. Public is the less restricted level of access in the access network and the further an access level with respect to _public_ the more restricted it the access level.

## 5.2. User Status, Categories and Access Permissions

Users have the status of either _unregistered_, _pre-registered_, or _registered_. A registered user is one who went through the process of signing up for HADatAc and confirming the authenticity of her/his email address. A registered user was capable of going through the registration process because he/she was pre-registered by an administrator. A user is unregistered if s/he is not registered or pre-registered.

Users also have categories that are described below. For instance, a registered user is capable of logging into the system and owning data. An admin user has the permission of granting admin permission to any registered user. 
 
**Administration (admin) user**: One default administration user is automatically created during a HADataC installation. This is the admin user who can pre-register new users and grant admin status to other registered users. A user is said to be a pre-registered if the user is included into the HADataC metadata repository and has not yet signed up.   

**Data owner**: Every registered user is considered a data owner, whether the user actually owns or not any data in the data repository. A data owner is capable of the following: uploading data and metadata into the system; recording deployment metadata; annotating data with metadata; setting the permission of who has the right of accessing their data; deleting their data from the system.  

**Guest user**: Every user is considered unregistered until the user logs into the system. Unregistered users can access and download publicly available data. Unregistered users cannot upload and own data in the HADataC system.

### 5.2.1. User Registration

#### Pre-Registration

Admin users should fill out the HASNetO agent's spreadsheet with the relevant information about HADataC users including the list of organizations associated with users and relationship between associated organizations. An admin user should upload the spreadsheet into the system by using the metadata loader, which will transfer all the agent information into the knowledge base. Agent information added into the system includes all the relevant user pre-registration information.

#### Full Registration

### 5.2.2. Authentication Backup and Recovery

Users having admin privilege can easily perform backup and recovery operations on user graph (e.g. user profiles, access levels, etc) and authentication (e.g. accounts, encrypted passwords, security roles, etc) when system upgrade necessitates this. To backup, go to the **Manage Users** page and then you will see an button called **Backup User Authentication** for exporting a **.json** file containing required information for recovering later, and another button called **Backup User Graph** for exporting a **.ttl** file containing the whole user graph. To recover, in the same page, use the file upload panel called **Load User Graph from turtle** first to upload the previously saved **.ttl** file for recovering the user graph and then use another file upload panel called **Load User Authentication from json** to upload the previously saved **.json** file for recovering the user authentication.

## 5.3. Data and Metadata Privacy

Every data point ingested into HADatAc has an owner. The user who uploaded the data is the owner of the data. The owner is responsible for assigning who can access the data, and can opt to share the data with other HADatAc users and even to make the data publicly available without any access restriction. It is also possible to share the data with _HADatAc users_ restricting data access to anyone who is registered with HADatAc.

Access to study-level information and corresponding static metadata is public. The decision of respecting an embargo period and/or making the data publicly available rest with data owners.

## 5.4. Data and Metadata Preservation

Data preservation along with their contextual knowledge provides a mechanism for data users to assess whether data have the qualities required for reuse. Moreover, the encoding of the contextual knowledge as metadata allows data users other them the ones responsible for acquiring and uploading in HADatAc to understand the very nature of each data point of a study. For instance, HADatAc searching and browsing mechanisms allows the following:

* to differentiate elicited data from measured data

* to identify the instruments used to measure/elicit the data (e.g., that a thermometer was used to measure the value “78”), the meaning of the quantities in terms of units (e.g., that the value is in “Fahrenheit”)

* to identify the element of interest behind measurements/elicitations (e.g., room’s air at a given location), and properties of interest from the element (e.g., dry bulb temperature).  

***

# 6. Projects Involved With HADatAc

* RPI/IBM/Fund-For-Lake-George's Jefferson Project on Lake George

* NIH-funded CHEAR 

* Gates Foundation-funded HBGDki

* RPI CASE Air Quality

* UNIFOR/City Of Fortaleza's Smart City Project

*** 

# 7. Other Products and Technologies Related to HADatAc

## 7.1. Data Journey (DJ)

## 7.2. MOCCASN





