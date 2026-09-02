# Physics Simulations

Computational fluid-dynamics models by **Arian Ashrafi** (`@unluckyphysicist`).

This repository collects compact, reproducible COMSOL Multiphysics models for canonical transport-phenomena problems. The first collection, **Project Zero**, studies fully developed laminar flows driven by moving walls, pressure gradients, or both.

## Projects

| Project | Focus | Models |
| --- | --- | ---: |
| [Project Zero](./Project-Zero/) | Classical viscous-flow benchmarks | 5 |

## Requirements

- COMSOL Multiphysics
- The fluid-flow functionality needed to open and solve the included `.mph` files
- A compatible COMSOL release; if prompted, allow COMSOL to upgrade a copy of the model rather than the only original

## Using the models

1. Download or clone the repository.
2. Open the relevant project and simulation folder.
3. Read that folder's `README.md` for the physical setup and validation target.
4. Open the `.mph` file in COMSOL, review its parameters and boundary conditions, then compute the study.

The models are educational reference simulations. Verify the geometry, material properties, mesh, solver configuration, units, and boundary conditions before using any result in research, design, or safety-critical work.

## Rights

Copyright © 2026 Arian Ashrafi. **All rights reserved.** No open-source license is granted. See [LICENSE](./LICENSE) for the complete notice.
