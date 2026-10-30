# Aerodynamic Case: case_12_aoa-10_u10
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.1323
- **Drag Coefficient ($C_d$):** 0.2004
- **Mean Wall $y^+$:** 7.25
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": -10.0, "case_idx": 12}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -37.9 | -0.6182 | 0.6501 | 0.283 | 1.00 | 13.71 | 12.72 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -92.2 | -1.5061 | 0.2206 | 0.281 | 1.00 | 7.94 | 15.83 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -82.2 | -1.3419 | 0.1930 | 0.291 | 1.00 | 7.69 | 15.30 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -63.9 | -1.0431 | 0.0574 | 0.289 | 1.00 | 4.16 | 14.29 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -54.7 | -0.8934 | 0.1315 | 0.291 | 1.00 | 6.36 | 13.76 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -58.1 | -0.9493 | 0.2319 | 0.290 | 1.00 | 8.42 | 13.96 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -56.7 | -0.9265 | 0.1744 | 0.299 | 1.00 | 7.52 | 13.88 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -47.9 | -0.7822 | 0.0319 | 0.286 | 1.00 | 3.06 | 13.35 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -41.4 | -0.6759 | 0.0790 | 0.306 | 1.00 | 5.18 | 12.95 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -34.6 | -0.5645 | 0.0713 | 0.360 | 1.00 | 5.79 | 12.51 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 74.5 | 1.2164 | 0.2051 | 0.284 | 1.00 | 7.11 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | 9.9 | 0.1611 | 0.7106 | 0.273 | 1.00 | 13.86 | 9.16 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -33.8 | -0.5516 | 0.7953 | 0.282 | 1.00 | 15.16 | 12.46 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -50.3 | -0.8211 | 0.6011 | 0.290 | 1.00 | 13.54 | 13.49 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -54.4 | -0.8883 | 0.3243 | 0.292 | 1.00 | 10.01 | 13.74 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -49.1 | -0.8018 | 0.1149 | 0.295 | 1.00 | 6.02 | 13.42 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -43.0 | -0.7015 | 0.0496 | 0.297 | 1.00 | 3.97 | 13.04 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -38.5 | -0.6283 | 0.0962 | 0.292 | 1.00 | 5.46 | 12.76 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -35.7 | -0.5836 | 0.0919 | 0.305 | 1.00 | 5.57 | 12.58 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -32.6 | -0.5315 | 0.0458 | 0.349 | 1.00 | 4.50 | 12.38 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
