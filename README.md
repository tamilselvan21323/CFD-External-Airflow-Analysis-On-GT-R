# CFD-External-Airflow-Analysis-On-GT-R
To evaluate aerodynamic drag (Cd) and lift (Cl) coefficients of a passenger car body using steady-state CFD, and to identify major flow structures affecting aerodynamic efficiency

## Overview

This project sets up and runs an external aerodynamics simulation on a simplified
passenger vehicle body inside a virtual wind tunnel, then post-processes the results
to study drag, lift, and flow separation behavior (wheel wake, roof acceleration,
underbody flow).

## Workflow

1. **Geometry & domain** — Import car body, generate enclosure (virtual wind tunnel), boolean subtraction, named selections (`inlet`, `outlet`, `walls`, `wall solid`).
2. **Meshing** — Unstructured tetrahedral mesh, CFD physics preference, Fluent solver preference. *(Inflation layers on the car body pending — see Known Issues.)*
3. **Solution setup** — Steady, pressure-based solver; turbulence model TBD (k-ω SST recommended for external aero).
4. **Solve** — Run to convergence, monitor residuals and force coefficients.
5. **Post-processing** — Velocity/pressure contours, streamlines, Cd/Cl force reports in CFD-Post.
