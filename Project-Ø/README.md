# Project Zero — Canonical Viscous Flows

Project Zero is a five-model introduction to steady, incompressible, fully developed laminar flow. Together, the simulations separate the effects of wall motion, pressure forcing, and cross-sectional geometry.

## Model catalog

| No. | Simulation | Driving mechanism | Geometry | Reference behavior |
| ---: | --- | --- | --- | --- |
| 01 | [Couette flow](./01-couette-flow/) | Moving wall | Infinite parallel plates | Linear velocity profile |
| 02 | [Plane Poiseuille flow](./02-plane-poiseuille-flow/) | Pressure gradient | Infinite parallel plates | Parabolic velocity profile |
| 03 | [Circular-pipe Poiseuille flow](./03-circular-pipe-poiseuille-flow/) | Pressure gradient | Circular pipe | Axisymmetric parabolic profile |
| 04 | [Rectangular Couette flow](./04-rectangular-couette-flow/) | Moving wall | Rectangular channel | Viscous shear with side-wall effects |
| 05 | [Rectangular Couette–Poiseuille flow](./05-rectangular-couette-poiseuille-flow/) | Moving wall + pressure gradient | Rectangular channel | Superposed shear- and pressure-driven flow |

## Shared physical regime

For a Newtonian fluid with constant density and viscosity, the governing equations are

$$
\nabla \cdot \mathbf{u}=0,
$$

$$
\rho(\mathbf{u}\cdot\nabla)\mathbf{u}=-\nabla p+\mu\nabla^2\mathbf{u}.
$$

In the creeping-flow or fully developed limit, the inertial term is negligible or vanishes, leaving a balance between viscous stresses, pressure forcing, and moving-wall boundary conditions.

## Suggested validation workflow

1. Inspect the model parameters, geometry, materials, boundary conditions, mesh, and study before solving.
2. Plot the streamwise velocity over a representative cross-section.
3. Compare the numerical profile with the analytical limit described in the simulation README.
4. Refine the mesh and confirm that the quantity of interest changes negligibly.
5. Record the COMSOL version and any parameter changes when reporting results.

## File format

All simulations are COMSOL Multiphysics model files (`.mph`). Each model is self-contained in its numbered folder with a short technical guide.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../LICENSE).
