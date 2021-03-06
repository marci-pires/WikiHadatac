# 3.2 - Manage Data File Ingestion

_Data/Metadata ingestion_ is a combined two-step process of \(step 1\) uploading data/metadata files into the infrastructure's filesystem, and \(step 2\) moving files that are in the infrastructure's filesystem into the infrastructure's databases.

Only files that are in CSV or Excel formats can be submitted for ingestion into HADatAc \(there is a plan for HADatAc to support more data formats in the future\). In addition to the format requirement, files also need to meet one of following criteria to be ingested into HADatAc:

* file's name starts with "DPL-" and file conforms with DPL structure described in \[Section 5.1.\]\([https://github.com/paulopinheiro1234/hadatac/wiki/5.1.-Deployment-Specification-\(DPL](https://github.com/paulopinheiro1234/hadatac/wiki/5.1.-Deployment-Specification-%28DPL)\)\), or   
* file's name starts with "STD-" and file conforms with STD structure described in \[Section 5.2.\]\([https://github.com/paulopinheiro1234/hadatac/wiki/5.2.-Study-Specification-\(STD](https://github.com/paulopinheiro1234/hadatac/wiki/5.2.-Study-Specification-%28STD)\)\), or
* file's name starts with "SSD-" and file conforms with SSD structure described in \[Section 5.3.\]\([https://github.com/paulopinheiro1234/hadatac/wiki/5.3.-Semantic-Study-Design-\(SSD](https://github.com/paulopinheiro1234/hadatac/wiki/5.3.-Semantic-Study-Design-%28SSD)\)\), or  
* file's name starts with "SDD-" and file conforms with SDD structure described in \[Section 5.4.\]\([https://github.com/paulopinheiro1234/hadatac/wiki/5.4.-Semantic-Data-Dictionary-\(SDD](https://github.com/paulopinheiro1234/hadatac/wiki/5.4.-Semantic-Data-Dictionary-%28SDD)\)\), or  
* file's name starts with "STR-" and file conforms with STR structure described in \[Section 5.5.\]\([https://github.com/paulopinheiro1234/hadatac/wiki/5.5.-Stream-Specification-\(STR](https://github.com/paulopinheiro1234/hadatac/wiki/5.5.-Stream-Specification-%28STR)\)\), or   
* file's name starts with "DA-" and file is associated with an existing data stream, or
* file's name starts with "DOI-" and file is used to annotate DOI references related to DA files.

## 3.2.1. Ingesting Study Content

In this section we describe the process of organizing the data and metadata files of a study and putting them in the order required for them to be ingested. The actual process of ingesting each individual file is described in [Section 3.2.2](https://github.com/paulopinheiro1234/hadatac/wiki/3.2.-Manage-Data-File-Ingestion#322-manual-submission-of-data-file-for-ingestion).

The final goal of ingesting the content of a study is to get the data of the study ingested. Study data can be fed into HADatAc either through a collection of data files \(DA files\), a collection of message streams, or a combination of data files and message streams.

The blue box in the diagram below shows the categories of metadata files required to ingest the data fed through message streams. The grey box in the diagram below \(which includes everything inside of the blue box\) shows the categories of metadata files required to ingest the data fed through data files.

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec3/StudyMetadataFiles.png)

Each white box in the diagram corresponds to one file category. The arrows connecting the white boxes show how one file category relies on another file category. For example, an SSD file can only be ingested after its corresponding STD file has been ingested, and a DA file can only be ingested when its corresponding STR files have also been ingested. In that way, we can see, for example, that STD, SDD, and DPL files can be ingested at any time, since they do not depend on other metadata files. We also see that an STR file can only be ingested after its corresponding SSD, SDD, and DPL files have been ingested.

From the diagram, we see that the process of ingesting study content needs to respect a partial order on how files are ingested. The order is said to be partial because it does not matter if, for example, SDDs are loaded before DPLs as long as all that is required for the ingestion of an STR file \(e.g., its SSD, SDDs, and DPL files\) are ingested before an STR file is submitted for ingestion.

Note that every study must have one STD file and one SSD file.

Note that SDD files and DPL files are not study specific. This means that, for example, one DPL can support multiple studies. The same is also true that one SDD can support multiple studies.

For the ingestion of any given DA file, the ingestion of all the following is required:

* one STD file
* one SSD file
* one or more SDD files
* one or more DPL files, and
* one or more STR files. 

  To keep things simple, we suggest that during the process of ingesting study content, when SDD files are ingested, all the SDD files for that study are ingested one after the other. The same suggestion is valid for DPL and STR files.

Finally, and optional DOI file may be used to annotate the Digital Object Identifier \(DOI\) that was used to derive the data in a DA file, if any. This file can only be submitted for ingestion after the DA files have been ingested.

## 3.2.2. Manual submission of data files for ingestion

Data and metadata file upload \(Manual data file upload\) is done by going to **Home &gt; Ingest Files**.

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec3/DatafileManagement.png)

The screenshot above shows the **Ingest Files** user interface, which includes three distinct areas:

* the **drop file area** \(the gray box\)
* the **processed files area** \(right below the drop file area\), and
* the **unprocessed files area** \(below the processed files area\)

