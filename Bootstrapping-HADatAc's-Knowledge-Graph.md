## 2.2.1. HADatAc's Knowledge Graph

> **No data is expected to be properly ingested in HADatAc if its Knowledge Graph is not properly constructed**

HADatAc's Knowledge Graph is composed of the content inside both the data repository (SOLR) and the metadata repository (Blazegraph). The so-called __Bootstrapping process__, which is entirely described in this Section 2.2.1, entirely erases any data and metadata content inside of HADatAc (only information about users is preserved). No bootstrapping should occur on HADatAc instance that has already been bootstrapped. 

## 2.2.2. Erase Data and Metadata Repositories 
 
Clearing the data before beginning the ingestion process of datasets is one way to ensure the exact control over the contents of HADatAc's repositories. 

Action: Clean repositories
  http://localhost:9000/hadatac/ts/clean?oper=init 

Verification:  After cleaning the Data Repository and Metadata Repository, they should be like this:

    Status: OPERATIONAL 
    Data Acquisitions: 0 documents. Data Content: 0 documents. 

    Status: OPERATIONAL 
    Metadata Content: 0 triples. User Graph Content: 0 triples.

## 2.2.3. Uploading Supporting Ontologies

HADatAc associated/supporting ontologies provide the concepts required for the framework to acquire and manage scientific data. Those ontologies may be loaded straight from the web, or may be cached locally in case they need to be reloaded afterward, when connectivity may be unavailable. 
  
Action:  To upload supporting ontologies, use options "Load cached ontologies" or "Load ontologies from the web" (http://localhost:9000/hadatac/ts/loadont?oper=init).

Verification (a):  verify message about loading supporting ontologies. All the ontologies should result in some triples being added to the triplestore. After loading the supporting ontologies: 19982 triples (numbers will vary as the case may be.)

	Triples before [loadOntologies]: 0
	Triples after [loadOntologies]: 19982

Obs. The "user graph content" should have some triples. Those are the registration of your account with HADatAc.

Verification (b):  verify if supporting ontologies were loaded by querying the triplestore.  Go to blazegraph service / query menu and type the Sparql query: 

	select ?p ?o ?u where {?p ?o ?u . } 	

You should get 19982 triples as result. 

## 2.2.4. Uploading Domain Ontology

Action: Now you need to "Load Ontology from Labkey". Hadatac will ask for your username and password in labkey.  Then you click on "view" on your specific labkey folder. 

Click on "Batch Loading Concepts" button. 

Note that you have two options to upload the main ontology: (a) to use labkey to feed your main ontology ("Load Ontology from LabKey"), or (b) to upload an ontology itself by using the "Upload Additional Knowledge".

A brief note about LabKey: The labkey contains a copy of Hadatac's KG status in the form of tables. Each table is either a concept table or an instance table. The first column of each table is always a hasUri. The second column is either a rdfs: subclassOf or a rdf: type (represented in RDF also by an 'a'). If the second column is a rdfs: subclassOf, then the table is for concepts, otherwise it is for instances. The concept table set represents the "ontology" that is loaded from Labkey. The set of instance tables are all instances of Hadatac. KG is the set of ontology + instances.

Verification: verify message about loading main ontology 

Verification: verify if main ontology was loaded by querying the triplestore. Go to blazegraph service / query menu and type the Sparql query: select ?p ?o ?u where {?p ?o ?u . } 	 You should get 24723 triples as result. 

Triples before loading from LABKEY: 19982
Triples after [loading from LABKEY]: 24723   

## 2.2.5. Uploading Knowledge Base

Action: Now you need to "Load Knowledge from Labkey". Hadatac will ask for your username and password in labkey. Then you click on "view" on your specific labkey folder.  Click on "Select All" checkbox. 

Click on "Batch Loading Selected Instance Data" button. 

Triples before loading from LABKEY: 24723
Triples after [loading from LABKEY]: 36420   

Msg: Operation [load] complete -- check the results above to see if the parsing of the facts was successful.
