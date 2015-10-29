### What are Static Metadata Spreadsheets?

They are spreadsheets used by domain experts to document data-related [static metadata](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide:--Data-Management). Like any other spreadsheet, Static Metadata Spreadsheets are composed of one or more sheets. Once spreadsheets are filled out completely, they can be parsed, and if they are syntactically correct, they can be added into HADatAc's knowledge base.  
  
### Which Kind of Content Am I expected to See inside of Each Sheet?

Each sheet is either a concept kind (or class) or a list of concept instances. For instance, the sheet named InstrumentModels list the models of the instruments in a sensor network. The sheet named Instruments lists the actual instruments in the sensor network. The sheets are named according to the concepts described in the following paper (the reading of the paper is strongly suggested): 

Pinheiro, P., McGuinness, D.L., and Santos, H. 2015. Human-Aware Sensor Network Ontology: Semantic Support for Empirical Data Collection. In Proceedings of International Semantic Web Conference (ISWC) 2015 (October 11-15 2015, Bethlehem, PA, US).  [(PDF)](http://tw.rpi.edu/media/2015/10/12/10c35/ISWC-LISC-2015-Paper.pdf)

### What is the Meaning of the hasURI Column At the Beginning of Each Sheet?

Every concept and instance in a sensor network should have a name, and the name of concepts and instances are URIs (unified resource identifiers). The first column is named **hasURI** and contains the URI of the concept or instance described in the row of the sheet. If the sheet contains concepts, the first column identifies the URI of each concept that is going to be registered in HADatAc. If the sheet contains instances, the first column identifies the URI of each actual instances registered in HADatAc.

### How Do I Know if a Sheet is Used to Describe Concepts or Instances?

The header of the second column tells you if a sheet is about concepts or instances. If the sheet is about classes the header is **rdf:subClassOf**. If the sheet is about instances the header is **a**.

### What Are the Values that I Should Use in Each Cell of a Row?

Values should be literals or URIs. For example, the second column is always a URI. 

Each concept is a subconcept of something else. For instance, an instrument called _Mass Spectrometer_ is a subclass of _Spectrometer_. Thus, the value of the **rdf:subClassOf** column for the Mass Spectrometer should be the URI of the spectrometer. In that way, concepts are organized into hierarchies.

In the case of instances, each instrument instance should have the URI of an instrument model.

### What are the Values for the Rest of the Columns in a Sheet?

The names are often self-explanatory. The **rdfs:label** is an important exception to this rule is that property names are self-explanatory. For instance, ***rdfs:label** is a textual description of the concept or instance being described in the spreadsheet. 
 