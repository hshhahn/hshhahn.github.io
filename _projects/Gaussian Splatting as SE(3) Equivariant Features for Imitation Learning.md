---
layout: page
title: Gaussian Splatting as SE(3) Equivariant Features for Imitation Learning
description: Research Intership @ SNURPM
contributers: <strong>Sanghyun Hahn</strong>, Taekyun Ha, Inhee Lee
img: assets/img/GS_SE3/method_overview.png
importance: 1
category: work
proj_pdf: Gaussian Splatting as SE(3) Equivariant Features for Imitation Learning.pdf
related_publications: false
---

In this project, we achieve one-shot imitation learning of robotic manipulations with Gaussian Splatting.
The key idea is that the Gaussian Features obtained from Gaussian Splatting carries more information compared to point clouds, enabling SE(3) pose matching between different objects within the same category.
This project was initially aiming for a submission for ICRA 2025, but before doing the real-world experiment I found out that the Gaussian ICP was already a proposed method in the paper RGBD GS ICP SLAM of ECCV 2024. 
While that paper used G-ICP to find correspondences between the map, the idea to treat Gaussians as feature descriptors is the shared.
Therefore, I left it as a project paper for one of the graduate classes.

From this experience, I learned the importance of literature reviews to my heart.

Check the pdf for more information.