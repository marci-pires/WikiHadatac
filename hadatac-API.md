### All methods:

Response object has two fields:

isSuccessful: "true" or "false"

body: If isSuccessful is true, response contains the data/metadata for the API call, serialized as JSON. If isSuccessful is false, contains a plaintext error message.
See also the hadatac/utils/ApiUtil.java file

***

### Response getStudies()

Access at: /hadatac/api/studies/all

Returns all Study objects in hadatac


### Response getStudy(studyuri: String)

Access at /hadatac/api/studies/:studyuri

Given the URI of a study, returns the Study object matching that URI if it exists.

### Response getVariablesInStudy(studyuri: String)

Access at /hadatac/api/studies/variables/:studyuri

Given the URI of a study, returns the variables for which there are measurements in that study.
NOTE: If the study metadata has been ingested but no data acquisitions exist yet, then this will return 0 variables. This method checks SOLR for measurements first.

### Response getUnitsInStudy(studyuri: String)

Access at /hadatac/api/studies/units/:studyuri

Given the URI of a Study, returns the URI and label for all units of measure used in measurements in that study.
NOTE: If the study metadata has been ingested but no data acquisitions exist yet, then this will return 0 units. This method checks SOLR for measurements first.

### Response getOCListInStudy(studyuri: String)

Access at /hadatac/api/studies/objectcollections/:studyuri

Given the URI of a study, returns the URIs and types for all ObjectCollections in that study.

NOTE: The full ObjectCollection object is not returned, in order to avoid an oversized response body that also contains the objects themselves. For the contents of an ObjectCollection, use the below method

### Response getObjectsInCollection(ocuri: String, offset: Integer)

Access at /hadatac/api/objectcollections/:ocuri/:offset

Given the URI of an ObjectCollection and an offset number, returns the StudyObjects in that collection in pages of 250.

NOTE: For the first page, you must provide an offset of 0

NOTE2: Right now, the page size is hard-coded at 250. This can be adjusted as needed for performance.

### Response getVariable(variableuri: String)

Access at /hadatac/api/variables/:variableuri

Given the URI of a Variable, returns the DataAcqusisitionSchemaAttribute associated with that Variable.

### Response getOCSize(ocuri: String)

Access at /hadatac/api/objectcollections/size/:ocuri

Given the URI of an ObjectCollection, returns the size of that ObjectCollection. 

NOTE: If the collection is expected to exist but currently contains 0 objects, isSuccessful will return "true" with a body of "0". If no collection exists with that URI, then isSuccessful returns "false".

### Response getMeasurements(studyuri: String, variableuri: String)

Access at /hadatac/api/measurements/:studyuri/:variableuri

Given the URI of the study and variable, returns all relevant measurement values in Solr. Included fields: measurementuri, studyuri, studyobjecturi, variableuri, value, unituri.

### Response getIndicatorTypes()

Access at /hadatac/api/indicators/all

Returns the URIs for all indicator types included in all studies in hadatac.