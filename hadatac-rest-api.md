# HADatAc-REST-API

Users need to acquire a token inside of HADatAc to download metadata/data programmatically. Tokens provide the same level of access to HADatAc as the level of access of the user requesting the token.

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

