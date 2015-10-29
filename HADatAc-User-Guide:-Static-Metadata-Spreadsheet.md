### What are Static Metadata Spreadsheets?

They are spreadsheets used by domain experts to document data-related [static metadata](https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide:--Data-Management). Like any other spreadsheet, Static Metadata Spreadsheets are composed of one or more sheets. Once spreadsheets are filled out completely, they can be parsed, and if they are syntactically correct, they can be added into HADatAc's knowledge base.  

### How Do I Build a Static Metadata Spreadsheet?

Static Metadata Spreadsheets are expected to be developed from spreadsheet templates. In a template we have the following:
* one of more sheets;
* each sheet has a name (a simple string);
* each sheet has just one title row, and nothing else;
* the title row is composed of two or more columns, each column containing a label.

Once you go through the process of reading the template of a static metadata spreadsheet, you may start the process of describing your static metadata by filling out static metadata spreadsheets, one row a time. 

These are some of the rules that you most follow:

1. Do not add or remove columns;
2. It is okay to group create a spreadsheet that is about a single concept or instance. It is also okay to build a single spreadsheet for all concepts;
 
### Where Can I Find the Static Metadata Spreadsheet Templates? 

Use the templates below to create metadata for your scientific activities. A single static spreadsheet template may be used to record needed basic metadata.
* [Full Spreadsheet Template](https://github.com/paulopinheiro1234/hadatac/blob/master/public/example/metadata/templates/HASNetO-Template-Full.xlsx?raw=true)

Alternatively, the three complementary spreadsheets listed below may be used to record needed metadata. It is recommended that the these spreadsheets are used and populated into HADataC following the order in the list below.
 
* [Agent Spreadsheet Template](https://github.com/paulopinheiro1234/hadatac/blob/master/public/example/metadata/templates/HASNetO-Template-Agents.xlsx?raw=true) - Used to create agents (including users) and organizations (see example Agent spreadsheet)
* [Classes Spreadsheet Template](https://github.com/paulopinheiro1234/hadatac/blob/master/public/example/metadata/templates/HASNetO-Template-Classes.xlsx?raw=true) - Used to specialize classes of the family of Human-Aware Science Ontologies (see example Class spreadsheet)
* [Instances Spreadsheet Template](https://github.com/paulopinheiro1234/hadatac/blob/master/public/example/metadata/templates/HASNetO-Template-Instances.xlsx?raw=true) - Used to create instances of registered classes (see example Instance spreadsheet)
  
### Which Kind of Content Am I Expected to See Inside of Each Sheet?

Each sheet is either a concept kind (or class) or a list of concept instances. For instance, the sheet named InstrumentModels list the models of the instruments in a sensor network. The sheet named Instruments lists the actual instruments in the sensor network. The sheets are named according to the concepts described in the following paper (the reading of the paper is strongly suggested): 

_Pinheiro, Paulo., McGuinness, Deborah.L., and Santos, Henrique. 2015. Human-Aware Sensor Network Ontology: Semantic Support for Empirical Data Collection. In Proceedings of International Semantic Web Conference (ISWC) 2015 (October 11-15 2015, Bethlehem, PA, US). [(PDF)](http://tw.rpi.edu/media/2015/10/12/10c35/ISWC-LISC-2015-Paper.pdf)_

### What is the Meaning of the hasURI Column At the Beginning of Each Sheet?

Every concept and instance in a sensor network should have a name, and the name of concepts and instances are URIs (unified resource identifiers). The first column is named **hasURI** and contains the URI of the concept or instance described in the row of the sheet. If the sheet contains concepts, the first column identifies the URI of each concept that is going to be registered in HADatAc. If the sheet contains instances, the first column identifies the URI of each actual instances registered in HADatAc.

### How Do I Know if a Sheet is Used to Describe Concepts or Instances?

The header of the second column tells you if a sheet is about concepts or instances. If the sheet is about classes the header is **rdf:subClassOf**. If the sheet is about instances the header is **a**.

If a sheet is about a concept, the concept is from the Human-Aware Sensor Network Ontology (HASNetO), which is available at [http://hadatac.org/ont/hasneto/](http://hadatac.org/ont/hasneto/).

These are the URIs of some core concepts. 
- Platform Model: 
- Instrument Model:
- Detector Model:
- Entity:
- Characteristic:

### How Can I See the Hierarchies of Core HADatAc Concepts?

WE SHOULD HAVE AN EXAMPLE HADatAc installation -- not related to any project -- and the links to be included here should be to the metadata browser of the example installation (Henrique, can you do this?)

(TO BE WRITTEN)

### How Can I Add A New Concept Under an Existing Subconcept?

When browsing an hierarchy, you can inspect the concepts inside the hierarchy but hovering the mouse over the concepts. The info box on the right side of the browser would show you the details of the concept currently selected. One of the properties shown in the info box is the URI of the concept. If this is the concept that is going to be the parent of a new concept to be included, this is the URI that should be added to the **rdfs:subClassOf** property of the new concept.

### What Are the Values that I Should Use in Each Cell of a Row?

Values should be literals or URIs. For example, the second column is always a URI. 

Each concept is a subconcept of something else. For instance, an instrument called _Mass Spectrometer_ is a subclass of _Spectrometer_. Thus, the value of the **rdf:subClassOf** column for the Mass Spectrometer should be the URI of the spectrometer. In that way, concepts are organized into hierarchies.

In the case of instances, each instance should have the URI of a concept. For instance, the value of the **a** column of a mass spectrometer should have the URI of the concept _Mass Spectrometer_. 

### What are the Values for the Rest of the Columns in a Sheet?

The names are often self-explanatory. The **rdfs:label** is an important exception to this rule is that property names are self-explanatory. For instance, ***rdfs:label** is a textual description of the concept or instance being described in the spreadsheet. 

### Can I Validate My Spreadsheet?

A spreadsheet validation consists of a two phases:

1 The Parsing phase identifies syntax erros during the process of filling out the spreadsheets. The instructions for [parsing static metadata spreadsheets] (https://github.com/paulopinheiro1234/hadatac/wiki/HADatAc-User-Guide:-Parsing-a-Static-Metadata-Spreadsheet) describe how to identify syntax erros and fix them.

2 The Verification phase executes a number of basic rules to assure a minimal level of quality for the metadata captured through the use of static metadata spreadsheets. For instance, it is in the verification phase that we check if every instance has a concept URI, and if the concept URI exists. 


(TO BE WRITTEN) 