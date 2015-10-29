### What are Static Metadata Spreadsheets?

They are spreadsheets used by domain experts to document data-related static metadata. Like any spreadsheet, it is composed of one or more sheets. Once spreadsheets are filled out completely, they can be parsed, and if they are syntactically correct, they can be added into HADatAc's knowledge base.  
  
### What is the meaning of each sheet?

Each sheet is either a concept kind (or class) or a list of concept instances. For instance, the sheet named InstrumentModels list the models of the instruments in a sensor network. The sheet named Instruments lists the actual instruments in the sensor network. 

### What is the meaning of the URI field in the beginning of each sheet?

Every concept and instance in a sensor network should have a name, and the name of concepts and instances are URIs (unified resource identifiers). If the sheet contains concepts, the first column identifies the URI of each concept that is going to be registered in HADatAc. If the sheet contains instances, the first column identifies the URI of each actual instances registered in HADatAc.

   