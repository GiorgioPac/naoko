---
title: "Aerodynamic Optimization of Car Cargo Boxes: OpenFOAM CFD vs. Wind Tunnel Validation"
categories:
  - CFD
  - Automotive
tags:
  - OpenFOAM
  - Wind Tunnel
  - Aerodynamics
  - Experimental Validation
  - Fuel Consumption
  - project
mathjax: true
layout: single
classes: wide
header:
  # Nessuna immagine di sfondo qui, solo il credito generale se serve
  caption: "Credit: D. Terraneo, G. Pacchione, M. Maddonini, P. Sarti"
excerpt: "A comparative study combining OpenFOAM CFD simulations and wind tunnel testing to minimize drag and fuel consumption of an Audi A4 equipped with various cargo box configurations."
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

# Introduction: The Aerodynamic Challenge 🎯

The addition of a cargo box to a vehicle represents a classic aerodynamic trade-off: gaining storage space at the cost of efficiency. The objective of this project was to investigate how different cargo box configurations alter the airflow around an **Audi A4 Sedan**, specifically looking for a design that minimizes aerodynamic drag ($C_D$) and, consequently, fuel consumption.

The study was conducted using a dual approach: **Computational Fluid Dynamics (CFD)** with OpenFOAM to visualize the flow physics, and **Experimental Testing** in a wind tunnel to validate the results.

## Methodology

The simulation setup was designed to capture the complex wake interactions caused by the bluff body of the box.

* **Numerical Analysis (OpenFOAM):** We performed steady-state RANS simulations using the `simpleFoam` solver and the $k-\omega$ SST turbulence model.
* **Experimental Validation:** A 1:15 scale model of the car was 3D printed and tested in a wind tunnel equipped with a force balance to validate the numerical trends.

## Qualitative Analysis of Flow Physics

### Impact of Box Placement on the Wake

Introducing a standard box on the roof significantly disrupts the vehicle's aerodynamics. The box acts as a bluff body in the free stream, forcing the flow to separate and creating a massive, low-pressure wake behind the car. This pressure difference is the primary driver of increased drag.

In contrast, placing the box at the **rear of the vehicle ("Back Box")** places it within the car's existing "dead air" zone. As shown in the velocity field comparison below, the Back Box maintains a much cleaner flow pattern similar to the car's native aerodynamics.

<figure>
    <a href="/naoko/assets/images/openfoam/velocity.png"><img src="/naoko/assets/images/openfoam/velocity.png" alt="Velocity Magnitude Comparison"></a>
    <figcaption>Figure 1: Visualization of the velocity magnitude. The roof box (top) generates a significantly larger and more turbulent wake compared to the streamlined flow of the back-mounted solution (bottom).</figcaption>
</figure>

### Visualization of Turbulence (Q-Criterion)

To understand the noise and drag generation, we analyzed the vortical structures using the Q-Criterion. The roof box generates intense horseshoe vortices originating from the gap between the box and the roof. The back box, instead, keeps the flow attached over the roofline.

<figure class="half">
    <a href="/naoko/assets/images/openfoam/q1.jpeg"><img src="/naoko/assets/images/openfoam/q1.jpeg" alt="Q-Criterion Roof Box"></a>
    <a href="/naoko/assets/images/openfoam/q2.jpeg"><img src="/naoko/assets/images/openfoam/q2.jpeg" alt="Q-Criterion Back Box"></a>
    <figcaption>Figure 2: Comparison of turbulent structures. The roof configuration (left) shows massive vortex shedding compared to the cleaner flow of the rear configuration (right).</figcaption>
</figure>

## Experimental Validation and Fuel Consumption

The wind tunnel tests confirmed the trends observed in the CFD simulations. Despite the complexities of scaling, the force balance measurements verified that the **Back Box** is the superior aerodynamic solution.

The aerodynamic penalty of a roof box translates directly into fuel consumption. The study concluded that choosing a **rear-mounted solution** effectively neutralizes the penalty of the extra load, offering significant fuel savings over long distances.

<figure>
    <a href="/naoko/assets/images/openfoam/wind_tunnel.jpg"><img src="/naoko/assets/images/openfoam/wind_tunnel.jpg" alt="Wind Tunnel Setup"></a>
    <figcaption>Figure 3: The 3D-printed Audi A4 model mounted in the wind tunnel for experimental force measurements.</figcaption>
</figure>

***

### 📄 Full Project Report

For a detailed breakdown of the setup, mesh convergence analysis, and experimental data, you can download the complete report.

[**Download Final Report (PDF)**]( /naoko/assets/docs/report_finale_atv.pdf ){: .btn .btn--primary .btn--large :target="_blank"}
