# 1. Installing HADatAc

HADatAc can be installed for _development_ purposes, or for _production_ purposes. When installed for development, HADatAc does not require the setting of an email service since just one user with full access to the system is created. When installed for production, HADatAc requires access to an email service so that new users and access levels can be created and users can be authenticated through an email verification process.

## 1.1. On Linux (Production)

## 1.2. On Linux (Development)

## 1.3. On MacOS (Development)

## 1.4. Using Docker

***

# 2. Setting Up HADatAc

HADatAc need to be configured so that it can access its corresponding repositories. Lets assume that "/data/hadatac/" is the folder where HADatAc is installed, in this case, configuration files are located at "/data/hadatac/conf". 

Use these [configuration instructions](https://github.com/paulopinheiro1234/hadatac/wiki/Setting-up-HADatAc-Configuration)  to set up HADatAc.

***

# 3. Concepts

## 3.1. Content Upload

Static Metadata

Dynamic Metadata

Scientific Data

## 3.2. Content Ingestion

***

# 4. Using the Web Console

## 4.1. Data Upload

We call _data uploading_  the process of adding content into the data repository, and _data ingestion_ the process of collecting, organizing, indexing content's metadata, and as important, the process of connecting the newly organized metadata to the content. 

Using traditional databases developers are requires to develop one very large schema to manage both the data content and its associated metadata, and to make sure that content identifiers and corresponding metadata are properly connected.	 
The use of ontologies to guide the process of organizing metadata alleviates the task of organizing the metadata since the data becomes self-organizing when values are tagged with terms from a common set of ontologies. Furthermore, ontologies also help the process of logically connecting data to newly created graphs inside of the metadata repository.

The screenshot above shows how data files can be uploaded into HADatAc in ways very similar to other well established cloud-based online repositories like Dropbox and Google drive. For instance, the “DA-CBIS-Feb-2017-DMG-B-3.csv” file, which is a data file, was uploaded into the infrastructure and now it is assigned to a user who can leave the datafile there or may decide to share, download or even delete the file. 

Once files are uploaded, they can either be automatically ingested in case the infrastructure’s knowledge base knows how to process the file, or may guide scientists in the process of telling the system how to ingest the data. 

## 4.2. Data Preparation and Ingestion

## 4.3. Data Search

The screenshot above shows HADatAc’s Data Faceted Search where users go to select interactively select and download HADatAc content for analysis, including the possibility of data owners sharing their data with other users. 

We observe that scientific images would take central stage in the faceted search with image metadata being used to play multiple roles during the process of selecting and downloading images from the image repository. 

**Facet Panel**: Each property of images can be used as facets, where the actual selection of a facet is the selection of one or more possible values for each image. For instance, images may be selected by its source (a study, an image collection), by physical characteristics of the entities the image is from (part of a body, presence of some feature, known disease), by the instruments generating the images (e.g., MRI, CAT Scan), and so on.

**Scientific Data Panel**: It provides a preview of the images to be downloaded providing some contextual data like the IDs of the subjects and/or samples, temporal and spatial information.

**Detail Panels**: It provides more in-depth explanation about information that can be found on the facets and in the Scientific Data Panel, and such detailed information may contain links to actual external documents that enable a quick investigation from users on whether the current selection of the search corresponds to the actual data to downloaded from the repository of if further refinement/relaxation of the selection criteria is necessary.
Data Faceted Search

[Metadata Browser](https://github.com/paulopinheiro1234/hadatac/wiki/HADataC-User-Guide:--Metadata-Browser)
 
Metadata management including HASNetO-Loader (also available for batch execution)


## 4.4. Data Download

***

# 5. Architecture

## 5.1. Interactive Web Console functionalities

## 5.2. Batch automated functionalities

[Data management](https://github.com/paulopinheiro1234/hadatac/wiki/HADataC-User-Guide:--Data-Management) including HADataC-Loader (also available for batch execution)

## 5.3. Embedded SOLR repository

## 5.4. Embedded Triple Store repository

# 6. Data Governance

HADatAc Users

Data and Metadata Privacy

Data and Metadata Preservation


# 7. Using Other HADataC Products

MOCCASN

