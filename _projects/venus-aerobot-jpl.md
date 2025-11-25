---
title: "Aerodynamic Characterization and Passive Stability Analysis of the Venus Aerobot through CFD and Overset Methods"
categories:
  - Aerospace
  - Planetary Science
tags:
  - NASA JPL
  - OpenFOAM
  - DDES
  - Fluid-Structure Interaction
  - Venus
  - project
mathjax: true
layout: single
classes: wide
date: 2025-11-26
excerpt: "Master's Thesis project in collaboration with NASA JPL. Advanced CFD investigation (DDES) and Fluid-Structure Interaction analysis of a robotic balloon for Venus exploration."
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

# Introduction: Exploring Venus 🪐

Understanding the evolution of Venus is a central objective in planetary science. The atmospheric region between **52 and 62 km** above the surface offers Earth-like conditions, making it ideal for long-duration aerial exploration using balloon-based platforms like the **Venus Aerobot**.

<figure>
    <a href="/naoko/assets/images/jpl/venus_aerobot.jpg"><img src="/naoko/assets/images/jpl/venus_aerobot.jpg" alt="Venus Aerobot Concept"></a>
    <figcaption>Figure 1: Concept art of the Venus Aerobot. Image Credit: NASA/JPL-Caltech.</figcaption>
</figure>

## Methodology: Advanced CFD (DDES)

Venus presents unique challenges, including super-rotating zonal winds and strong vertical gusts. To capture the complex unsteady aerodynamics of the Aerobot (treated as a bluff body), **Delayed Detached Eddy Simulations (DDES)** were performed using OpenFOAM.

<figure class="half">
    <a href="/naoko/assets/images/jpl/vertical_wind_1.png"><img src="/naoko/assets/images/jpl/vertical_wind_1.png" alt="Vertical Wind Simulation 1"></a>
    <a href="/naoko/assets/images/jpl/vertical_wind_2.png"><img src="/naoko/assets/images/jpl/vertical_wind_2.png" alt="Vertical Wind Simulation 2"></a>
    <figcaption>Figure 2: CFD visualization of vertical wind effects on the Aerobot hull.</figcaption>
</figure>

This approach allowed for the accurate characterization of flow separation and wake dynamics.

<figure>
    <a href="/naoko/assets/images/jpl/vertical_q.png"><img src="/naoko/assets/images/jpl/vertical_q.png" alt="Q-Criterion Visualization"></a>
    <figcaption>Figure 3: Visualization of vortical structures using Q-Criterion.</figcaption>
</figure>

## Fluid-Structure Interaction (FSI)

The final phase focused on the **Fluid-Structure Interaction (FSI)** to evaluate the passive stability of the Aerobot. The system was modeled using an **overset mesh** technique coupled with a mass-spring dynamic model to simulate the balloon's response to vertical gusts.

<figure>
    <a href="/naoko/assets/images/jpl/aerobot_springs.png"><img src="/naoko/assets/images/jpl/aerobot_springs.png" alt="Mass-Spring Model Setup"></a>
    <figcaption>Figure 4: Schematic of the mass-spring model used for FSI simulations.</figcaption>
</figure>

Below are the resulting pressure and velocity fields showing the Aerobot's interaction with the flow during vertical motion.

<figure class="third">
    <a href="/naoko/assets/images/jpl/fsi_1.png"><img src="/naoko/assets/images/jpl/fsi_1.png" alt="FSI Field 1"></a>
    <a href="/naoko/assets/images/jpl/fsi_2.png"><img src="/naoko/assets/images/jpl/fsi_2.png" alt="FSI Field 2"></a>
    <a href="/naoko/assets/images/jpl/fsi_3.png"><img src="/naoko/assets/images/jpl/fsi_3.png" alt="FSI Field 3"></a>
    <figcaption>Figure 5: Sequence of pressure and velocity fields during the FSI simulation.</figcaption>
</figure>

***

<div class="notice--warning">
  <h4>⚠️ Disclaimer & Copyright</h4>
  <p>No sensitive or classified information regarding NASA/JPL missions has been disclosed in this portfolio. All data presented is derived from publicly available models or generic simulations.</p>
  <p>Unless explicitly stated otherwise (e.g., Image Credits to NASA/JPL-Caltech), all content, images, and simulations on this page are <strong>Copyright © Giorgio Pacchione</strong>. All rights reserved.</p>
</div>
