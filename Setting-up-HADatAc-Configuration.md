Assuming that HADatAc is installed at "[HADatAc]", configuration files are located at "[HADatAc]/conf"

## Setting up hadatac.conf

This is the main configuration file and tells the system.

### hadatac.conf
	  
#### the application's base host URL
     default: host="http://localhost:9000"
		
#### the url that the application is deployed
     default: host_deploy="http://localhost:9000"
		
#### the base url that the application uses to send email
     default: base_url="127.0.0.1:9000"
		
#### the kb's base host URL -- usually, the application's base host URL without any port information
     default: kb="http://localhost"

### SOLR
    
#### HOME: the path in the file system where the SOLR instances are located
     default: home=/../hadatac/solr

#### URL for data collections
     default: data="http://127.0.0.1:8983/solr"
        
### URL for metadata (RDF triplestore RDF) collection
### For blazegraph in the local
    default: triplestore="http://127.0.0.1:9999/blazegraph/namespace/store"
### For blazegraph in the vm
    default: triplestore="http://127.0.0.1:8080/bigdata/namespace"
	    
### URL for user management collection
    default: users="http://127.0.0.1:8983/solr"

### URL for user permission management collection
### For blazegraph in the local
    default: permissions="http://127.0.0.1:9999/blazegraph/namespace/store_users"
### For blazegraph in the vm
    default: permissions="http://127.0.0.1:8080/bigdata/namespace"

### activity flags are used to verify if HADatAc knowledge base contains 
### concepts essential for supported scientific activities 

#### use true for empirical activities involving the use of sensors
     empirical=true

#### use true for computational activities involving computational simulations
     computational=false

### properties about community using current HADatAc installation
###  - these properties are used to project customization of HADaAc installations
       
    default: fullname="Child Health Exposure Analysis Repository"
       
    default: shortname="CHEAR"
       
    default: description=""
	   
    default: ont_prefix="heals"

## Setting up email configuration

You may not need to set up email configuration if you are using HADatAc for development purpose. This configuration is essential if you are planning to create users, and to have this users to have authenticated access to the system. In this case, the email configuration will enable users to verify their emails and to request password reset.

### application.conf

#### Deadbolt
include "play-authenticate/deadbolt.conf"

#### SMTP
include "play-authenticate/smtp.conf"

#### Play authenticate
include "play-authenticate/mine.conf"

#### HADataC 
include "hadatac.conf"

#### Session conf
session.maxAge=1h
play.http.session.maxAge=12h

#### java config
jvm.memory=-Xmx2048M -Xms2048M

## Setting up autoccsv.config

Raw files and metadata files that are uploaded into HADatAc are managed as part of the overall content of the app. This configuration file tells the app where those files go when are initially uploaded and where they are stored after they are processed.

### Configure the path of csv files
path_proc=processed_csv/
path_unproc=unprocessed_csv/
auto=on

## Setting up namespaces.properties

## Setting up labkey.config

### Configure the labkey server url
site=https://chear.tw.rpi.edu/labkey/
folder=CHEAR PRODUCTION

### Configure the key for encryption on LabKey authority
encryption_key=yourkey

## Setting up template.conf

[list and describe the meaning of each property]

## Creating Master user

