---
layout: page
title: 3D Dynamic Scene Interpolation with Gaussian Splatting
description: <strong>Sanghyun Hahn*, </strong>Jungwoo park*, Wonjae Ho*
img: assets/img/Dynamic_Interp_3DGS_proj/main.png
importance: 3
category: work
proj_pdf: 3D Dynamic Scene Interpolation with Gaussian Splatting.pdf
related_publications: false
---

In this project, we enhance the performance of Dynamic 3D Gaussian Splatting for sparse timewise inputs by introducing a loss term which integrates interpolated Gaussians from unseen timesteps.
Detailed explanations of the project can be found in the downloadable paper on the upper right. 


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/4.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/5.PNG" title="example image 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Gaussian Splatting is a method for representing a 3D scene with a large number of 3D Gaussians. 
In order to express a dynamic scene using 3D gaussians, the conventional approach is to generate an independent set of Gaussians for every timestep. 
However, this method requires a large amount of data and compuatational resources, which is inefficient. 
Deformable 3D Gaussians, or 4D Gaussian Splatting uses a MLP to solve this issue.
In this approach, a trained MLP takes the initial Gaussian as its input, and returns the Gaussian at time t, which greatly reduces the number of parameters. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/13.PNG" title="example image 2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/dnerf.gif" title="example image 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The biggest downside of 4D Gaussians Splatting is that the network is strongly overfitted to the input images, resulting in broken images at timesteps without any ground truth, which we refer to as interpolated timesteps. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/losses.png" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In order to address this issue, we propose Blended Gaussian Loss, which penalizes deviations between the scenes at interpolated timesteps and the ground truth. This loss term forces each interpolated scene to resemble one of the ground truth images, guiding the network to produce more realistic images.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/main.png" title="example image 4" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dynamic_Interp_3DGS_proj/result.png" title="example image 4" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The proposed method slightly outperforms vanilla 4D Gaussian Splatting, generating figures with less artifacts at timesteps without ground truth.