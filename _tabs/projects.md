---

icon: fas fa-flask
order: 2



---

## 1.  Particle Dynamics within a Tornado-like Vortex (Doctoral Research)

### Flow Configuration
A tornado-like vortex is a complex flow characterized by **radial inflow**, **intense azimuthal swirl**, and **upward axial transport**. The dominant non-dimensional parameter governing the structure and stability of such flows is the **swirl ratio**, defined as the ratio of angular momentum to radial inflow rate.

- **Low swirl ratios:**  
  The vortex core exhibits a laminar axial jet that undergoes **vortex breakdown** at a finite height.

{% include embed/youtube.html id='do4Ew8c-nGM' w='48%' %}

- **High swirl ratios:**  
  Vortex breakdown occurs at or near the surface, resulting in a fully turbulent vortex core throughout the domain.

{% include embed/youtube.html id='lAxdf9ytp-U' w='48%' %}

---

### Particle Dynamics and Flow–Particle Interaction
The dynamics of **suspended sand particles** within the vortex are strongly coupled to the turbulent flow field. The presence of particles can significantly modify the underlying vortex dynamics.

Initial studies indicate that **vortex breakdown is suppressed in the presence of particles**, a phenomenon captured through **two-way coupled particle–flow interactions**. Key features of the particle model include:

- High particle **coefficients of restitution**
- Large **spring stiffness constants** for collision modeling
- Formation and evolution of a **particle bed** at the surface
- Entrainment, suspension, and clustering of particles within the vortex

{% include embed/youtube.html id='lM57F5_2UQY' w='48%' %}

---

### Computational Methods
- **CFD solver:** `Nek5000`[^nek5000] 
- **Multiphase flow model for particle-laden flow:** Euler–Lagrange formulation within Nek5000 using `ppiclF`[^ppiclf], allowing particles to advance concurrently with the flow solver
- **Physics captured:**
  - Particle–particle collisions using elastic spring-damper models
  - Particle friction 
  - Gravitational force on particles
  - Fluid-induced forces and moments on particles - Drag, lift and hydrodynamic torque
  - Inter-phase momentum exchange between particles and fluid
  - Influence of flowfield due to the non-negligible volume occupied by finite-sized particles

---

### High-Performance Computing
- MPI-based parallel simulation runs
- Optimized simulations compiled and run with **Intel compilers** on supercomputers (Stampede3, ASU Sol supercomputer)
- Production runs efficiently scaled up to **1000 CPUs**




---
## 2. Ventilated capsules for sweat measurements (MS Thesis project)

Dynamics of sweat evaporation on skin ranges from in-pore sweating, sweat droplets to thin film of sweat puddle. Sweating is an efficient cooling mechaninsm that helps us to survive in extreme conditions. Sweating is often measured through a device called ventilated capsules on foreheads, palms etc. Onset of sweating and sweat droplet formation can be visualized through MWIR. By combining both of these tools together in a new ventilated capsule design with an IR window, this paves the way to explore sweat evaporation dynamics. An imporved understanding of sweat evaporation mechanism will help to optimize cooling of body at extreme heat conditions and design clothing that can promote sweat evaporation.


- Developed, tested and demonstrated custom ventilated capsule with viewable window to measure sweat evaporation rate from skin and simultaneously visualize sweat droplets using MWIR imaging technique 



![im1](images/im1.jpg)


- Artificial sweating skin



[^nek5000]: [Nek5000](https://nek5000.mcs.anl.gov) is a fast and scalable open source computational fluid dynamics (CFD) solver that uses spectral element method (SEM) and [NekRS](https://github.com/Nek5000/NekRS) is its GPU variant. They both target large scale high fidelity turbulence simulations on supercomputers.

[^ppiclf]: [ppiclF](https://dpzwick.github.io/ppiclF-doc/index.html) is a parallel particle-in-cell library written in Fortran. ppiclF can be linked to the incompressible, spectral element, fluid solver Nek5000.