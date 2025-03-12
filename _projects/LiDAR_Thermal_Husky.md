---
layout: page
title: LiDAR-Thermal Husky UGV Platform
description: Undergraduate Research Oppertumity Program (2023 Summer)
contributers: <strong>Sanghyun Hahn</strong>
img: assets/img/lidar_thermal_ugv_proj/main.png
importance: 5
category: work
proj_pdf: LiDAR_Thermal_Husky.pdf
related_publications: false
---

In this project, I developed a UGV platform that is capable of collecting LiDAR, thermal image, and IMU data for SLAM.
I designed mounts for the sensor system and a mini PC, set up the radio control system, and performed LiDAR-Camera Calibration.
I collected data inside the engineering department building of SNU, and tested LIO-SAM on the dataset.
More information on the project can be found in the downloadable presentation slide on the upper right.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/1.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/2.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/3.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The frame was made of 10mm x 10mm aluminum profile, with the IMU and FLIR placed at H=130mm.
The LiDAR was directly attatched to the frame, while the IMU, FLIR, and Mini PC were fixed to a 3D printed mount.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/5.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Power converters were used to match the input voltages of the sensors.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/move.gif" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

A remote control system was set up to control the HUSKY, using ROS.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/6.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

LiDAR, Thermal Camera, and IMU data was collected in the engineering department building of SNU, and LIO-SAM succeeded in loop closure.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/calib.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The intrinsic/extrinsics for LiDAR-Camera calibration was obtained by a calibration toolbox. 