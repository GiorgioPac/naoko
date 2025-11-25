---
title: " Numerical Investigation of Aerodynamic Performance of a Formula 1 Rear Wing: DRS Activation and Gurney Flap"
categories:
  - CFD
  - F1
tags:
  - SU2
  - Aerodynamics
  - Formula 1
  - project
mathjax: true
layout: single
classes: wide
date: 2025-11-24
header:
  overlay_image: /assets/images/su2/su2_banner.png
  caption: "Credit: Giorgio Pacchione"
excerpt: "A CFD investigation into Formula 1 rear wing aerodynamics, employing sliding meshes to simulate DRS deployment and evaluate the performance of the Gurney Flap."
---

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [['$','$'], ['\\(','\\)']],
      processEscapes: true
    }
  });
</script>
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Introduction: Problem Statement and Objective 🎯

This project utilized the open source CFD solver **SU2** to perform a two dimensional RANS analysis of a Formula 1 rear wing. The primary goal was to quantify the aerodynamic performance gains achieved by two key solutions: the active **Drag Reduction System (DRS) deployment** and the addition of a **Gurney Flap**. The study focuses on a DRS setup and investigates the effects of unsteady and transient phenomena that may arise upon its activation. The Gurney flap is tested to evaluate its functioning and effectiveness limitedly to steady conditions.

## Methodology and Simulation Setup

The simulation focused on a two-element wing (mainplane and DRS flap). To accurately model the $40^{\circ}$ rotation of the DRS flap, a **Sliding Mesh approach** was employed, allowing the mesh around the flap to move dynamically while the rest of the domain remained stationary.

We used the compressible form of the RANS equations with the SST $k-\omega$ turbulence model to ensure high fidelity near the walls and in separated flow regions. Special geometric attention was required to model the Gurney Flap, necessitating the use of transfinite surfaces for the boundary layer mesh.

### Visualization of Sliding Mesh Topology

The images below illustrate the mesh topology. A key challenge was maintaining the boundary layer integrity at the interface between the rotating and stationary zones. Furtheremore, the use of slinding meshes requires particular attention in meshing the interface area, where cells from different zone must have similar size to have stability and convergence.

<figure class="half">
    <a href="/naoko/assets/images/su2/mesh_sliding_close.png"><img src="/naoko/assets/images/su2/mesh_sliding_close.png" alt="Mesh DRS Closed"></a>
    <a href="/naoko/assets/images/su2/mesh_sliding_open.png"><img src="/naoko/assets/images/su2/mesh_sliding_open.png" alt="Mesh DRS Open"></a>
    <figcaption>Figure 1: Comparison of the sliding mesh interface for the disabled (left) and enabled (right) DRS configurations.</figcaption>
</figure>

## Key Results: Transient Effects and Gurney Flap

### 1. Transient Effects (DRS Activation)
The $40^{\circ}$ DRS opening occurs over a rapid $0.2$ second window. The **unsteady analysis** was crucial as it revealed that the aerodynamic performance does not stabilize immediately:
* **Transient Duration:** Aerodynamic coefficients continue to change for approximately one second after the motion stops, highlighting that transient effects impact performance for 10-20% of the duration the DRS is enabled on track.
* **Vortex Influence:**  A vortex can be detected downstream of the rear wing after activating the DRS. This vortex is injected into the flow by the changing circulation that results from the opening of the DRS flap. As such, it has a circulation that is opposite, in sign, to that of the starting vortex. When sufficiently close to the rear wing, it induces a velocity component on the airfoils, which has the effect of altering their perceived angle of attack. Due to the influence of the vortex, the mainplane airfoil feels an increased angle of attack that contributes to make the lift on the main wing more negative, generating temporarily a larger downforce. As time evolves, the vortex is advected away by the velocity field while diffusing. 

<figure class="half">
    <a href="/naoko/assets/images/su2/lift_coefficient.png"><img src="/naoko/assets/images/su2/lift_coefficient.png" alt="Lift Coefficient Evolution"></a>
    <a href="/naoko/assets/images/su2/drag_coefficient.png"><img src="/naoko/assets/images/su2/drag_coefficient.png" alt="Drag Coefficient Evolution"></a>
    <figcaption>Figure 2: Transient evolution of Lift (left) and Drag (right) coefficients during the DRS opening phase.</figcaption>
</figure>

### 2. Gurney Flap Trade-Off
The Gurney Flap (tested at $0.01c$ and $0.02c$) was confirmed to significantly increase downforce ($C_L$). However, because the flap introduces a drag deficit, the overall **Lift-to-Drag ($L/D$) ratio was worse than the wing without the Gurney Flap**. The shorter flap delivered a more balanced performance.

<figure>
    <a href="/naoko/assets/images/su2/gurney_flap.png"><img src="/naoko/assets/images/su2/gurney_flap.png" alt="Streamlines around Gurney Flap"></a>
    <figcaption>Figure 3: Streamlines visualization showing the flow structures around the Gurney Flap.</figcaption>
</figure>

### Summary of Results (Total Coefficients)

The table below summarizes the aerodynamic total coefficients and lift-to-drag ratio with and without the Gurney flap for the analised configurations.

| Configuration | **DRS Disabled** <br> $C_L$ | **DRS Disabled** <br> $C_D$ | **DRS Disabled** <br> $L/D$ | **DRS Enabled** <br> $C_L$ | **DRS Enabled** <br> $C_D$ | **DRS Enabled** <br> $L/D$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Gurney 0.02c** | -5.937 | 0.160 | 37.11 | -2.991 | 0.046 | 65.02 |
| **Gurney 0.01c** | -5.870 | 0.156 | 37.63 | -2.867 | 0.041 | 69.93 |
| **No Gurney** | -5.806 | 0.133 | 43.65 | -2.604 | 0.036 | 72.33 |

## Conclusion and Future Work

The CFD investigation successfully quantified the trade-offs of the **DRS (significant drag reduction)** and the **Gurney Flap (downforce gain at the cost of $L/D$)**. However, the 2D modeling approach remains a major limitation, as it excludes crucial 3D effects like ground effects and spanwise flow, which are vital for Formula 1 aerodynamics. Future work requires expanding this analysis to 3D simulations.

***

### 📄 Comprehensive Technical Report

This report serves as the full documentation for the project, including all setup details and verification analyses.

[**Download Full Technical Report (PDF)**]( /naoko/assets/docs/Final_report_cfd_drs.pdf ){: .btn .btn--primary .btn--large :target="_blank"}
