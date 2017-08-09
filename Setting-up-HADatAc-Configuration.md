Assuming that HADatAc is installed at "[HADatAc]", configuration files are located at "[HADatAc]/conf"

## Setting up hadatac.conf

This is the main configuration file and tells the system.

#hadatac.conf
	  
# the application's base host URL
		host="http://localhost:9000"
		
		# the url that the application is deployed
		host_deploy="http://localhost:9000"
		
		# the base url that the application uses to send email
		base_url="127.0.0.1:9000"
		
		# the kb's base host URL -- usually, the application's base host URL without any port information
		kb="http://localhost"
	}

    # SOLR connection string
    #   - Current values are for locally installed SOLR instance
    #   - IMPORTANT NOTES FOR THE URL VALUESs BELOW:
    #     * DO NOT INCLUDE ENDING SLASHES
    #     * SOLR CONNECTION STRINGS OFTEN END WITH "/solr"
    #     * USE ABSOLUTE URLs INCLUDING THE PROTOCAL PART, e.g., "HTTP://" OR "HTTPS://" 
    solr {
    
        # HOME: the path in the file system where the SOLR instances are located
        home=/Users/paulo/hadatac/solr

        # URL for data collections
        data="http://127.0.0.1:8983/solr"
        
        # URL for metadata (RDF triplestore RDF) collection
        # For blazegraph in the local
		triplestore="http://127.0.0.1:9999/blazegraph/namespace/store"
        # For blazegraph in the vm
        # triplestore="http://127.0.0.1:8080/bigdata/namespace"
	    
        # URL for user management collection
        users="http://127.0.0.1:8983/solr"

        # URL for user permission management collection
        # For blazegraph in the local
        permissions="http://127.0.0.1:9999/blazegraph/namespace/store_users"
        # For blazegraph in the vm
        # permissions="http://127.0.0.1:8080/bigdata/namespace"
    }

    # activity flags are used to verify if HADatAc knowledge base contains 
    # concepts essential for supported scientific activities 
    activities {

        # use true for empirical activities involving the use of sensors
        empirical=true
        
        # use true for computational activities involving computational simulations
        computational=false
    }

    # properties about community using current HADatAc installation
    #  - these properties are used to project customization of HADaAc installations
    community {
       fullname="Child Health Exposure Analysis Repository"
       
       shortname="CHEAR"
       
       description="This is the CHEAR Human-Aware Data Acquisition framework installation. HADataC's concept of community is very broad ranging from a single person to the members of a laboratory to an entire organization to a large group of people from multiple organizations. The goal of CHEAR is to provide the extramural research community access to laboratory and statistical analyses aimed at adding or expanding the inclusion of environmental exposures in their research."
	   
       ont_prefix="heals"
    }

}

## Setting up email configuration

You may not need to set up email configuration if you are using HADatAc for development purpose. This configuration is essential if you are planning to create users, and to have this users to have authenticated access to the system. In this case, the email configuration will enable users to verify their emails and to request password reset.
[list and describe the meaning of each property]

## Setting up autoccsv.config

Raw files and metadata files that are uploaded into HADatAc are managed as part of the overall content of the app. This configuration file tells the app where those files go when are initially uploaded and where they are stored after they are processed.

[list and describe the meaning of each property]

## Setting up namespaces.properties

## Setting up labkey.config

[list and describe the meaning of each property]

## Setting up template.conf

[list and describe the meaning of each property]

## Creating Master user

