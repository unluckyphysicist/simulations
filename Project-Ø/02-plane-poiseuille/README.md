# 02 — Plane Poiseuille Flow

This model represents steady, incompressible, pressure-driven flow between two stationary, effectively infinite parallel plates.

## Physics

Let the plates be at $y=0$ and $y=h$, and let $dp/dx$ be a constant streamwise pressure gradient. The fully developed velocity profile is

$$
u(y)=-\frac{1}{2\mu}\frac{dp}{dx}\,y(h-y).
$$

The velocity is zero at the walls and reaches its maximum at the mid-plane. The volumetric flow rate per unit span is

$$
q=-\frac{h^3}{12\mu}\frac{dp}{dx}.
$$

## What to check

- No-slip velocity at both plates
- A consistent inlet-to-outlet pressure drop
- Symmetry about the channel mid-plane
- Parabolic velocity profile
- Agreement of the numerical flow rate with the analytical expression

## Model file

`plane-poiseuille-flow.mph`

Open the model in COMSOL Multiphysics, review all parameters and units, compute the study, and compare the cross-gap velocity and flow rate with the analytical solution.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../../LICENSE).
