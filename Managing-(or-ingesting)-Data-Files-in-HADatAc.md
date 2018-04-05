By using HADatAc on the menu entry “Manage Data Files”, we usually process the following files in order:
1. STD
1. PID (after STD (if any))
1. SID (after STD (if any))  
1. MAP (after PID and SID files are loaded) 
1. SDD (any time before ACQ, even before STD) 
1. ACQ (after STD, PID, SID, MAP (if any), SDD)
1. DA (after ACQ)

Note: after clicking on “Manage Data Files”, and before starting the ingestion process you might need to click "Start Auto-Annotator" button, on the top of the screen.

#### 1. Load STD file for a given testing study

	Verification: Go to "home" > "manage studies" and inspect the list of studies and look for an entry for the study in STD.

#### 2. Load PID file for same STD, if any

PID files are used to include an object collection of subjects inside of a given study.

	Verification: Go to "home" > "manage studies". Inspect the list of studies and look for an entry for the study in STD. On the study entry, verify that “#OCs” is greater than “0”  (zero). If so, select “objects” in the entry.
From the list of entries, verify if one of them is named “Study Population (...)” and that the number of objects in the object collection corresponds to the number of subjects in the PID file


#### 3. Load  SID file for same STD, if any

SID files are used to include an object collection of samples inside of a given study.

	Verification:  Go to home > manage studies. Inspect the list of studies and look for an entry for the study in STD. On the study entry, verify that “#OCs” is greater than “0”  (zero). If so, select “objects” in the entry. From the list of entries, verify if one of them is named “Sample Collection (...)” and that the number of objects in the object collection corresponds to the number of samples in the SID file.

	Verification: Visualize study in “Study Management” and verify if object collection “Sample” was created and populated accordingly.

#### 4. Load MAP file for same PIDs and SIDs, 

	Verification: Go to home > Search Study. Select the study of interest (please note that you may need to press the “update” button on the top-left part of the screen to update the list of studies). Select “samples” and verify that samples are connected to subjects, if there is a case for SIDs to be connected to PIDs.

#### 5. Load SSD files for each kind of data acquisition 

(i.e., EPI data, LAB data) that is going to be ingested under current study

	Verification: Visualize study to verify 9, 10, 11 and 12

#### 6. Load EPI files (ACQ-EPI file)

	Verification: perform a faceted search to verify 14

#### 7. Load LAB file (ACQ-LAB file) 

	Verification: perform a faceted search to verify 16

#### 8. Load the DA file

Data Preparation and Ingestion

	Verification: When processing the DA files, you need to confirm the ingestion is ready by going to the prepare ingestion page.

Once files are uploaded, they can either be automatically ingested in case the infrastructure’s knowledge base knows how to process the file, or may guide scientists in the process of telling the system how to ingest the data.

