---
title: "CFD Analysis of Drag Reduction System (DRS) Opening and Gurney Flap Influence using SU2"
date: 2025-11-24
last_modified_at: 2025-11-24T21:20:00+01:00
categories:
  - CFD
  - Engineering
tags:
  - SU2
  - Aerodynamics
# Aggiungi questa linea:
layout: single
# ... il resto ...
  - DRS
  - Gurney Flap
  - Transient Simulation
layout: single
classes: wide
header:
  overlay_image: /assets/images/su2/su2_banner.png # (Immagine di copertina generale)
  [cite_start]caption: "Credit: Francesco Lo Sardo, Gino Martella, Giorgio Pacchione, Davide Ruocchio, Luca Servadio [cite: 5, 6, 7, 8, 9]"
excerpt: "A comprehensive Computational Fluid Dynamics (CFD) study investigating the performance optimization of a Formula 1 rear wing through the deployment of a Drag Reduction System (DRS) and the geometric influence of a Gurney Flap."
---

# Introduction: Problem Statement and Objective 🎯

[cite_start]This work presents a two-dimensional CFD analysis performed with the open-source software **SU2** to numerically investigate the aerodynamic performance of a Formula 1 rear wing[cite: 24, 4]. [cite_start]Rear wings are one of the most impactful components on the aerodynamic performance of an F1 car, with strategies like the Drag Reduction System (DRS) and the Gurney flap being key features[cite: 15, 17].

[cite_start]The primary objective was to understand and reproduce the aerodynamics of these solutions, focusing on the effects of unsteady phenomena upon DRS activation and the effectiveness of the Gurney flap under steady conditions[cite: 25, 26, 27].

## Methodology and Simulation Setup

[cite_start]The rear wing geometry utilized a two-element wing, composed of a mainplane and a DRS flap, both based on S1223 airfoils[cite: 31, 32].

### Computational Domain and Mesh
[cite_start]To simulate the rotation of the DRS flap, a **sliding mesh approach** was employed, where a circular portion of the domain enclosing the DRS profile rotates without intersecting the mainplane[cite: 37, 38, 48]. [cite_start]The mesh itself was generated using an **O-grid approach** to adapt well to the restrictions of the sliding mesh[cite: 63].

[cite_start]**Gurney Flap Modeling:** The Gurney flap was modeled as a rectangular appendage perpendicular to the pressure side of the DRS wing[cite: 41]. [cite_start]Two configurations were tested, with heights of $0.01$ and $0.02$ chords[cite: 42]. [cite_start]Special care was required for the Gurney flap mesh generation due to sharp convex corners, necessitating the use of **transfinite surfaces** instead of automatic boundary layer meshing[cite: 84, 86, 87].

### Visualization of Mesh Topology

[cite_start]The use of a sliding mesh requires dividing the domain into distinct zones that slide against each other[cite: 49].

![Sliding Mesh for Disabled and Enabled DRS]( /assets/images/su2/mesh_sliding_close.png )
[cite_start]*Figure 1: Sliding mesh topology for the disabled (left) and enabled (right) DRS configurations[cite: 65].*

### Numerical Methods and Turbulence

[cite_start]To account for expected high velocities (reaching Mach numbers over 0.3) in regions of high curvature, the **compressible form of the RANS equations** was employed[cite: 107, 108]. [cite_start]The two-equation **SST $k-\omega$ turbulence model** was selected as it is better suited for flows close to walls and in regions where separated flow might occur[cite: 127, 128].

## Key Results: Transient Effects of DRS

[cite_start]The total angle swept by the DRS is $\Delta\alpha=40^{\circ}$, executed over a time window of $\Delta t=0.2$ s[cite: 149]. The unsteady analysis provided crucial insights into the transient phase during this activation.

