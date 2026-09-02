# 05 — Rectangular-Channel Couette–Poiseuille Flow

This model combines tangential wall motion with a streamwise pressure gradient in a rectangular channel. It demonstrates the linear superposition of shear-driven and pressure-driven contributions in the steady laminar regime.

## Physics

For the ideal parallel-plate limit with stationary lower wall, upper-wall speed $U$, gap $h$, and constant $dp/dx$, the velocity profile is

$$
u(y)=U\frac{y}{h}-\frac{1}{2\mu}\frac{dp}{dx}\,y(h-y).
$$

The first term is Couette flow and the second is plane Poiseuille flow. In a finite rectangular cross-section, side-wall no-slip conditions modify this ideal profile.

## What to check

- Correct direction and magnitude of the moving-wall velocity
- Correct sign and magnitude of the imposed pressure gradient
- No slip on stationary walls
- Side-wall effects in the cross-sectional contours
- Whether opposing wall and pressure forcing produces a stagnation plane or local reverse flow
- Mesh independence of flow rate and wall shear

## Model file

`rectangular-couette-poiseuille-flow.mph`

Open the model in COMSOL Multiphysics, review all parameters and units, compute the study, and compare a central cross-gap profile with the ideal superposed solution above.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../../LICENSE).
