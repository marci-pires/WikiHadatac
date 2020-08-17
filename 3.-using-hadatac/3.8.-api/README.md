# 3.8.-API

All API interfaces support authentication. If an API user does not supply credentials, they will only see the data and metadata visible to public users. If they are authenticated, they see only the data and metadata that is visible to that user, which can be a much smaller subset of the entire data and metadata collection.

## 3.8.1. Object Definitions

**Study**

* uri - The unique URI that identifies this study and can be used in queries for measurement data \(e.g. "[https://hadatac.org/kb/hbgd\#STD-AMANHI](https://hadatac.org/kb/hbgd#STD-AMANHI)"\)  
* label\_short - A short label that identifies this study \(e.g. "AMANHI"\)  
* label\_long - A longer label for the study \(e.g. "Alliance for Maternal and Newborn Health Improvement"\)  
* location\_uris - Array containing the URIs of all locations related to this study.  
* question\_uris - Array containing the URIs of all questions related to this study.  
* variable\_uris - Array containing the URIs of all variables that this study has some sort of measurement data for.  
* subject\_uris - Array containing the URIs of all subjects that were in this study.  

**Variable**  
This is what we are calling anything for which measurement data is available. Things like height for age z-score \(HAZ\), etc.

* uri  
* label\_short  
* label\_long  
* unit\_uri - URI for the unit that describes how this variable was measured.  

**Deployment**  
A deployment occurs when an instrument is placed on a platform and is ready to acquire data

* uri  
* platform - URI for the platform where the instrument is placed
* instrument  - URI for the instrument being placed

**Subject** A subject in the study for which measurements of variables were made.

* uri  
* id - The identifier used for this subject in the study.  

**Location** A place in the world where a study took place or even locations of individual subjects.

* uri  
* label\_short  
* label\_long  

**Question**  
A question addressed by the study \(e.g. How does body composition differ by sex, ethnicity, and region? From HBGDki data.\)  
uri

* label\_long  
* label\_short  

**Unit**  
The unit used for measuring a particular variable.

* uri   
* label\_short - String containing the units.  

**Platform**  
A location that enables operating instruments. For platforms with associated field of view, field of view metadata is retrieved along with platform metadata.

* uri 
* label - name of platform
* coord1 - the value of the first coordinate
* coord1Unit - the unit of the first coordinate
* coord1Char - the type of the coordinate, e.g., latitude or Xcoodinate in a cartesian system
* coord2
* coord2Unit
* coord2Char
* coord3
* coord3Unit
* coord3Char
* refLayout - the URI of a platform with the reference layout for coord1, coord2 and coord3
* layout- the layout of the platform, if any
* layoutWidth - the width of the bounding 3D box for the layout
* layoutWidthUnit
* layoutDepth
* layoutDepthUnit
* layoutHeight
* layoutHeightUnit
* partOf - the URI of an immediate super-platform, if any
* fovgeometry - the 3d shape of the field of view 
* fovparam1
* fovparam1Unit
* fovparam1Char
* fovparam2
* fovparam2Unit
* fovparam2Char
* fovparam3
* fovparam3Unit
* fovparam3Char

**Field of View**

* uri
* label
* geometry - the 3d shape of the field of view 
* platform\_uri - URI of associated platform
* param1
* param1Unit
* param1Char
* param2
* param2Unit
* param2Char
* param3
* param3Unit
* param3Char

## 3.8.2. API Calls

### 3.8.2.1. Where to Post API Calls

Lets assume that your HADatAc instance is hosted at "[http://example.com](http://example.com)". In this case, your HADatAc is expected to be available at "[http://example.com/hadatac](http://example.com/hadatac)" and your api at "[http://example/hadatac/api](http://example/hadatac/api)".

By going to "[http://example/hadatac/api](http://example/hadatac/api)" you are still not going to get any data back because you need to select an API Call. For example, **studies/all** is a valid API Call that returns a list of all the studies registered in your HADatAc instance. In this case, the complete URI to use for the **studies/all** call should be "[http://example/hadatac/api/studies/all](http://example/hadatac/api/studies/all)".

Some API Calls require a parameter. For instance, a study URI is required to retrieve the data about a specific study. In this case, the API Call is **studies/\(studyUri\)** where **\(studyUri\)** is the encoded version of the URI. If you are building this call in your browser, you may use a service like [https://www.urlencoder.org/](https://www.urlencoder.org/) to generate the encoded version of your URI.

In the following section we list HADatAc API Calls.

### 3.8.2.2. General Calls

**studies/all** - Return all studies in HADatAc, with the properties specified here.

**studies/\(studyUri\)** - Return additional meta-information about a study given a study URI. Things like PI, Institution, etc.

**studies/variables/\(studyUri\)** -

**studies/objectcollections/\(studyUri\)** - Given a Study URI, return the URI’s of all ObjectCollections that are a part of that Study, and the Type of that collection \(Subjects, Samples, etc\).

**studies/units/\(studyUri\)** -

**variables/all** - Should return all variables

**variables/\(variableUri\)** - Return additional meta-information about a variable given a variable URI.

**deployments/all** - Should return all deployments

**objectcollections/\(ocUri\)/all** - Given an ObjectCollection URI, return all StudyObjects in that collection

**objectcollections/size/\(ocUri\)** -

**objectcollections/\(ocUri\)/\(offset\)** -

**indicators/all** -

**units/all** - Get all units used for all variables.

**platforms/all** - Get all the platforms

**viewdsofview/all** - Get all the fields for view

### 3.8.2.3. Fetching Measurement Data

**measurements/\(studyUri\)/\(variableUri\)/\(objectUri\)** - Returns measurements of the given variable taken of the given subject for the given study

**measurements/\(studyUri\)/\(variableUri\)/\(objectUri\)/\(fromdatetime\)/\(todatetime\)** - Returns measurements of the given variable taken of the given subject for the given study between the specified time range.

**measurements/\(studyUri\)/\(variableUri\)** - Returns all measurements for all subjects of the given variable.

**measurements/dpl/\(studyUri\)/\(variableUri\)/\(dplUri\)** -

**measurements/dpl/\(studyUri\)/\(variableUri\)/\(dplUri\)/timerange** -

**measurements/dpl/\(studyUri\)/\(variableUri\)/\(dplUri\)/\(fromdatetime\)/\(todatetime\)** -

**measurements/\(studyUri\)/\(variableUri\)** -

