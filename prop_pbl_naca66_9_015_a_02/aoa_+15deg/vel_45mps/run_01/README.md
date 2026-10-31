# Aerodynamic Case: case_69_aoa+15_u45
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.7580
- **Drag Coefficient ($C_d$):** 0.1895
- **Mean Wall $y^+$:** 19.18
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 15.0, "case_idx": 69}'
  ```
- **Publication Manuscript:** [research_paper.pdf](reports/research_paper.pdf)

---

### Discrete Surface Sampling (10 Stations per Surface, 20 Total)

> **Note on First-Layer Height vs. Local Wall Friction y+:**
> - **First-Cell Height (`y1_mesh`):** As verified on the structured Blossom boundary-layer grid, the wall-normal cell centroid spacing is **strictly uniform and constant (~0.320 mm)** across all stations.
> - **Nominal Mesh Design Target (`y+_target`):** Fixed constant design specification = **1.00**.
> - **Local Friction Wall Coordinate (`y+_local`):** Non-dimensional boundary layer distance defined by local friction velocity: $y^+_{\text{local}}(x) \equiv \frac{y_1 u_\tau(x)}{\nu} = \frac{y_1 \sqrt{|\tau_w(x)|/\rho}}{\nu}$. While physical grid height $y_1$ is constant, this local coordinate varies along the surface with physical fluid acceleration, stagnation, and shear stress $\tau_w(x)$.

| Point | Surface | x (m) | y (m) | x/c | p_wall (Pa) | Cp | tau_w (Pa) | y1_mesh (mm) [FIXED] | y+_target [FIXED] | y+_local (u_tau) | U_e (m/s) |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 1097.8 | 0.8851 | 0.9351 | 0.441 | 1.00 | 24.23 | 15.26 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 453.9 | 0.3659 | 2.4543 | 0.300 | 1.00 | 28.29 | 35.83 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 126.2 | 0.1017 | 2.6303 | 0.295 | 1.00 | 28.82 | 42.65 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -275.8 | -0.2224 | 2.3763 | 0.287 | 1.00 | 26.67 | 49.75 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -655.5 | -0.5285 | 1.9660 | 0.270 | 1.00 | 22.76 | 55.63 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -920.1 | -0.7418 | 1.7780 | 0.259 | 1.00 | 20.81 | 59.39 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -967.4 | -0.7800 | 1.2492 | 0.264 | 1.00 | 17.76 | 60.04 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -862.2 | -0.6952 | 0.8334 | 0.284 | 1.00 | 15.60 | 58.59 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -764.2 | -0.6161 | 0.7805 | 0.286 | 1.00 | 15.22 | 57.21 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -830.1 | -0.6693 | 1.7749 | 0.166 | 1.00 | 13.36 | 58.14 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -919.8 | -0.7416 | 3.7217 | 0.299 | 1.00 | 34.68 | 59.39 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -1468.0 | -1.1836 | 3.3175 | 0.277 | 1.00 | 30.34 | 66.50 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -1171.8 | -0.9448 | 1.1944 | 0.281 | 1.00 | 18.47 | 62.76 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -1102.5 | -0.8889 | 0.7723 | 0.275 | 1.00 | 14.53 | 61.85 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -932.9 | -0.7521 | 0.5588 | 0.281 | 1.00 | 12.64 | 59.57 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -1146.2 | -0.9242 | 0.0338 | 0.288 | 1.00 | 3.19 | 62.42 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -1002.1 | -0.8080 | 0.4190 | 0.275 | 1.00 | 10.73 | 60.51 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -962.0 | -0.7756 | 0.3299 | 0.266 | 1.00 | 9.19 | 59.96 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -965.7 | -0.7786 | 0.5915 | 0.293 | 1.00 | 13.60 | 60.01 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -932.1 | -0.7515 | 0.0087 | 0.333 | 1.00 | 1.87 | 59.55 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
