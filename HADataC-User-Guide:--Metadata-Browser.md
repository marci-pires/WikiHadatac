The Metadata Browser allows you to examine the parts of your data collection that give it context, including the entities observed, the characteristics being measured, and the sensors taking the measurements. Metadata is kept as linked data in order to preserve the relationships between it and the data, and leverages ontologies already in use by other scentific communities to aid interoperability. Ontologies also provide a hierarchical structure of concepts, which can help lend insight into the organization of the sensor network collecting the data.

You can reach the Metadata Browser from the HADataC portal page by clicking "Browse Metadata", or, if you are already on another page, by clicking "Metadata Browser" in the black top bar.

##Platform, Instrument, and Detector Model Hierarchies
These three displays show the models of sensors in your data collection project. They are represented as a hierarchy backed by the HASNetO and VSTOI ontologies. Sensor models are considered classes - that is, they are more general concepts rather than physical objects. The default "tree view" on these pages displays this hierarchy as an interactive tree, with less specific concepts on the left side, branching out into more specific ones towards the right. Click nodes to expand or contract subtrees (all are expanded by default), or mouse over a node for additional information.

The "table view" contains the same information as a flat table. Click the name of the model to expand its block entry in order to see detailed information about that sensor model.

###Platform Models
- Name: The name of the model.
- Maker: The manufacturer.
- Description: Some description of the Platform Model, such as where it is used, etc.

###Instrument Models
- Name: Model name
- Maker: Manufacturer name
- Description: Short description of Instrument model.
- Number of attached detectors: How many Detectors are permanently part of this Instrument
- Maximum number of detachable detectors: How many removable Detectors may be attached to this Instrument
- Maximum number of logged measurements: How many measurements can be stored.
- Min and max operating temperature: Temperature range inside which the Instrument is expected to function.

###Detector Models
- Name: Model name
- Maker: Manufacturer name
- Description: Short description of Detector model.
- **Sensing Perspective**: A description of what and where this Detector is designed to measure. Each Sensing Perspective has its own set of additional properties:

- Name: A pairing of an Entity and a Characteristic, to help uniquely define a Detector's context. This is important in cases where there may be measurements of two different Characteristics of the same Entity (for example, AirTemperature vs AirRelativeHumidity), or the same Characteristic of two different Entities (such as AirTemperature vs WaterTemperature).
- Accuracy %: The expected accuracy of this Detector when measuring the given EntityCharacteristic, expressed as a percentage.
- Accuracy R2
- Output resolution: The resolution of the measurements taken by the Detector.
- Max response time: 
- Min and max range of values: Lowest and highest numbers the Detector records.

##Platform, Instrument, and Detector Lists
These displays are for viewing individual sensors. Each one is an instance of a model, which is why you may see some names repeated in the table list. For example, your project may use two thermometers of the same model; HASNetO requires that each one have its own unique identifier (typically a serial number), but because they are both the same class (eg, model), they still share certain characteristics such as manufacturer or design specifications.

While the Model Hierarchy view gives information about the properties common to all individual sensors of that model, the individual Lists views shows properties specific to each single sensor. There is only a table view for these displays, and each entry can be expanded to see detailed information about that sensor.

###Platform List
- Name: Model name of the Platform.
- Serial Number: Unique identifier for this Platform.
- Lat-long location: Latitude and Longitude describing where this Platform is deployed.

###Instrument List
- Name: Instrument model name.
- Serial Number: Instrument's unique identifier.

###Detector List
- Name: Model name of the Detector.
- Serial Number: Detector's unique identifier.

##Entity, Characteristic, and EntityCharacteristic
These displays show metadata for what your collection measures. These sections leverage the Extensible Observation Ontology (OBOE) to describe the Entity and Characteristic of the measurements in order to provide context for the data. In the OBOE model, the Entity is the thing being observed (such as the water in a lake, the air in a room, or a sample in a laboratory), and the Characteristic is the specific thing being measured (such as dissolved oxygen saturation, relative humidity, or color). Note that it is possible for a sensor to also be an Entity if it also logs data about itself, such as battery charge. Both Entities and Characteristics are more general concepts, and there is no one-to-one mapping between Entities and Characteristics in OBOE: two Entities may share a Characteristic (ie, water temperature and air temperature), and a single Entity may have multiple Characteristics (ie, temperature, relative humidity, and particulate matter are all possible Characteristics of air). 

Entity and Characteristic displays also contain both a tree view showing the hierarchy from the OBOE ontology, including whatever extensions have been made to include concepts relevant to your data collections. As with the sensors' tree views, subtrees can be expanded/contracted by clicking on the nodes, and mousing over displays additional information in a panel on the right side.

###EntityCharacteristic
An EntityCharacteristic is, as the name suggests, a pairing of an Entity with a Characteristic. These are the more specific things that we can match to Detectors as "sensing perspectives". If a thermometer only works in water, then it has "WaterTemperature" as the EntityCharacteristic of its Sensing Perspective. This differentiates it from a different thermometer that only works in air - both measure the same Characteristic, but of different Entities. A thermometer that can be used for both AirTemperature and WaterTemperature has two Sensing Perspectives.

The EntityCharacteristic view is a pair of tables that shows the matchings between Entity and Characteristic. The information in both tables is the same, but displayed differently: one with the Entity in the leftmost column, and one with the Characteristic in the leftmost column. Both are provided so that you can decide which is easier to use for your specific task. In both tables, you may sort any column alphabetically by clicking the column name.

##Standards
