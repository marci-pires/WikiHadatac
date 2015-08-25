## Grades
For each field (property):
* A - Metadata is present, complete, and correct.
* B - Metadata is present and correct, but incomplete.
* C - There is metadata, but it is incorrect.
* D - Metadata is not present, but it is known.
* E - Metadata is not present; values are unknown.
* NA - Metadata is not present but field is not necessary for this item.

If there is a concept or individual missing completely:
* X - Item is omitted entirely (and therefore all fields are either D or E)

## Lists - Sensor Network
### Platform Model Hierarchy
Ensure that there is one entry for each Platform Model. Verify that each entry has all of the following properties:
- Name
- Maker
- Description

### Platform List
Ensure there is one entry for each Platform, and each has the following properties:
- Name (Note that this might not be unique if there are two separate platforms of the same model)
- Serial number (This *must* be unique for each Platform, regardless of model)
- Lat-long location

### Instrument Model Hierarchy
Verify that there is one entry for each Instrument Model, each with properties:
- Name
- Maker
- Description

Not all of these are applicable to every Instrument Model; verify that these fields contain data where necessary:
- Number of attached detectors
- Maximum number of detachable detectors
- Maximum number of logged measurements
- Min and max operating temperature (+ units)

### Instruments
Ensure there is one entry for each Instrument, and all have both properties:
- Name (Again, not necessarily unique)
- Serial number (Must be unique)

### Detector Models
Verify there is one entry per Detector Model:
- Name
- Maker
- Description

In addition, each Detector Model should have at least one Sensing Perspective. A Sensing Perspective should have the following properties, however it is possible that not all are known for every Sensing Perspective:
- EntityCharacteristic name (Necessary)
- Accuracy %
- Accuracy R2
- Output resolution
- Max response time (+ units)
- Min and max range of values

### Detector List
As with other lists of individuals, verify that there is one entry for each Detector with the following information:
- Name (Might not be unique)
- Serial number (Must be unique)

## Lists - Measurements
### Entities
Review list of Entities to be sure that everything your project plans to observe for data measurements is included. Note that context is very important in differentiating Entities - for example, measuring water in a lake is different from measuring a sample of water brought back to the lab.
### Characteristics
### EntityCharacteristics
A unique pairs of an Entity and a Characteristic, for describing Sensing Perspectives. There will not be an EntityCharacteristic for _every_ pairing of Entity and Characteristic, only those represented in the Sensing Perspectives.
- Entity (Exactly one per entry)
- Characteristic (Exactly one per entry)

### Standards

### Agents
There are two different types of thing represented as "Agents" - People and Organizations. This graph should be connected, with the placeholder Agent node at the root. Edges in this graph represent a part-of/has-part relationship.
- Name (For both People and Organizations)
- Email (Where applicable)
- Website (Where applicable)
- Some parent node in the graph - an Organization may be a part of another organization, or, if it stands alone, then its parent is the Agent placeholder at the center. Similarly, a person may belong to one or more Organizations, or, if completely unaffiliated, will connect only to the Agent placeholder.