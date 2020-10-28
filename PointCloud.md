# Point Cloud
## Introduction

### Content

#### Laser measurement

1. Three-dimensional coordinates (XYZ)

2. Laser reflection intensity

    1. surface material

	2. roughness

	3. incident angle direction of the target

	4. the emission energy of the instrument

	5. laser wavelength

#### Photogrammetry

1. Three-dimensional coordinates (XYZ)

2. Color information (RGB)

#### Laser measurement and photogrammetry

1. Three-dimensional coordinates (XYZ)

2. Laser reflection intensity

3. Color information (RGB)

### Attributes

#### Spatial resolution

#### Point accuracy

#### Surface normal vector

## Acquisition

| Acquisition       |         | Point density                                                                                         | Advantages                                                                                  | Disadvantages                                                                                                                                                                                                                                        | Applications                                                              |
| ----------------- | ------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| **Image-derived** |         | From Sparse to extremely high, depends on the spatial resolution   of the stereo or multi view images | With color (RGB, multi-spectral) information; suitable for large area(airborne, spaceborne) | Influenced by light;     Depends on camera, image matching algorithms, stereo angles, image resolutions, and image quality;     Not suitable for areas or objects without texture, such as water or snow-covered regions;     Influenced by shadows. | Urban monitoring;     Vegetation monitoring;     3D object reconstruction |
| **LiDAR**         | **ALS** | Sparse                                                                                                | High accuracy (<15cm); suitable for large area; not affected by weather                     | Expensive;     affected by mirror reflection;     Long scanning time.                                                                                                                                                                                | Urban monitoring;     Vegetation monitoring;     Power line detection     |
|                   | **MLS** | Dense, the smaller the survey distance, the higher the density                                        | High accuracy (cm-level)                                                                    |                                                                                                                                                                                                                                                      | Mapping;     Urban monitoring                                             |
|                   | **TLS** | Dense, the smaller the survey distance, the higher the density                                        | High accuracy (mm-level)                                                                    |                                                                                                                                                                                                                                                      | Small area 3D reconstruction                                              |
|                   | **ULS** | Dense, the smaller the survey distance, the higher the density                                        | High accuracy (cm-level)                                                                    |                                                                                                                                                                                                                                                      | Forestry survey;     Mining survey;     Disaster monitoring               |
| **RGB-D**         |         | Middle density                                                                                        | Cheap; flexible                                                                             | Close range;  Limited accuracy                                                                                                                                                                                                                       | Indoor reconstruction;     Object tracking;     Human pose recognition    |
| **InSAR**         |         | Sparse                                                                                                | Global data is available                                                                    | Expensive;     Ghost scatterers;     Pre-processing                                                                                                                                                                                                  | Urban monitoring;     Forest monitoring                                   |

## Processing

![pclstructure](PointCloud.assets/pclstructure.png)

Read [Point Cloud Library][1].

### Low-Level processing

### Mid-Level Processing

### High-Level Processing

[1]:https://pcl.readthedocs.io/projects/tutorials/en/latest/

