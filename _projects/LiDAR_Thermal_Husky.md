---
layout: page
title: LiDAR-Thermal Husky UGV Platform
description: Undergraduate Research Oppertumity Program (2023 Summer)
contributers: <strong>Sanghyun Hahn</strong>
img: assets/img/lidar_thermal_ugv_proj/main.png
importance: 5
category: work
related_publications: false
---

In this project, I developed a UGV platform that is capable of collecting LiDAR, thermal image, and IMU data for SLAM.
I designed mounts for the sensor system and a mini PC, set up the radio control system, and performed LiDAR-Camera Calibration.
I collected data inside the engineering department building of SNU, and tested LIO-SAM on the dataset.

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
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lidar_thermal_ugv_proj/4.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The frame is made of 10mm x 10mm aluminum profile, with the IMU and FLIR placed at h=130mm.
The LiDAR is directly attatched to the frame, while the IMU and FLIR, Mini PC are fixed by a 3D printed mount.

3D Gaussian Splatting as Markov Chain Monte Carlo (3DGS-MCMC) is a modified version of 3D Gaussian Splatting, which reduces the heuristics of the original method. 3DGS-MCMC treats the training and optimization process as a sampling process from a probability distribution. 
Using the probability approach, 3DGS MCMC treats the complicated Adaptive Density Control step as simple state transitions.
This metric does not require cloning or splitting of the Gaussian, reducing the number of hand-tuned parameters throughout the algorithm.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/8.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/9.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

While 3DGS-MCMC performs decently for a number of 360° datasets, we discovered some weaknesses of 3DGS-MCMC in forward-facing scenarios, especially when given random initials. 
The failure of 3DGS-MCMC in forward-facing scenes is mainly due to floating artifacts, which we suspect is from the model overfitting to closer regions of the camera during the state transition phase.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/10.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/11.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In order to address the weaknesses mentioned above, we integrated Depth Supervision to the model, while penalizing Gaussians that are placed near the cameras. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/13.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/14.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

As a result, our model, FF-3DGS-MCMC, outperformed the original 3DGS-MCMC algorithm in the LLFF Dataset, a dataset with forward-facing scenes. 
