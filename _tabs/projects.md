---

icon: fas fa-flask
order: 2



---

## 1.  Particle Dynamics within a Tornado-like Vortex (Doctoral Research)

---

### Particle dynamics in a tornado-like vortex


Tornado-like vortex is a fascinating flow characterized by a radially converging flow that swirls and is advected upwards. A key non-dimensional parameter that controls the dynamics of such flow is called the swirl ratio. Swirl ratio is the ratio of the angular momentum to the radial inflow rate. At low swirl ratios, the core of the vortex has a laminar jet that breaks down at a certain height called vortex breakdown. At higher swirl ratios vortex breakdown occurs at the surface thus the entire vortex core is turbulent.

Entrainment of sand-like particles by a tornado-like vortex is representative of geophysical phenomena called dust devils. The intense cloud of particles generated is strong enough to disturb the flow which is captured in these simulations.

{% include embed/youtube.html id='B9P-on9yb8U' w='48%' %}
{% include embed/youtube.html id='do4Ew8c-nGM' w='48%' %}

### Computational Methods
- **CFD solver:** `Nek5000`[^nek5000] 
- **Multiphase flow model for particle-laden flow:** Euler–Lagrange formulation within Nek5000 using `ppiclF`[^ppiclf], allowing particles to advance concurrently with the flow solver
- **Physics captured:**
  - Influence of flowfield due to the non-negligible volume occupied by finite-sized particles
  - Inter-phase momentum exchange between particles and fluid
  - Particle–particle collisions using elastic spring-damper models
  - Particle friction 
  - Gravitational force on particles
  - Fluid-induced forces and moments on particles - Drag, lift and hydrodynamic torque

- **High-Performance Computing**
  - MPI-based parallel simulation runs
  - Optimized simulations compiled and run with **Intel compilers** on world's top 500 supercomputers (Stampede3, ASU Sol supercomputer)




---
## 2. Ventilated capsules for sweat measurements (MS Thesis project)

Dynamics of sweat evaporation on skin ranges from in-pore sweating, sweat droplets to thin film of sweat puddle. Sweating is an efficient cooling mechaninsm that helps us to survive in extreme conditions. Sweating is often measured through a device called ventilated capsules on foreheads, palms etc. Onset of sweating and sweat droplet formation can be visualized through MWIR. By combining both of these tools together in a new ventilated capsule design with an IR window, this paves the way to explore sweat evaporation dynamics. An imporved understanding of sweat evaporation mechanism will help to optimize cooling of body at extreme heat conditions and design clothing that can promote sweat evaporation.


- Developed, tested and demonstrated custom ventilated capsule with viewable window to measure sweat evaporation rate from skin and simultaneously visualize sweat droplets using MWIR imaging technique 



![im1](images/im1.jpg)



[^nek5000]: [Nek5000](https://nek5000.mcs.anl.gov) is a fast and scalable open source computational fluid dynamics (CFD) solver that uses spectral element method (SEM) and [NekRS](https://github.com/Nek5000/NekRS) is its GPU variant. They both target large scale high fidelity turbulence simulations on supercomputers.

[^ppiclf]: [ppiclF](https://dpzwick.github.io/ppiclF-doc/index.html) is a parallel particle-in-cell library written in Fortran. ppiclF can be linked to the incompressible, spectral element, fluid solver Nek5000.