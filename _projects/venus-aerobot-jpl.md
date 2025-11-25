---
title: "Aerodynamic Characterization and Passive Stability Analysis of the Venus Aerobot through CFD and Overset Methods"
categories:
  - Aerodynamics
  - Aerospace
  - Planetary Science
tags:
  - NASA JPL
  - OpenFOAM
  - Fluid-Structure Interaction
  - Venus
  - project
mathjax: true
layout: single
classes: wide
date: 2025-11-25
header:
  overlay_image: /assets/images/jpl/venus.png
  caption: "Image Credit: NASA/JPL-Caltech"
excerpt: "Master's Thesis project developed at NASA JPL. A CFD investigation of the Venus Aerobot employing scale-resolving methods and Fluid-Structure Interaction through Chimera meshes."
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

Understanding the evolution of Venus is a central objective in planetary science. Scientists believe that the planet may once have hosted liquid water and conditions similar to those on Earth. However, the planet underwent a dramatic climatic transformation, possibly driven by volcanic resurfacing, atmospheric collapse, or photochemical processes.

Today, Venus is enveloped by a dense atmosphere composed almost entirely of carbon dioxide ($\text{CO}_2$) and interspersed with clouds of sulphuric acid ($\text{H}_2\text{SO}_4$). This produces surface temperatures exceeding $460^\circ\text{C}$ and pressures more than ninety times those at sea level on Earth. Beneath the persistent cloud cover, the landscape is characterised by extensive volcanic structures and deformed mountainous regions. This hostile setting, shaped by an uncontrolled greenhouse effect, has rendered Venus one of the most extreme environments in the Solar System.

### The "Habitable" Layer and Atmospheric Dynamics

Nevertheless, the atmospheric layer located between **52 and 62 km** above the surface exhibits temperature and pressure conditions comparable to those at sea level on Earth. Within this region, temperatures range from $30$ to $70^\circ\text{C}$, values that could potentially accommodate hardy forms of life, such as extremophile microbes.

At the upper boundary of the cloud deck, another intriguing phenomenon occurs: persistent dark streaks appear, the nature of which remains unexplained. These features are capable of absorbing ultraviolet radiation. The most plausible explanations point to fine particles, ice crystals, or chemical compounds such as iron chloride ($\text{FeCl}_3$).

The planet’s atmosphere is further distinguished by the phenomenon of **super-rotation**, whereby the upper atmosphere completes a full circuit around the planet in approximately **4 Earth days**. This stands in stark contrast to Venus’s slow retrograde rotation, which requires **243 Earth days** to complete. Taken together, these factors indicate a rich and dynamic meteorological system that warrants further investigation.

### The Case for Aerial Exploration

Balloon based exploration has once again emerged as a **promising strategy** for planetary missions, particularly in environments like Venus where traditional landers face significant operational constraints. By utilising buoyancy rather than propulsion for lift, balloons or **aerobots** can accomplish long-duration missions with minimal energy consumption.

This capability is especially beneficial on Venus, where periods of darkness may last up to $70 \text{ hours}$, posing serious challenges for solar energy management.

<figure>
    <a href="/naoko/assets/images/jpl/venus_aerobot.jpg"><img src="/naoko/assets/images/jpl/venus_aerobot.jpg" alt="Venus Aerobot Concept"></a>
    <figcaption>Figure 1: A prototype aerial robotic balloon, or aerobot, is readied for a sunrise test flight at Black Rock Desert, Nevada, in July 2022, by team members from JPL and Near Space Corporation. The aerobot successfully completed two flights, demonstrating controlled altitude flight. Image Credit: NASA/JPL-Caltech.</figcaption>
</figure>

## Aerodynamic Characterization and Modeling Strategy

Aerodynamics is a pivotal factor in the operational success of scientific balloons. During flight, the platform is subjected to complex aerodynamic forces and moments that dictate its trajectory, stability, and overall motion within the atmosphere.

The primary objective of this project is to investigate the aerodynamics of the **Venus Aerobot** under a wide range of wind and inflation conditions, aiming to fully characterize its aerodynamic coefficients and dynamic response.

