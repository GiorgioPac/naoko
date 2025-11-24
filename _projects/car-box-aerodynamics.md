---
title: "Aerodynamic study of Car Cargo Boxes: OpenFOAM CFD and Wind Tunnel Validation"
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
  caption: "Credit: G. Pacchione"
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

The addition of a cargo box to a vehicle represents a classic aerodynamic trade-off: gaining storage space at the cost of efficiency. The objective of this project was to investigate how different cargo box configurations alter the aerodynamic performances around an **Audi A4 Sedan**, specifically looking for a design that minimizes aerodynamic drag and, consequently, fuel consumption.

The study was conducted using a dual approach: **CFD** with OpenFOAM, and **Wind Tunnel Testing** to validate the results.

## Methodology

The study has been conducted following two paths:

* **Numerical Analysis (OpenFOAM):** We performed steady-state RANS simulations using the `simpleFoam` solver and the $k-\omega$ SST turbulence model.
* **Experimental Validation:** A 1:15 scale model of the car was 3D printed and tested in a wind tunnel equipped with a force balance to validate the numerical trends.

## Qualitative Analysis of Flow Physics

### Impact of Box Placement on the Wake

Introducing a standard box on the roof significantly disrupts the vehicle's aerodynamics. The box acts as a bluff body in the free stream, forcing the flow to separate and creating a massive, low-pressure wake behind the car. This pressure difference is the primary driver of increased drag.

<figure>
    <a href="/naoko/assets/images/openfoam/velocity.png"><img src="/naoko/assets/images/openfoam/velocity.png" alt="Velocity Magnitude Comparison"></a>
    <figcaption>Figure 1: Visualization of the velocity magnitude influenced by the car boxes.</figcaption>
</figure>

### Visualization of Turbulence (Q-Criterion)

To understand the drag generation, we analyzed the vortical structures using the Q-Criterion. The roof box generates intense horseshoe vortices.

<figure class="half">
    <a href="/naoko/assets/images/openfoam/q1.jpeg"><img src="/naoko/assets/images/openfoam/q1.jpeg" alt="Q-Criterion Roof Box"></a>
    <a href="/naoko/assets/images/openfoam/q2.jpeg"><img src="/naoko/assets/images/openfoam/q2.jpeg" alt="Q-Criterion Back Box"></a>
    <figcaption>Figure 2: Visualization of Turbulent structures. </figcaption>
</figure>

## Experimental Validation and Fuel Consumption

The wind tunnel tests confirmed the trends observed in the CFD simulations. 

The aerodynamic penalty of a roof box translates directly into fuel consumption.

<figure>
    <a href="/naoko/assets/images/openfoam/wind_tunnel.jpg"><img src="/naoko/assets/images/openfoam/wind_tunnel.jpg" alt="Wind Tunnel Setup"></a>
    <figcaption>Figure 3: The 3D-printed Audi A4 model mounted in the wind tunnel for experimental force measurements.</figcaption>
</figure>

***

### 📄 Full Project Report

For a detailed breakdown you can download the complete report.

[**Download Final Report (PDF)**]( /naoko/assets/docs/report_finale_atv.pdf ){: .btn .btn--primary .btn--large :target="_blank"}
