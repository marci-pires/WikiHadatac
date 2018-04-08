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

## 2.1. Software Configuration

HADatAc needs to have a correct configuration to access its repositories. Let assume that "/data/hadatac/" is the folder where HADatAc is installed, in this case, configuration files are located at "/data/hadatac/conf". 

Use these [configuration instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Setting-up-HADatAc-Configuration)  to set up HADatAc.

## 2.2. Knowledge Graph Bootstrap

HADatAc can only process data if its supporting knowledge graph has the correct knowledge added to its knowledge base. Use the [bootstrapping instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Bootstrapping-HADatAc's-Knowledge-Graph) to initiate HADatAc's knowledge graph.  

HADatAc should be ready to be used after its software components have been installed (Section 1), the main software components has been configured (Section 2.1), and its knowledge graph has been bootstrapped (Section 2.2).

***

# 3. Using HADatAc

## 3.1. Initial Page

The main page is composed of two or three vertical blocks of functionalities (three blocks if the user is an administrator). The first block has the functionalities required for a user to search and retrieve content from HADatAc. The second block has the functionalities required to update and maintain content in HADatAc. The third block has the functionalities required for managing underlying knowledge as described in Section 3.6 of this User Guide.  

## 3.2. File Upload

File Upload is used as an initial stage for feeding content into HADatAc. HADatAc content can be composed of data files (starting with a **DA** prefix) or metadata files (staring with any of the following prefixes: **STD**, **SSD**, **PID**, **SID**, **MAP**, **ACQ**, **OAS**, or **SDD**). [This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.2.-File-Upload) describes how to manually upload any file into HADatAc, making the file locally available for ingestion as described in Section 3.3. for data files and Section 3.4 for metadata files.

## 3.3. Data Preparation and Ingestion

Once data files are uploaded into HADatAc, they are going to stay in the unprocessed folder of HADatAc until the application has information enough to ingest the file's content (i.e., parse, annotate and copy the file's content into appropriate data and metadata repositories). [This section]() describes how to manually provide HADatAc the information needed for the application to be able to ingest the file's content.

For automated preparation of data file's ingestion, please consider the use of the OAS metadata file described in Section 3.4.

## 3.4. Metadata Ingest

Metadata content is added into HADatAc through the use of online forms or through the uploading and ingestion of content files. Content files can further be added manually or automatically.  

### 3.4.1. Inserting Metadata Content Manually

[This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.4.-Metadata-Ingest#341-inserting-metadata-content-manually) describes how to use on-line forms to add/edit metadata content into HADatAc including description of studies, study objects, semantic study designs and semantic data dictionaries.

### 3.4.2. inserting Metadata Content Automatically

[This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.4.-Metadata-Ingest#342-inserting-metadata-content-automatically) describes how to construct and submit templates to add metadata content into HADatAc including description of studies, study objects, semantic study designs and semantic data dictionaries. These templates are used in lieu of on-line forms since they can be automatically fed and processed into HADatAc. 

## 3.5. Data Search

The screenshot above shows HADatAc’s Data Faceted Search where users go to select interactively select and download HADatAc content for analysis, including the possibility of data owners sharing their data with other users. 

**Facet Panel**: Each property of data can be used as facets, where the actual selection of a facet is the selection of one or more possible values for each data point. For instance, data may be selected by its source (a study, a data file), by physical characteristics of entities that the data is from (part of a body, presence of some feature, known disease), by the instruments generating the data (e.g., MRI, mass spectrometer, thermometer), and so on.

**Scientific Data Panel**: It provides a preview of data to be downloaded providing some contextual information like the IDs of the subjects and/or samples, temporal and spatial information.

**Detail Panels**: It provides more in-depth explanation about information that can be found on the facets and in the Scientific Data Panel, and such detailed information may contain links to actual external documents that enable a quick investigation from users on whether the current selection of the search corresponds to the actual data to downloaded from the repository of if further refinement/relaxation of the selection criteria is necessary.
Data Faceted Search

## 3.6. Metadata Browser and Search

Metadata stored in HADatAc can be browsed and searched through the app. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.6.-Metadata-Browser-and-Search) describes these capabilities in detail. 

## 3.7. API 

Data and metadata stored in HADAtAc can also be retrieved programmatically. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.7.-API) describes a list of RESTful services, which compose the __Tetherless World Knowledge Exchange API__. Data visualization frameworks, visual analytical frameworks and dashboards with a back end HADatAc support are expected to use the API to retrieve content from the app.  

## 3.8. Data Download

***

# 4. Architecture

## 4.1. Software Components

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec4/architecture.png)

HADatAc has a web-based application and an underlying content repository infrastructure. The web-based application is used to manage data security and privacy, to delete and archive existing repository content, to upload new content into the repository, and to provide multiple ways of searching for data and metadata with the use of a collection of faceted searches.  

HADatAc content repository infrastructure is organized as follows:

* Data are stored in Apache SOLR instances, which are highly-scalable no-SQL solutions for managing unstructured, semi-structured and structured data;  

* Metadata are stored in SOLR instances as a knowledge graph, and managed with the use of a Apache JENA-based API. HADatAc may also be based on any other SPARQL-based knowledge graph repository since RESTful SPARQL queries are the way for the web application to communicate with the underlying RDF repository.  
Metadata stored in HADatAc is composed of concepts and instances, also known as objects. Concepts come from ontologies published on the web and objects, which are concept instances, come from LabKey, which is an open-source, web-based Laboratory Information Management System (LIMS). A combination of concepts and instances related to some scientific activities, e.g., a study, can be described as the knowledge graph of those activities, Thus, HADatAc uses LabKey as its preferred way of inputting and editing knowledge graphs.

After respecting security and privacy policies in place, HADatAc allows advanced users to access data in SOLR with the use of Lucene queries, and to access metadata in SOLR with the use of SPARQL queries. 

## 4.2. Knowledge Components

### 4.2.1. On the use of URIs

### 4.2.2. The Human-Aware Science Ontology (HAScO)

#### Supporting Ontologies

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





