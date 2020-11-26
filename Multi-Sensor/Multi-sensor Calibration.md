# Multi-sensor calibration

Find the accurate relative poses between multiple sensors with different modalities and varying fields of view(FOVs).

## Difficulties

### Different modalities

- Dense but lack 3D information: camera
- 3D accurate but sparse and noise: lidar
- Radial accurate, but tangent coarse: radar
- Accurate but simple ego-location: GNSS

### Different FOVs

- Long-focus, short-focus, fisheye
- 360 surrounding
- 2d plane view

### Key step right after sensor setup

- Need sensitive enough to sensor condition
- Need generative enough to tolerate sensor noise, etc.

## Camera & Lidar calibration

| Title                                                        | Link                                                         | Year |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ---- |
| Unified Intrinsic and Extrinsic Camera  and LiDAR Calibration under Uncertainties | https://www.semanticscholar.org/paper/Unified-Intrinsic-and-Extrinsic-Camera-and-LiDAR-K%C3%BCmmerle-K%C3%BChner/09643e0a0d33ba6d7227eb10e38e0ccdcbca3345 | 2020 |
| Analytic Plane Covariances Construction  for Precise Planarity-Based Extrinsic Calibration of Camera and LiDAR | https://www.semanticscholar.org/paper/Analytic-Plane-Covariances-Construction-for-Precise-Koo-Kang/3d7e3046ac8db99f8166f558cb0d40e5d8283b47 | 2020 |
| Online Camera-LiDAR Calibration with  Sensor Semantic Information | https://www.semanticscholar.org/paper/Online-Camera-LiDAR-Calibration-with-Sensor-Zhu-Li/51c6f6f9bc15c4dd0160df21e359d008eae1fbac | 2020 |
| Improvements to Target-Based 3D LiDAR to  Camera Calibration | https://arxiv.org/abs/1910.03126v2                           | 2020 |
| Automatic extrinsic calibration between a  camera and a 3D Lidar using 3D point and plane correspondences | https://arxiv.org/abs/1904.12433v1                           | 2019 |
| Targetless Rotational Auto-Calibration of  Radar and Camera for Intelligent Transportation Systems | https://arxiv.org/abs/1904.08743v2                           | 2019 |
| A Novel Method for the Extrinsic  Calibration of a 2D Laser Rangefinder and a Camera | https://arxiv.org/abs/1603.04132v4                           | 2018 |
| LiDAR and Camera Calibration using Motion  Estimated by Sensor Fusion Odometry | https://arxiv.org/abs/1804.05178v1                           | 2018 |
| Semantic sensor fusion: from camera to  sparse lidar information | https://arxiv.org/abs/2003.01871v1                           | 2020 |