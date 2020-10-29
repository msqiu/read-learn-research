# Point Cloud Segmentation

## Traditional segmentation methods based on point clouds

The main process of Point Cloud Segmentation is to group the original 3D points into non-overlapping areas. These areas correspond to specific structures or objects in a scene. Since this segmentation process does not require supervised prior knowledge, the results obtained do not have strong semantic information.

### Edge-based segmentation

The edge-based PCS method converts the two-dimensional image-based method directly into a three-dimensional point cloud. This method is mainly used in the early stage of PCS. Since the shape of the object is described by the edge, it can be found by looking for the area close to the edge. The principle of the edge-based method is to locate the points with rapid changes in brightness, which is similar to some two-dimensional image segmentation methods.

There are two main steps:

1. Edge detection, extract the boundaries of different regions
2. Edge point grouping, generate the final segmentation by grouping the points within the boundary in 1.

### Segmentation based on regional growth



### Segmentation based on model fitting



### Segmentation based on clustering