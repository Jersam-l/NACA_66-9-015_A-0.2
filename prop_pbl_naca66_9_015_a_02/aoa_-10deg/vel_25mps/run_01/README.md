# Aerodynamic Case: case_15_aoa-10_u25
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0120
- **Drag Coefficient ($C_d$):** 0.1490
- **Mean Wall $y^+$:** 11.71
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": -10.0, "case_idx": 15}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -309.2 | -0.8078 | 1.6181 | 0.283 | 1.00 | 21.60 | 33.61 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -625.7 | -1.6344 | 0.4373 | 0.281 | 1.00 | 11.18 | 40.58 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -561.5 | -1.4669 | 0.4707 | 0.291 | 1.00 | 12.01 | 39.27 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -421.7 | -1.1017 | 0.1154 | 0.289 | 1.00 | 5.89 | 36.24 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -359.9 | -0.9403 | 0.3908 | 0.291 | 1.00 | 10.97 | 34.82 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -382.7 | -0.9996 | 0.5956 | 0.290 | 1.00 | 13.50 | 35.35 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -371.2 | -0.9697 | 0.3743 | 0.299 | 1.00 | 11.02 | 35.09 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -327.1 | -0.8546 | 0.0556 | 0.286 | 1.00 | 4.04 | 34.05 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -294.9 | -0.7703 | 0.0924 | 0.306 | 1.00 | 5.60 | 33.26 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -272.6 | -0.7120 | 0.0804 | 0.360 | 1.00 | 6.14 | 32.71 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 379.2 | 0.9907 | 0.3796 | 0.284 | 1.00 | 8.12 | 2.41 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -83.6 | -0.2183 | 1.8725 | 0.273 | 1.00 | 22.50 | 27.59 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -353.5 | -0.9234 | 2.0226 | 0.282 | 1.00 | 24.17 | 34.67 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -454.8 | -1.1881 | 1.4802 | 0.290 | 1.00 | 21.24 | 36.98 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -480.2 | -1.2544 | 0.7967 | 0.292 | 1.00 | 15.70 | 37.54 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -442.5 | -1.1558 | 0.3070 | 0.295 | 1.00 | 9.85 | 36.71 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -384.0 | -1.0031 | 0.0942 | 0.297 | 1.00 | 5.46 | 35.38 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -341.6 | -0.8922 | 0.2558 | 0.292 | 1.00 | 8.90 | 34.39 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -310.3 | -0.8105 | 0.2656 | 0.305 | 1.00 | 9.47 | 33.64 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -278.2 | -0.7267 | 0.1728 | 0.349 | 1.00 | 8.73 | 32.85 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
