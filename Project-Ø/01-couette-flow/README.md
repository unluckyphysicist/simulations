# 01 — Couette Flow Between Parallel Plates

This model represents steady, incompressible flow between two effectively infinite parallel plates. One plate moves tangentially while the other remains stationary, and there is no imposed streamwise pressure gradient.

## Physics

For a plate spacing $h$, stationary lower wall, and upper-wall speed $U$, the fully developed streamwise velocity is

$$
u(y)=U\frac{y}{h}.
$$

The profile is linear, the shear stress is uniform, and

$$
\tau_{xy}=\mu\frac{U}{h}.
$$

## What to check

- No-slip velocity at both plates
- Zero or negligible streamwise pressure gradient
- Linear velocity profile across the gap
- Constant wall shear stress
- Mesh independence of the velocity gradient

## Model file

`couette-flow-parallel-plates.mph`

Open the model in COMSOL Multiphysics, review all parameters and units, compute the study, and compare a cross-gap velocity plot with the analytical line above.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../../LICENSE).
