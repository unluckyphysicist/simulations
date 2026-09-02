# Project Zero - Canonical Viscous Flows

Project Zero is a five-model study of steady, incompressible, fully developed laminar flow. The collection separates the effects of wall motion, pressure forcing, and cross-sectional geometry, then combines them in a finite rectangular channel.

## Model catalog

| No. | Simulation | Driving mechanism | Geometry | Analytical benchmark |
| ---: | --- | --- | --- | --- |
| 01 | [Couette flow](./01-couette-flow/) | Moving wall | Infinite parallel plates | Linear velocity profile |
| 02 | [Plane Poiseuille flow](./02-plane-poiseuille-flow/) | Pressure gradient | Infinite parallel plates | Parabolic velocity profile |
| 03 | [Circular-pipe Poiseuille flow](./03-circular-pipe-poiseuille-flow/) | Pressure gradient | Circular pipe | Hagen-Poiseuille profile |
| 04 | [Rectangular Couette flow](./04-rectangular-couette-flow/) | Moving wall | Rectangular channel | Finite-width Fourier series |
| 05 | [Rectangular Couette-Poiseuille flow](./05-rectangular-couette-poiseuille-flow/) | Moving wall and pressure gradient | Rectangular channel | Superposed finite-width series |

## Analytical solution for Model 05

The full derivation is provided in:

[Rectangular Couette-Poiseuille Flow - Analytical Solution (PDF)](./Rectangular%20Couette-Poiseuille%20flow%20Analytical%20Solution.pdf)

The corresponding [Model 05 README](./05-rectangular-couette-poiseuille-flow/) states the exact series solution for the repository geometry and gives validation checks for COMSOL.

## Shared physical model

For a Newtonian fluid with constant density $\rho$ and dynamic viscosity $\mu$,

$$
\nabla\cdot\mathbf{u}=0,
$$

$$
\rho(\mathbf{u}\cdot\nabla)\mathbf{u}
=-\nabla p+\mu\nabla^2\mathbf{u}.
$$

For steady, unidirectional, fully developed flow,

$$
\mathbf{u}=u(y,z)\,\mathbf{e}_x,
$$

so the convective term vanishes and the streamwise momentum equation becomes a two-dimensional boundary-value problem over the channel cross-section.

## Suggested validation workflow

1. Inspect the geometry, parameters, units, material properties, boundary conditions, mesh, and study before solving.
2. Plot the streamwise velocity over a representative cross-section.
3. Compare the numerical field and volumetric flow rate with the analytical benchmark in the relevant README.
4. Refine the mesh and confirm that the velocity and flow rate are mesh independent.
5. Record the COMSOL version and all parameter changes when reporting results.

For Model 05, compare the series solution and COMSOL result away from the two upper corners, where the moving-wall and stationary-side-wall boundary values are incompatible at a single point.

## File format

All simulations are COMSOL Multiphysics model files (`.mph`). Each numbered folder contains one model and its technical README.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../LICENSE).