### High-Fidelity CFD: Resolving the Scales
The study was performed using the open-source software **OpenFOAM**. To achieve a high level of physical accuracy, scale-resolving simulations, specifically **Delayed Detached Eddy Simulations (DDES)** were employed. Unlike standard RANS models, DDES allows for a detailed characterization of:
* The complex **turbulent structures** in the wake.
* The dominant unsteady frequencies associated with vortex shedding and wind interactions.

<figure>
  <div style="display: flex; gap: 10px; margin-bottom: 10px;">
    <a href="/naoko/assets/images/jpl/vertical_wind_1.png" style="width: 50%;">
      <img src="/naoko/assets/images/jpl/vertical_wind_1.png" alt="Vertical Wind 1">
    </a>
    <a href="/naoko/assets/images/jpl/vertical_wind_2.png" style="width: 50%;">
      <img src="/naoko/assets/images/jpl/vertical_wind_2.png" alt="Vertical Wind 2">
    </a>
  </div>

  <a href="/naoko/assets/images/jpl/horizontal_wind.png">
    <img src="/naoko/assets/images/jpl/horizontal_wind.png" alt="Horizontal Wind">
  </a>

  <figcaption>Figure 2: CFD visualization of wind effects. Top: Vertical wind interaction on the Aerobot. Bottom: Horizontal wind interaction on the Aerobot. Image credits: Giorgio Pacchione.</figcaption>
</figure>

<figure class="half">
    <a href="/naoko/assets/images/jpl/vertical_q.png"><img src="/naoko/assets/images/jpl/vertical_q.png" alt="Q-Criterion Vertical"></a>
    <a href="/naoko/assets/images/jpl/horizontal_q.png"><img src="/naoko/assets/images/jpl/horizontal_q.png" alt="Q-Criterion Horizontal"></a>
    <figcaption>Figure 4: Vortical structures (Q-Criterion) generated by vertical winds (left) vs horizontal winds (right). Images Credits: Giorgio Pacchione</figcaption>
</figure>

### System Dynamics via Chimera Methods
Following the aerodynamic characterization, the project advanced to dynamic modeling. A **Overset mesh approach** was implemented to simulate the **Fluid-Structure Interaction**. This methodology was essential to accurately characterize the vertical dynamics of the system, allowing the balloon to move freely through the mesh grid in response to aerodynamic forces.

Overall, this work represents a novel contribution to the field of scientific ballooning, introducing state of the art methodologies and providing new insights into the stability of aerial platforms on Venus.

<figure class="third">
    <a href="/naoko/assets/images/jpl/fsi_1.png"><img src="/naoko/assets/images/jpl/fsi_1.png" alt="FSI Field 1"></a>
    <a href="/naoko/assets/images/jpl/fsi_2.png"><img src="/naoko/assets/images/jpl/fsi_2.png" alt="FSI Field 2"></a>
    <a href="/naoko/assets/images/jpl/fsi_3.png"><img src="/naoko/assets/images/jpl/fsi_3.png" alt="FSI Field 3"></a>
    <figcaption>Figure 6: Sequence of pressure and velocity fields during the FSI simulation to characterize the response under vertical wind gusts. Images Credits: Giorgio Pacchione</figcaption>
</figure>


***

***

<div class="notice--info">
  <h4>💻 Computational Effort & Scope</h4>
  <p>This thesis project demanded extensive research work and massive high-performance computational resources. Only a few and general information regarding the project scope, methodology, and qualitative results is presented here.</p>
</div>

<div class="notice--warning">
  <h4>⚠️ Disclaimer & Copyright</h4>
  <p>No sensitive or classified information regarding NASA/JPL missions has been disclosed in this portfolio. All data presented is derived from publicly available models or generic simulations.</p>
  <p>Unless explicitly stated otherwise (e.g., Image Credits to NASA/JPL-Caltech), all content, images, and simulations on this page are <strong>Copyright © Giorgio Pacchione</strong>. All rights reserved.</p>
</div>
