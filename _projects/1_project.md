---
layout: page
title: Initial Kernel Estimation for Image Deblurring
description: Dongkyu Shin*, Jonghooh Shin*, <strong>Sanghyun Hahn*</strong>, Seungseok Oh*, Jooyoung Kim*, Seokjin Park*
img: assets/img/Kernel_Estimation_proj/main_img.png
importance: 1
category: work
related_publications: false
---

In this project, we combine an energy function based method with initial kernel estimation to achieve single-image deblurring.

The process of deblurring an image can be reduced into finding an optimal kernel to be convoluted with the blurred image.
We embed the blurred image into the Fourier domain, and minimize the energy function through iteration.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Kernel_Estimation_proj/2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

However, estimating the deblur kernel from a simple gaussian initial kernel is challenging as shown in the figure below. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Kernel_Estimation_proj/3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Therefore, we trained an initial kernel estimation network from a blurred image dataset through deep learning, and started the deblurring process from the estimated initial kernel. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Kernel_Estimation_proj/4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

We compared the results to an End-to-End Deep learning method. The intial kernel estimation method outperformed the deblurring algorithm with raw gaussian intial kernel, but fell short compare to the state-of-the-art DL models. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Kernel_Estimation_proj/main_img.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Kernel_Estimation_proj/5.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


