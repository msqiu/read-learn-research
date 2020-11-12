# Object detection in RGB-D images

## important paper review

### [Learning Rich Features from RGB-D Images for Object Detection and Segmentation(ECCV'14)](https://arxiv.org/abs/1407.5736)

On the basis of the 2D target detection framework R-CNN, add a module that utilizes Depth Map(encode the depth image with three channels at each pixel: horizontal disparity, height above ground, and the angle the pixel’s local surface normal makes with the inferred gravity direction).

![img](RGBDOD.assets/640)

1. Based on RGB image and Depth Map, detect the contour in the image, and generate 2.5D proposals (as can be seen from the overview, the so-called 2.5D actually includes the parallax, height and tilt angle of each pixel of the target)

2. Use CNN for feature extraction. The network here includes two: Depth CNN learns features on the depth map, RGB CNN learns features on 2D images, and finally uses SVM for classification.