# Steady-State Diffusion FEM Solver (Python)

This repository implements a modular finite-element framework for solving 2D steady-state diffusion problems. The project is organized so that the FEM core, physics kernels, solver routines, and visualization outputs are cleanly separated and reusable.

## Overview

The goal of this project is to provide a lightweight but extensible FEM codebase that:

- Solves 2D steady-state diffusion using the Galerkin finite element method  
- Uses Q4/T3 elements with Gaussian quadrature  
- Exports VTK files for visualization in ParaView  
- Demonstrates the full workflow through a Jupyter notebook  

## Repository Structure

```text
FemFrameWork/              # Shape functions, Gauss points, ID matrices, FEM utilities
Physics_models/            # Diffusion kernel (local matrices, D-matrix, load)
Kernel/                    # High-level assembly and solver routines
DataFiles/                 # Meshes with boundary-condition data (.npz)
VTKoutputs/                # VTK output files for ParaView
test_functions/            # Unit tests for FEM components
pictures/                  # Solution figures and mesh visuals
steadystate_diffusion.ipynb  # Main example notebook
README.md
```

## Installation

```bash
git clone https://github.com/feignOP/FEM-Diffusion-Solver
cd FEM-Diffusion-Solver
python -m venv .venv
source .venv/bin/activate
pip install numpy scipy meshio matplotlib jupyter
```

## Running the Example

1. Start Jupyter:
```bash
jupyter notebook
```

2. Open `steadystate_diffusion.ipynb`  
3. Run all cells:
   - Loads mesh and boundary data from `DataFiles/*.npz`
   - Assembles local and global matrices
   - Applies Dirichlet constraints
   - Solves the sparse linear system
   - Writes results to `VTKoutputs/`

## Visualizing Results in ParaView

1. Open ParaView  
2. File → Open  
3. Select `.vtk` from `VTKoutputs/`  
4. Apply and choose Coloring to visualize concentration  

## Data File Structure (.npz)

- Coord – nodal coordinates  
- Connectivity – Q4 element connectivity  
- Constraints – DOF boundary condition mapping  
- Lx, Ly – domain dimensions  

## Extending the Framework

- Transient diffusion  
- Heat conduction  
- Linear elasticity  
- Higher-order elements  
- 3D extensions  
- Nonlinear materials  

## License

MIT License

Copyright (c) 2025 Anand Mathew
