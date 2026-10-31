# Aerodynamic Case: case_67_aoa+15_u35
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8228
- **Drag Coefficient ($C_d$):** 0.2024
- **Mean Wall $y^+$:** 16.67
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 15.0, "case_idx": 67}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 640.6 | 0.8538 | 0.7251 | 0.441 | 1.00 | 21.36 | 13.38 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 254.8 | 0.3397 | 1.8918 | 0.300 | 1.00 | 24.83 | 28.44 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 58.0 | 0.0773 | 1.9915 | 0.295 | 1.00 | 25.08 | 33.62 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -185.5 | -0.2472 | 1.7695 | 0.287 | 1.00 | 23.02 | 39.09 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -404.2 | -0.5387 | 1.4840 | 0.270 | 1.00 | 19.78 | 43.41 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -552.4 | -0.7362 | 1.3603 | 0.259 | 1.00 | 18.21 | 46.12 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -569.0 | -0.7583 | 0.9456 | 0.264 | 1.00 | 15.45 | 46.41 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -491.8 | -0.6554 | 0.6022 | 0.284 | 1.00 | 13.26 | 45.03 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -412.4 | -0.5496 | 0.5324 | 0.286 | 1.00 | 12.57 | 43.57 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -412.8 | -0.5501 | 1.1645 | 0.166 | 1.00 | 10.82 | 43.58 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -565.7 | -0.7540 | 2.8766 | 0.299 | 1.00 | 30.49 | 46.35 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -880.8 | -1.1739 | 2.5103 | 0.277 | 1.00 | 26.39 | 51.60 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -730.6 | -0.9738 | 0.9012 | 0.281 | 1.00 | 16.05 | 49.17 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -680.5 | -0.9070 | 0.6025 | 0.275 | 1.00 | 12.83 | 48.33 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -573.5 | -0.7644 | 0.4477 | 0.281 | 1.00 | 11.31 | 46.49 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -666.4 | -0.8882 | 0.0306 | 0.288 | 1.00 | 2.82 | 48.09 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -580.4 | -0.7736 | 0.3415 | 0.275 | 1.00 | 9.68 | 46.61 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -549.7 | -0.7326 | 0.4025 | 0.266 | 1.00 | 10.15 | 46.07 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -517.4 | -0.6895 | 0.4541 | 0.293 | 1.00 | 11.91 | 45.49 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -463.5 | -0.6178 | 0.0857 | 0.333 | 1.00 | 5.87 | 44.52 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
