Users need to acquire a token inside of HADatAc to download metadata/data programmatically. Tokens are created for the user asking for a token. 

## List of Studies

/hadatac/apiStudy/download

* input: token
* output: list of study URIs and Study names

## List of Study's Variables

/hadatac/apiStudyVariable/download

* input: token, study URI
* output: list of variable URIs and Variable names

## List of Study Variable's Values

/hadatac/apiStudyVariableData/download

* input: token, study URI, variable URI
* output: list of variable values