| Finding | Detail |
| :--- | :--- |
| **Drag Reduction** | [cite_start]Upon activation, the DRS resulted in a substantial reduction in both downforce ($\Delta C_{L}$) and drag ($\Delta C_{D}$)[cite: 655, 461]. [cite_start]The total drag was reduced by approximately $72.93\%$ and total lift by $55.15\%$ (values noted as likely overestimated due to 2D limitations [cite: 463]). |
| **Transient Duration**| [cite_start]The transient phenomena, while temporally brief, persisted for approximately **one second** following the initiation of motion[cite: 536, 659]. [cite_start]This represents 10-20% of the typical duration of a DRS activation zone on track[cite: 660]. |
| **Transient Spikes** | [cite_start]The evolution of the aerodynamic coefficients showed a significant spike at the impulsive start of the motion[cite: 489]. |
| **Vortex Influence** | [cite_start]The opening of the DRS flap injects a vortex into the flow that temporarily makes the lift coefficient **overshoot** its steady-state value (higher downforce) and the drag coefficient **undershoot** (temporarily providing a positive forward thrust)[cite: 537, 540, 541]. |

### Visualization of Transient Coefficients

![Evolution of Aerodynamic Coefficients over Time]( /assets/images/su2/lift_coefficient.png )
[cite_start]*Figure 13: Evolution of the aerodynamic coefficients during the three phases: (a) Disabled, (b) Opening, and (c) Enabled DRS[cite: 531].*

## Key Results: Gurney Flap Influence

[cite_start]The Gurney flap was tested under steady conditions for both DRS enabled and disabled configurations[cite: 604].

[cite_start]The presence of the Gurney flap significantly increases the pressure on the pressure side near the trailing edge, leading to the production of **more downforce**[cite: 606, 607]. [cite_start]However, being a bluff geometry, it also introduces a drag deficit[cite: 610, 644].

### Lift-to-Drag Ratio Comparison (Total Coefficients)

[cite_start]The table below summarizes the effect on the total lift-to-drag ratio ($L/D$) compared to the "No Gurney flap" case[cite: 650].

| Configuration | $C_L$ (Total) | $C_D$ (Total) | $L/D$ Ratio |
| :--- | :--- | :--- | :--- |
| **No Gurney flap** (DRS Disabled) | -5.806 | 0.133 | **43.65** |
| **Gurney $0.01\times0.0026$** (DRS Disabled)| [cite_start]-5.870 [cite: 649] | [cite_start]0.156 [cite: 649] | [cite_start]37.63 [cite: 649] |
| **Gurney $0.02\times0.0026$** (DRS Disabled)| [cite_start]-5.937 [cite: 649] | [cite_start]0.160 [cite: 649] | [cite_start]37.11 [cite: 649] |

[cite_start]The results showed that the total $L/D$ ratio was worse than the case without the Gurney flap[cite: 645]. [cite_start]The shorter Gurney flap ($0.01\times0.0026$) demonstrated a more balanced performance compared to the taller one[cite: 664].

## Conclusion and Future Work

[cite_start]The study demonstrated the effectiveness of the DRS in reducing aerodynamic drag and provided insights into the transient vortex dynamics upon activation[cite: 655, 657]. [cite_start]It confirmed that the Gurney flap enhances lift, but the total lift-to-drag ratio decreases, suggesting its application depends on specific race strategies[cite: 663, 645].

### Limitation of 2D Modeling
[cite_start]It is crucial to acknowledge that the **2D modeling approach is a significant limitation** for a Formula 1 rear wing, as it excludes key 3D phenomena such as ground effects, spanwise flow, and interactions with the vehicle body[cite: 411, 666, 667]. [cite_start]Future implementations should prioritize extending the analysis to **3D simulations**[cite: 670].

***

### 📄 Comprehensive Technical Report

This report serves as the full documentation for the project, including all setup details, verification analyses (domain and grid independence), and detailed coefficient data.

[**Download Full Technical Report (PDF)**]( /assets/docs/Final_report_cfd_drs.pdf ){: .btn .btn--primary .btn--large :target="_blank"}

***

**Prossimi passi:**

1.  **Commit:** Esegui il commit del file `2025-11-24-drs-project.md` (e assicurati che le immagini e il PDF siano caricati con i nomi corretti).
2.  **Verifica:** Controlla che il post appaia correttamente sul tuo sito.

Quando hai finito con questo progetto, possiamo procedere con l'impostazione di **OpenFOAM**!
