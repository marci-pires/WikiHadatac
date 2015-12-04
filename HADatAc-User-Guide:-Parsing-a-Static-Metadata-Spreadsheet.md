### How To Parse
To Parse data from a csv do the following:
 1.	From HADatAc portal page select “Metadata Browser” from black top menu bar to navigate to the Metadata Browser page.
 2.	Choose “Create CCSV from CSV” from the “Data Upload” Menu.
 3.	Note: A CCSV is a contextualized common separated value.  This command takes a spreadsheet saved in CSV format and converts it to CCSV. 
 4.	The CSV Annotator opens
 5.	Step 1: Select Current Deployments. Choose from deployment that you want to add the csv data to. Deployments will have a Platform, Instrument, a Start Time and Operation.
 6.	Step 2:  (tbc)
 7.	Step 3: (tbc)
 8.	From the “Metadata Browser choose “Upload CCSV” from the Data Upload Menu. 
 9.	Select “Choose File”
 10.	Navigate to your CCSV file you want to upload and select “open”
 11.	A message appears asking ”if you are sure you want to load and index this file into the measurements repository?” Select “Confirm”.

### What Happens When Everything is Right
1.	If it is successfully loaded you will receive a message that the file has been loaded with date and time the file was loaded.
2.	Select “ok”

### How Do I know If Something Is Wrong and Where Is the Error?
When you upload the CCSV if you receive errors the problem is most likely with the data in the csv. See the "How to Fix it?" section below. 

### How to Fix It?
Make sure to check the following in your spreadsheet:
 1.	For everything that has a URI (“hasURI”) i.e. platforms, instrument models, instruments, detector models, detectors, sensing perspective, entities, characteristics, agents, make sure that it has indicated the correct URI linking it to its parent URI.
 2.	The collection of measurements under the metadata ‘characteristics’ should identify the ontology it is a sub-class of (“rdfs:subClassOf”), this name should be one word and should not have any spaces.
 3.	Agents: the identification of Agents in the spreadsheet should show the first and last name of a person. Make sure the assigned URI (“hasURI”) for each person or organization shows the name (first and last) without any spaces. Check hyphenated names in the assigned URI name as this can also cause errors. You may remove the hyphenation to solve this. 