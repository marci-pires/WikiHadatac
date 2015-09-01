# On the HADataC use of URIs

## Static metadata URI

### For classes

Static metadata classes are intended to be reused across multiple projects, and shared through HADataC.org. It is possible for one project to have its own set of classes, and to not share it outside the project. If that is the case, it is up to the project to define its own policy on how to assign URIs to classes of static metadata. 

If the project is willing to share the classes, we recommend the project to consider the use of the http://hadatac.org as the base for shared resources. 

(TODO: COMPLETE DESCRIPTION ON HOW TO REQUEST A HADATAC.ORG URI)

### For instances

## Dynamic metadata URI

Every HADataC has a host URI, e.g., http://example.org. The URI of a HADataC installation is typically the host URI followed with /hadatac/ (trailing slash is needed), e.g., http://example.org/hadatac/

URI generators is a piece of software responsible for generating dynamic metadata such as deployments, data collections and datasets. They are called URI generators because they are also responsible for generating and assigning URIs for dynamic metadata as they are created. 

Every HADatac installation has one console, which includes a Deployment Management module. The console's Deployment Management is a URI generator. MOCCASN, the Android application used for capturing contextual knowledge about human interventions is another URI generator. The console's Deployment Management module is already pre-registered with HADataC, and its URI generator ID is '00000001'. All other URI generators need to be registered with a HADataC installation, which will assign a new ID for each registered URI generator.

    

## Data URI

# Deployment Management
