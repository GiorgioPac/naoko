---
title: "CFD Analysis of Drag Reduction System (DRS) Opening and Gurney Flap Influence using SU2"
categories:
  - CFD
  - Engineering
tags:
  - SU2
  - Aerodynamics
  - DRS
  - Gurney Flap
  - Transient Simulation
  - project
layout: single
classes: wide
header:
  overlay_image: /naoko/assets/images/su2/su2_banner.png
  caption: "Credit: Francesco Lo Sardo, Gino Martella, Giorgio Pacchione, Davide Ruocchio, Luca Servadio"
excerpt: "A comprehensive Computational Fluid Dynamics (CFD) study investigating the aerodynamic optimization of a Formula 1 rear wing through the deployment of a Drag Reduction System (DRS) and the geometric influence of a Gurney Flap."
---

# Introduction: Problem Statement and Objective 🎯

This project utilized the open-source CFD solver **SU2** to perform a two-dimensional RANS analysis of a Formula 1 rear wing. The primary goal was to quantify the aerodynamic performance gains achieved by two key solutions: the active **Drag Reduction System (DRS) deployment** and the addition of a passive **Gurney Flap**. The study included both steady and unsteady analysis to capture transient effects.

## Methodology and Simulation Setup

The simulation focused on a two-element wing (mainplane and DRS flap). To accurately model the $40^{\circ}$ rotation of the DRS flap, a **Sliding Mesh approach** was employed, allowing the mesh around the flap to move dynamically while the rest of the domain remained stationary.

We used the **compressible form of the RANS equations** with the **SST $k-\omega$ turbulence model** to ensure high fidelity near the walls and in separated flow regions. Special geometric attention was required to model the Gurney Flap, necessitating the use of **transfinite surfaces** for the boundary layer mesh.

### Visualization of Sliding Mesh Topology

The images below illustrate the mesh topology. A key challenge was maintaining the boundary layer integrity at the interface between the rotating and stationary zones.

<figure class="half">
    <a href="/naoko/assets/images/su2/mesh_sliding_close.png"><img src="/naoko/assets/images/su2/mesh_sliding_close.png" alt="Mesh DRS Closed"></a>
    <a href="/naoko/assets/images/su2/mesh_sliding_open.png"><img src="/naoko/assets/images/su2/mesh_sliding_open.png" alt="Mesh DRS Open"></a>
    <figcaption>Figure 1: Comparison of the sliding mesh interface for the disabled (left) and enabled (right) DRS configurations.</figcaption>
</figure>

## Key Results: Transient Effects and Gurney Flap

### 1. Transient Effects (DRS Activation)
The $40^{\circ}$ DRS opening occurs over a rapid $0.2$ second window. The **unsteady analysis** was crucial as it revealed that the aerodynamic performance does not stabilize immediately:
* **Transient Duration:** Aerodynamic coefficients continue to change for approximately **one second** after the motion stops, highlighting that transient effects impact performance for 10-20% of the duration the DRS is enabled on track.
* **Vortex Influence:** During this transient phase, the lift coefficient temporarily **overshoots** its steady-state value, resulting in a brief moment of higher downforce and negative drag, beneficial for acceleration.

<figure class="half">
    <a href="/naoko/assets/images/su2/lift_coefficient.png"><img src="/naoko/assets/images/su2/lift_coefficient.png" alt="Lift Coefficient Evolution"></a>
    <a href="/naoko/assets/images/su2/drag_coefficient.png"><img src="/naoko/assets/images/su2/drag_coefficient.png" alt="Drag Coefficient Evolution"></a>
    <figcaption>Figure 2: Transient evolution of Lift (left) and Drag (right) coefficients during the DRS opening phase.</figcaption>
</figure>

### 2. Gurney Flap Trade-Off
The Gurney Flap (tested at $0.01c$ and $0.02c$) was confirmed to significantly increase downforce ($C_L$). However, because the flap introduces a drag deficit, the overall **Lift-to-Drag ($L/D$) ratio was worse** than the wing without the Gurney Flap. The shorter flap ($0.01c$) delivered a more balanced performance.

![Gurney Flap Flow]( /naoko/assets/images/su2/gurney_flap.png )
*Figure 3: Streamlines visualization showing the flow structures around the Gurney Flap.*

### Summary of Results (Total Coefficients)

| Configuration | $C_L$ (Total) | $C_D$ (Total) | $L/D$ Ratio |
| :--- | :--- | :--- | :--- |
| **No Gurney flap** | -5.806 | 0.133 | **43.65** |
| **Gurney $0.01c$** | -5.870 | 0.156 | 37.63 |
| **Gurney $0.02c$** | -5.937 | 0.160 | 37.11 |

## Conclusion and Future Work

The CFD investigation successfully quantified the trade-offs of the DRS (significant drag reduction) and the Gurney Flap (downforce gain at the cost of $L/D$). However, the **2D modeling approach remains a major limitation**, as it excludes crucial 3D effects like ground effects and spanwise flow, which are vital for Formula 1 aerodynamics. Future work requires expanding this analysis to 3D simulations.

***

### 📄 Comprehensive Technical Report

This report serves as the full documentation for the project, including all setup details and verification analyses.

[**Download Full Technical Report (PDF)**]( /naoko/assets/docs/Final_report_cfd_drs.pdf ){: .btn .btn--primary .btn--large :target="_blank"}
