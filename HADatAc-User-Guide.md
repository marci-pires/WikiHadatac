# Getting Started

[Section 3](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#3-using-hadatac) provides a set instruction on how to use HADatAc once HADatAc is ready to be use. This set of instructions progress from understanding its initial page to uploading data and metadata to searching the data to eventually selecting and downloading the data. But before one can actually use the app, one needs to install HADatAc, according to [Section 1](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#1-installing-hadatac), and set it up, according to [Section 2](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#2-setting-up-hadatac).

We strongly recommend starting with a development version of HADatAc that can run on either [Linux](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#12-on-linux-development) or [MacOS](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide#13-on-macos-development).

# 1. Installing HADatAc

HADatAc can be installed for _development_ purposes, or for _production_ purposes. When installed for development, HADatAc does not require the setting of an email service since just one user with full access to the system is created. When installed for production, HADatAc requires access to an email service so that new users and access levels can be created and users can be authenticated through an email verification process.

## 1.1. On Linux (Production)

[This section](https://github.com/paulopinheiro1234/hadatac/wiki/1.1.-Installing-for-Linux-(Production)) provides the installation instructions for HADatAc on Linux. This PRODUCTION installation is based on a distribution package and requires comprehensive configuration of the app including connection to an emailer. Production installation is required when the installation is expected to be **used by multiple users**, and the app is **regularly upgraded** by an upgrade script.

## 1.2. On Linux (Development)

[This section](https://github.com/paulopinheiro1234/hadatac/wiki/1.2.-Installing-for-Linux-(Developer)) provides installation instructions for HADatAc on Linux. This DEVELOPMENT installation is much simpler than the production installation but is designed to allow just one main user to use the system. In this version, you work from a folder in your local filesystem that is connected to git.  

## 1.3. On MacOS (Development)

[This section](https://github.com/paulopinheiro1234/hadatac/wiki/1.3.-Installing-for-MacOS-(OSX)) provides installation instructions for HADatAc on MacOS (OSX). This DEVELOPMENT installation is designed to allow just one main user to use the system. In this version, you work from a folder in your local filesystem that is connected to git.  

***

# 2. Setting Up HADatAc

## 2.1. Software Configuration

Correct configuration is required for HADatAc to access its repositories, the ontology repository, to connect to users through email, to adjust to operating system requirements, etc. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/Setting-up-HADatAc-Configuration) describes the many configuration files of HADatAc and how they may be used.

## 2.2. Knowledge Graph Bootstrap

HADatAc's Knowledge Graph (KG) is the main element allowing the app to manage files and their content. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/Bootstrapping-HADatAc's-Knowledge-Graph) describes the KG's boostrapping process required to initiate the KG. HADatAc should be ready to be used after its software components have been installed (Section 1), the main software components has been configured (Section 2.1), and its knowledge graph has been bootstrapped (Section 2.2).

***

# 3. Using HADatAc

## 3.1. Initial Page

[This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.1.-Initial-Page) describes the organization and functionalities available on its main page.

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

HADatAc's data faceted search is the mechanism to understand at harmonized value-level, what is the actual overall content of the framework, and of selecting this content across studies and instruments. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.5.-Data-Search) describes how to understand available content, and to select the content for eventual downloads.

## 3.6. Metadata Browser and Search

Metadata stored in HADatAc can be browsed and searched through the app. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.6.-Metadata-Browser-and-Search) describes these capabilities in detail. 

## 3.7. API 

Data and metadata stored in HADAtAc can also be retrieved programmatically. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/3.7.-API) describes a list of RESTful services, which compose the __Tetherless World Knowledge Exchange API__. Data visualization frameworks, visual analytical frameworks and dashboards with a back end HADatAc support are expected to use the API to retrieve content from the app.  

## 3.8. Data Download

***

# 4. Architecture

## 4.1. Software Components

HADatAc is implemented as a web application. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/4.1.-Software-Components) describe how the main website is built in terms of software components. The section also describe what data repositories are used for managing data and metadata content, and what infrastructure(s) is/are used to manage evolving ontologies.  

## 4.2. Knowledge Components

HADatAc's knowledge graph is composed by a collection of ontologies, a knowledge base with many instances of concepts defined in the ontologies, and data values semantically annotated to concepts and their instances. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/4.2.-Knowledge-Components) describes these core ontologies, how they are organized, and how their concepts are connected. 

***

# 5. Data Governance

## 5.1. Access Network

 Communities of data users behind each HADatAc installation have their own rules on who can do what in terms of accessing, using and managing data. HADatAc uses an access network to capture and enforce these rules. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/5.1.-Access-Network) provides the instructions for a HADatAc administrator to build and maintain an access network.

## 5.2. User Status, Categories and Access Permissions

Different users may have different permissions according to their roles (categories) and their current standing in terms of being registered or not with a HADatAc instance. [This section](https://github.com/paulopinheiro1234/hadatac/wiki/5.2.-User-Status,-Categories-and-Access-Permissions) describes the possible status and categories of users, how they are pre-registered, and how they are granted access permissions.

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





