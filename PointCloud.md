# Point Clouds

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

1. Spatial resolution

2. Point accuracy

3. Surface normal vector

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

**Marr's three levels**

### Low-Level processing

#### Image enhancement/filtering

1. Bilateral filtering
2. Gaussian filtering
3. Conditional filtering
4. Low/high pass filter
5. Random Filters for Compressive Sampling

#### Key point/edge detection

1. ISS3D

2. Harris3D
3. NARF
4. SIFT3D

### Mid-Level Processing

#### Feature description

1. Normal and curvature
2. Eigenvalue analysis
3. [SHOT](http://www.vision.deis.unibo.it/research/80-shot)
4. [PFH](https://ieeexplore.ieee.org/document/4650967)
5. [FPFH](https://ieeexplore.ieee.org/document/4650967)
6. 3D Shape Context
7. Spin Image

#### Point cloud segmentation

1. Regional growth
2. Ransac
3. Global optimization
4. K-Means
5. Normalize Cut (Context-based)
6. 3D Hough Transform
7. Connectivity analysis

#### Point cloud classification

1. Point-based classification
2. Segmentation-based classification
3. Classification based on deep learning

### High-Level Processing

#### Registration

##### Coarse Registration

Minimize the difference in spatial position between point clouds based on coarse registration.

1. [ICP](https://ieeexplore.ieee.org/document/121791) :  iterative closest point 
2. Robust ICP
3. point to plane ICP
4. Point to line ICP
5. MBICP
6. GICP
7. NICP

##### Fine Registration

Register the point cloud when the relative pose of the point cloud is unknown

###### Registration algorithm based on exhaustive search

Traverse the entire transformation space to select the transformation relationship that minimizes the error function or List the transformation relations that satisfy the most point pairs.

1. RANSAC
2. 4-Point Congruent Set
3. Super4PCS

###### Registration algorithm based on feature matching

Construct the matching correspondence between the point clouds through the morphological characteristics of the measured object itself, and then use the relevant algorithm to estimate the transformation relationship.

#### Three-dimensional reconstruction

#### Point cloud data management

1. Point cloud compression
2. Point cloud index
3. Point cloud LOD
4. Massive point cloud rendering.

[1]:https://pcl.readthedocs.io/projects/tutorials/en/latest/