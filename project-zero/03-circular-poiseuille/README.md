# 03 — Circular-Pipe Poiseuille Flow

This three-dimensional model represents steady, incompressible, pressure-driven laminar flow through a straight circular pipe.

## Physics

For pipe radius $R$ and constant streamwise pressure gradient $dp/dx$, the fully developed axial velocity is

$$
u(r)=-\frac{1}{4\mu}\frac{dp}{dx}\left(R^2-r^2\right).
$$

The profile is axisymmetric and parabolic. The Hagen–Poiseuille flow rate is

$$
Q=-\frac{\pi R^4}{8\mu}\frac{dp}{dx},
$$

and the centerline velocity is twice the cross-sectional mean velocity.

## What to check

- No slip at the pipe wall
- Axisymmetry of the solution
- A parabolic radial velocity profile
- $u_{\max}/\bar{u}=2$ in the fully developed region
- Agreement between computed and analytical flow rate

## Model file

`circular-pipe-poiseuille-flow.mph`

Open the model in COMSOL Multiphysics, review all parameters and units, compute the study, and evaluate the axial velocity on a downstream cross-section away from entrance effects.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../../LICENSE).
