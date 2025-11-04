
# Adversarially Robust Multitask Adaptive Control

This repository includes the code to reproduce the experimental results of the following paper:

1) K. Fallah*, L. F. Toso*, J. Anderson (2025). [Adversarially Robust Multitask Adaptive Control](https://github.com/jd-anderson/PG-LQG/blob/main/PG-LQG.pdf)

*:Alphabetical equal contribution.
## Overview

This repository implements the **adversarially robust multitask adaptive** framework proposed in our paper.  
The project studies how multiple control systems—each with uncertain or partially known dynamics—can **collaboratively learn stabilizing controllers** while remaining robust to **heterogeneous models** and **adversarial (Byzantine) participants**.

At the core of the method is a **clustered multitask learning pipeline** (illustrated below), which integrates  
1. **Data collection** from multiple agents operating under certainty-equivalent controllers,  
2. **Clustered system identification (CSI)** to group dynamically similar systems,  
3. **Resilient aggregation** of model updates using *(f, λ)*-resilient rules such as the trimmed mean or geometric median, and  
4. **Controller synthesis** via the discrete algebraic Riccati equation (DARE) for each identified cluster.  

<p align="center">
  <img src="figures/pipeline.png" width="600">
</p>
<p align="center"><em>Figure 1: Workflow for adversarially robust multitask adaptive control.</em></p>

This joint learning–control loop iteratively refines both the model estimates and the feedback gains, guaranteeing stable trajectories and **sublinear cumulative regret**.  
Theoretical analysis shows that the expected regret for any honest system in cluster C<sub>j</sub> scales as:


$$\mathbb{E}[R_T^{(i)}] = \tilde{\mathcal{O}}\left(\frac{\sqrt{dT}}{m_j}+ \lambda\sqrt{dT}+ \epsilon_{\mathrm{het}}^2 T\right)$$

## Instructions

To run the codes in this repository, you only need a working Jupyter installation.

## Troubleshooting

If you have any trouble running those codes or have any questions about the paper, please email [Kasra Fallah](mailto:kasra.fallah@columbia.edu). 
