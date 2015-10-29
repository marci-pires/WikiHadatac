# On the HADataC use of URIs

## Static metadata URI

### For classes

Static metadata classes are intended to be reused across multiple projects, and shared through HADataC.org. It is possible for one project to have its own set of classes without sharing the classes outside the project. If that is the case, it is up to the project to define its own policy on how to assign URIs to classes of static metadata. 

If the project shares classes, we recommend the project to consider the use of the http://hadatac.org as the base for shared resources. 

(TODO: COMPLETE DESCRIPTION ON HOW TO REQUEST A HADATAC.ORG URI)

### For instances

Static metadata instances are intended to be privately shared within projects. For instance, the serial number of instruments are not something that is of interest to other projects. Every HADatAc installation has a host URI, e.g., http://example.org. The URI of a HADataC installation is typically the host URI followed with /hadatac/ (trailing slash is needed), e.g., http://example.org/hadatac/. URIs of instances are often stored in a folder within the host machine, which is associated with a given URL in case the project decides to share their instances. For instance, we can create a folder meta (http://example.org/meta/).   

## Dynamic metadata URI

Every HADatAc installation has a host URI, e.g., http://example.org. The URI of a HADataC installation is typically the host URI followed with /hadatac/ (trailing slash is needed), e.g., http://example.org/hadatac/

URI generators is a piece of software responsible for generating dynamic metadata such as deployments, data collections and datasets. They are called URI generators because they are also responsible for generating and assigning URIs for dynamic metadata as they are created. 

Every HADatac installation has one console, which includes a Deployment Management module. The console's Deployment Management is a URI generator. MOCCASN, the Android application used for capturing contextual knowledge about human interventions is another URI generator. The console's Deployment Management module is already pre-registered with HADataC, and its URI generator ID is '00000001'. All other URI generators need to be registered with a HADataC installation, which will assign a new ID for each registered URI generator.

    

## Data URI

# Deployment Management
