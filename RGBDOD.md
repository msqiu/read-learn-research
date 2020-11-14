# Object detection in RGB-D images

## important paper review

### [Learning Rich Features from RGB-D Images for Object Detection and Segmentation(ECCV'14)](https://arxiv.org/abs/1407.5736)

On the basis of the 2D target detection framework R-CNN, add a module that utilizes Depth Map(encode the depth image with three channels at each pixel: horizontal disparity, height above ground, and the angle the pixel’s local surface normal makes with the inferred gravity direction).

![img](https://mmbiz.qpic.cn/mmbiz_jpg/J24zDnPUB9FOKibdzVJ8mrqTLfdiaVDIgZHLV2tyEASwst4lJ84LayGibkqyCtdIk7MJSpH62tISrQm5UpQPzYgAw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

1. Based on RGB image and Depth Map, detect the contour in the image, and generate 2.5D proposals (as can be seen from the overview, the so-called 2.5D actually includes the parallax, height and tilt angle of each pixel of the target)

2. Use CNN for feature extraction. The network here includes two: Depth CNN learns features on the depth map, RGB CNN learns features on 2D images, and finally uses SVM for classification.



### [3D Object Proposals for Accurate Object Class Detection(NIPS'15)](http://papers.nips.cc/paper/5644-3d-object-proposals-for-accurate-object-class-detection.pdf#:~:text=%20%20%20Title%20%20%203D%20Object,%20Neural%20Information%20Processing%20Systems%20ht%20...%20)

At present, the most advanced RCNN method does not perform well on the autonomous driving data set KITTI. One of the reasons is that the test images on KITTI contain many small objects, occlusions, and shadows, so that proposals that actually contain objects are considered to be excluded.

A new object proposal method: For each 3D bounding box (y), use a tuple to represent (x, y, z, θ, c, t), and (x, y, z) represent the 3D box The center of, θ represents its azimuth, c represents the type of object, and t represents the corresponding 3d box template set.

With x representing the point cloud and y representing the proposal, the author believes that y should have the following characteristics:

1. High-density areas containing point clouds
2. Cannot overlap with free space
3. The point cloud should not extend vertically outside the 3d box
4. The height of the point cloud near the box should be lower than the box

$$
E(\mathbf{x}, \mathbf{y})=\mathbf{w}_{c, p c d}^{\top} \phi_{p c d}(\mathbf{x}, \mathbf{y})+\mathbf{w}_{c, f s}^{\top} \phi_{f s}(\mathbf{x}, \mathbf{y})+\mathbf{w}_{c, h t}^{\top} \phi_{h t}(\mathbf{x}, \mathbf{y})+\mathbf{w}_{c, h t-c o n t r}^{\top} \phi_{h t-c o n t r}(\mathbf{x}, \mathbf{y})
$$

![img](https://mmbiz.qpic.cn/mmbiz_jpg/J24zDnPUB9FOKibdzVJ8mrqTLfdiaVDIgZSozuohNklibrTdWqcIW3uT7IKFttGwGkibNO4rGGyGNxQ9JTZCEuqXMw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



### [Deep Sliding Shapes for Amodal 3D Object Detection in RGB-D Images(CVPR'16)](https://ieeexplore.ieee.org/document/7780463)

Which representation is better for 3D object detection, 2D or 3D? The reason why the current 2D method performs better may be because its CNN model is more powerful (well-designed&pre-trained with ImageNet), not because of its 2D expression

Multi-scale 3D RPN (Region Proposal Network):

![img](https://mmbiz.qpic.cn/mmbiz_jpg/J24zDnPUB9FOKibdzVJ8mrqTLfdiaVDIgZqn33UF1axANnRiatO2t5aHcrN6fib9fhEWvobzguwwA7MEZ1CoFOYYiaA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

Encoding 3D Representation: Truncated signed distance function, TSDF

![img](https://mmbiz.qpic.cn/mmbiz_jpg/J24zDnPUB9FOKibdzVJ8mrqTLfdiaVDIgZITK325zfDcwn8KfNWBibLnmpRHxicX0bKBlVbXsnnE9Lt2LlboH4Tv8w/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

