# 04 — Rectangular-Channel Couette Flow

This three-dimensional creeping-flow model represents a rectangular channel driven by tangential motion of a wall. Unlike the ideal infinite-plate case, the finite side walls introduce cross-sectional viscous effects.

## Physics

In the creeping-flow limit, inertia is negligible and the streamwise momentum balance reduces to a viscous boundary-value problem. With no pressure gradient, wall motion supplies the driving force:

$$
\mu\nabla_{\perp}^{2}u=0,
$$

where $\nabla_{\perp}^{2}$ operates over the channel cross-section. Far from side-wall influence, the solution approaches the linear Couette profile; near stationary side walls, the velocity is reduced by no slip.

## What to check

- The intended wall is assigned the prescribed tangential velocity
- All stationary walls satisfy no slip
- The pressure boundary conditions do not introduce unintended forcing
- Side-wall retardation appears in cross-sectional velocity contours
- Mesh refinement resolves velocity gradients near corners and moving/stationary wall junctions

## Model file

`rectangular-couette-flow.mph`

Open the model in COMSOL Multiphysics, review all parameters and units, compute the study, and compare the channel-center profile with the infinite-plate Couette limit.

## Rights

Copyright © 2026 Arian Ashrafi. All rights reserved. See the repository-level [LICENSE](../../LICENSE).
