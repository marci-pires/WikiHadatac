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

HADatAc associated/supporting ontologies provide the concepts required for the framework to acquire and manage scientific data. Those ontologies may be loaded straight from the web, or may be cached locally in case they need to be reloaded afterwards, when connectivity may be unavailable. 
  
Action:  To upload supporting ontologies, use options "Load cached ontologies" or "Load ontologies from the web" (http://localhost:9000/hadatac/ts/loadont?oper=init).

Verification (a):  verify message about loading supporting ontologies. All the ontologies should result in some triples being added to the triplestore. After loading the supporting ontologies: 19982 triples

    	Triples before [loadOntologies]: 0
		Triples after [loadOntologies]: 19982

Obs. The "user graph content" should have some triples. Those are the registration of your account with HADatAc.

Verification (b):  verify if supporting ontologies were loaded by querying the triplestore.  Go to blazegraph service / query menu and type the Sparql query: 

	select ?p ?o ?u where {?p ?o ?u . } 	

You should get 19982 triples as result. 

## 2.2.4. Uploading Domain Ontology From Labkey

## 2.2.5. Uploading Domain Ontology From File

## 2.2.6. Uploading Knowledge Base From Labkey