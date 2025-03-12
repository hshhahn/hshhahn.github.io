---
layout: page
title: Forward Facing 3D Gaussian Splatting as Markov Chain Monte Carlo
description: Term Project - Deep Learning (2024 Fall)
contributers: Jeongtaek Oh*, Wonjun Jeong*, Huijeong Choe*, <strong>Sanghyun Hahn*</strong>
img: assets/img/FF_3DGS_proj/main.png
importance: 2
category: work
proj_pdf: FF_3DGS_MCMC.pdf
related_publications: false
---

In this project, we enhance the performance of 3D Gaussian Splatting as Markov Chain Monte Carlo in forward-facing scenes by introducing Depth Supervision and Near Gaussian Regularizers. 
Detailed explanations of the project can be found in the downloadable paper on the upper right. 

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/5.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FF_3DGS_proj/6.PNG" title="example image 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

3D Gaussian Splatting as Markov Chain Monte Carlo (3DGS-MCMC) is a modified version of 3D Gaussian Splatting, which reduces the heuristics of the original method. 3DGS-MCMC treats the training and optimization process as a sampling process from a probability distribution. 
Using the probability approach, 3DGS MCMC treats the complicated Adaptive Density Control step as simple state transitions.
This metric does not require cloning or splitting of the Gaussian, reducing the number of hand-tuned parameters throughout the algorithm.

<div class="row align-items-center">
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
