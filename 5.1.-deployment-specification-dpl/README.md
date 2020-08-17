# 5.1.-Deployment-Specification-\(DPL\)

## 5.1.1. Purpose of DPL specification files

Deployment specification \(DPL\) files are used to register instruments, platforms, and the deployment of instruments at platforms. Further, instruments rely on detectors that are used to capture signals that instruments translate into values.

## 5.1.2. Understanding DPL Content

In order to understand how to use measured data, e.g., to generate a data visualization, one needs to understand metadata about the sensing infrastructure, and from this understanding, be able to first answer the following question:

* Where are the instruments deployed? 

Measurement values coming from sensors can be acquired by local sensing \(i.e., acquiring measurement values where the sensor is located\) or remote sensing \(i.e., acquiring measurements that are not necessarily where the sensor is located\). For remote sensing, a more complete understanding about the sensing infrastructure would also require an understanding of the so-called field-of-view \(FOV\) of the sensor. FOVs are actually are in most cases 3D areas where range data come from. In this case, one need to also answer the following question:

* If remote sensing is used, what is the field of view of a given deployed instrument?

### 5.1.2.1 Instrument \(sensors\) Location

In the area of scientific visualization, geometries associated with spatial data \(i.e., spatial structure of measured object\(s\)\) is essential to render the spatial data \(the spatial structure of the object\) of the data.

For scientific visualization of measurement data, one needs to get both measurement spatial data and the geometry of spatial data. HADatAc uses DPL files to acquired knowledge about spatial data geometry. In this case, one can use the platform/all service of the HADatAc's API to retrieve spatial data geometry.

The exact specification of the platform can vary, and the DPL file is designed to capture key features of platforms, according to the following rules: 1. A platform can have either a static location \(e.g. a weather station installed in a fixed position\) or a dynamic location \(e.g., a human wearing a step counting equipment and walking around\) 2. Most platforms are static, which normally implies that three dimensions are specified for the platform location. If a platform is specified with less than three coordinates, for example, by having a location specified by a point \(x,y\) coordinates, one can assume that the z coordinate is irrelevant for the visualization, or that the platform is free to move in the "z" direction like an elevator, for example. 3. Platforms can be decomposed into sub-Platforms \(e.g., building into floors, floors into rooms/walls/etc\). Conversely, a platform can have more than one super-platforms. 4. If the coordinates of a certain platform is not specified, the platform will inherit the coordinated from one of its super-platforms, if any. 5. The coordinate system may be different between the sub and the super platforms. For example, a building may be defined in terms of lat and long, while the floor of the building may be defined in terms of Euclidean coordinates. 6. Platforms may have a layout, or use the layout of a related platform as a reference layout. In HADatAc, if coordinates are latitude and longitude, the reference layout of the platform is assumed to be the Earth's surface. Otherwise, HADatAc needs to have its own layout or inherit one layout, e.g., a reference layout.

With the concepts above and the content of a given DPL file, one may be able to answer the first question related to where sensors are located.

## Define the type of sensors

In general, two types of sensors exist local sensing or remote sensing.

### Spatial data based on local sensing

If the local sensor is used, the location of the data is at the platform where the instrument acquiring the data is deployed \(e.g temperature sensor\). Since the instrument is collecting data where the instrument is located, and the instrument is located at the platform where it is deployed, then the from the same location of the platform, and no field of view knowledge is required.

### Spatial data based on remote sensing

If a remote sensor is used, the location of the data is in a 3D volume called 'field of view' of the sensor, in this case, we need to use field of view information provided by the platform's FOV fields. The HADatAc API also provides a separate fieldsofview/all service to retried FOV info.

