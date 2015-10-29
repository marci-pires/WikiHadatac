### What are Static Metadata Spreadsheets?

They are spreadsheets used by domain experts to document data-related [static metadata](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide:--Data-Management). Like any other spreadsheet, Static Metadata Spreadsheets are composed of one or more sheets. Once spreadsheets are filled out completely, they can be parsed, and if they are syntactically correct, they can be added into HADatAc's knowledge base.  
  
### Which Kind of Content Am I expected to See inside Each Sheet?

Each sheet is either a concept kind (or class) or a list of concept instances. For instance, the sheet named InstrumentModels list the models of the instruments in a sensor network. The sheet named Instruments lists the actual instruments in the sensor network. The sheets are named according to the concepts described in the following paper (the reading of the paper is strongly suggested): 

Pinheiro, P., McGuinness, D.L., and Santos, H. 2015. Human-Aware Sensor Network Ontology: Semantic Support for Empirical Data Collection. In Proceedings of International Semantic Web Conference (ISWC) 2015 (October 11-15 2015, Bethlehem, PA, US).  [(PDF)](http://tw.rpi.edu/media/2015/10/12/10c35/ISWC-LISC-2015-Paper.pdf)

### What is the meaning of the URI field in the beginning of each sheet?

Every concept and instance in a sensor network should have a name, and the name of concepts and instances are URIs (unified resource identifiers). If the sheet contains concepts, the first column identifies the URI of each concept that is going to be registered in HADatAc. If the sheet contains instances, the first column identifies the URI of each actual instances registered in HADatAc.

   