Files are manually submitted for ingestion by dragging the files and dropping them into the drop file area. Once files are uploaded, they will show up in the unprocessed files folder. For instance, the **DA-CBIS-Feb-2017-DMG-B-3.csv** in the image above was uploaded into HADatAc and is waiting to be processed.

A file is selected for processing and is matched against an existing file stream. Otherwise, the file will be unprocessed until either the file is manually removed or a file stream is created for the file.

* If files are **matched against existing file streams**, the ingestion of the file starts automatically.
* If files are **not matched against existing streams**, the association of the file to a stream needs to be done manually, and it may require the creation of a new stream for the file. The manual process of assigning a file to a data stream is described below.

### 3.2.2.1. Data File Preparation

**Note**: In most projects, it is uncommon for files to not match existing file streams. Thus, the use of the data file preparation process described here is not typical.

The Data Preparation button next to a newly uploaded DA-\* file becomes available when there is no stream available to process the file. In this case, the **Data Preparation** button should be selected and the form needs to be completed. The following image shows the Data Preparation's online form.

![](https://raw.githubusercontent.com/paulopinheiro1234/hadatac-screenshots/master/Sec3/DataPreparation.png)

#### 3.2.2.1.1. Data File's Associated Elements

The Data Preparation Form is a workflow for acquiring the metadata required for ingesting the data. For instance, under the current configuration of this specific repository, a data file may be associated with the following:

* A Study associated with the data file of concern. This is often the study that originally funded the effort of acquiring the data, which may include the acquisition and deployment of instruments, the execution of simulation models, and the effort of conducting questionnaires with human subjects.
* Object\(s\) and/or object collection\(s\) associated with the values included in the data file of concern.
* An associated deployment describing the instruments and sensors used to acquire the data, as well as the exact conditions in which the instruments where deployed, e.g., associated _standard operating procedure_.
* An associated Semantic Data Dictionary describing how the contents of the data file are going to be parsed and semantically annotated in terms of attributes and units.

#### 3.2.2.1.2. Workflow

The process of filling up this form consists of either selecting an existing Stream or identifying all the associated elements. The option of selecting an existing Stream is the first one on the top of the form under "Select Complete and Active Data Acquisition".

If no Stream is suitable for the file to be ingested, then it becomes required to fill out the rest of the form. Selected elements are already shown. Combo box with values are available for existing elements that have not been selected yet. In the screenshot above, we see that the associated object\(s\)/object collection\(s\) is the only element that has not been selected yet.

Once associated elements have been identified, the green **Confirm Complete** button next to the name of the file becomes enabled. By selecting the button, the user confirms that the file is ready for ingestion, which will eventually result in the infrastructure trying to ingest the data file's content.

#### 3.2.2.1.3. Data Ingestion Error Messages

TBD

## 3.2.3. Automatic submission of data file for ingestion

The process of submitting files for HADatAc ingestion can be accomplished programatically.

* the code or script responsible for submitting new data files into HADatAc needs to have permission to write files into the **unprocessed\_csv** folder of HADatAc    
  * The exact location of **unprocessed\_csv** folder is defined in the autoccsv.config file \(as described in [Section 2.1.4](https://github.com/paulopinheiro1234/hadatac/wiki/2.1.-Software-Configuration#214-setting-up-autoccsvconfig)\)  

If the file being submitted is a DPL, STD, SSD, or SDD file, it will be ingested automatically once the code writes the file into **unprocessed\_CSV**. Otherwise, all the following need to occur:

* a data stream for the file needs to exit at the time the file is submitted \([Section 3.4.5.](https://github.com/paulopinheiro1234/hadatac/wiki/3.4.5.-Manage-Streams) describes how streams are created\)   
* the initial part of the name of the file being loaded needs to match the pattern name of the stream \(\[Section 5.4.1.\]\([https://github.com/paulopinheiro1234/hadatac/wiki/5.5.-Stream-Specification-\(STR\)\#551-stream-elements](https://github.com/paulopinheiro1234/hadatac/wiki/5.5.-Stream-Specification-%28STR%29#551-stream-elements)\) describes how the stream's pattern name is specified\)

## 3.2.4. Data File Operations

Every file in the data file ingestion filesystem is assumed to be ready for ingestion \(when files are in the unprocessed folder\), or has already been ingested \(when files are in processed folder\). Files are highlighted in red if any error is identified during ingestion. Files are highlighted in yellow if any warning condition is identified during the ingestion.

* **Preview File** : Whenever possible, it will open the file in an application that will allow the inspection of the file content.  
* **Move to Unprocessed Folder** : It will remove any content from the file that has been added to any HADAtaAc content  repository, and will move the file to the unprocessed folder. If no action is taken, the file will re re-ingest. This is a very useful operation when testing a new feature implemented as part of the ingestion of a file of a given type.    
* **Delete** : It will remove any content from the file that has been added to any HADatAc content repository, and remove the file from HADatAc.  
* **Assign Acquisition** : A data acquisition can be assigned/reassigned.   
* **Assign Owner** : The email of the owner of the data file can be assigned/reassigned, which is a way of changing the ownership of a file once it has been uploaded into HADatAc.   
* **Logs** : Display the log of the file's ingestion into the system. Error and warning messages are shown inside of this log.   
* **Download** : Download file from HADatAc into local computer.

