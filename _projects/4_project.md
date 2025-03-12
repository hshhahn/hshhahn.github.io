---
layout: page
title: Forward Facing 3D Gaussian Splatting as Markov Chain Monte Carlo
description: Jeongtaek Oh, Wonjun Jeong, Huijeong Choe, <strong>Sanghyun Hahn*</strong>
img: assets/img/FF_3DGS_proj/main.png
importance: 4
category: work
proj_pdf: FF_3DGS_MCMC.pdf
related_publications: false
---

In this project, we enhance the performance of 3D Gaussian Splatting as Markov Chain Monte Carlo in forward-facing scenes by introducing Depth Supervision and Near Gaussian Regularizers. 

<div class="row">
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

