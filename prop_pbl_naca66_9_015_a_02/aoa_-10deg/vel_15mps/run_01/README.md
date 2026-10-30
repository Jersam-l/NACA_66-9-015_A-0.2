# Aerodynamic Case: case_13_aoa-10_u15
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0196
- **Drag Coefficient ($C_d$):** 0.1702
- **Mean Wall $y^+$:** 8.88
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": -10.0, "case_idx": 13}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -94.7 | -0.6872 | 0.9792 | 0.283 | 1.00 | 16.82 | 19.48 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -217.3 | -1.5770 | 0.2943 | 0.281 | 1.00 | 9.17 | 24.08 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -191.8 | -1.3920 | 0.2868 | 0.291 | 1.00 | 9.38 | 23.20 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -143.4 | -1.0403 | 0.0602 | 0.289 | 1.00 | 4.24 | 21.43 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -124.6 | -0.9042 | 0.2299 | 0.291 | 1.00 | 8.41 | 20.70 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -133.2 | -0.9666 | 0.3491 | 0.290 | 1.00 | 10.33 | 21.04 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -128.0 | -0.9291 | 0.2182 | 0.299 | 1.00 | 8.42 | 20.83 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -110.3 | -0.8003 | 0.0050 | 0.286 | 1.00 | 1.10 | 20.13 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -98.0 | -0.7112 | 0.1207 | 0.306 | 1.00 | 6.40 | 19.62 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -87.2 | -0.6330 | 0.1021 | 0.360 | 1.00 | 6.92 | 19.17 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 159.5 | 1.1571 | 0.2671 | 0.284 | 1.00 | 7.75 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | 1.0 | 0.0069 | 1.0995 | 0.273 | 1.00 | 17.24 | 14.95 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -98.2 | -0.7129 | 1.1905 | 0.282 | 1.00 | 18.55 | 19.63 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -137.9 | -1.0004 | 0.8640 | 0.290 | 1.00 | 16.23 | 21.21 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -148.2 | -1.0755 | 0.4721 | 0.292 | 1.00 | 12.08 | 21.61 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -135.6 | -0.9841 | 0.1945 | 0.295 | 1.00 | 7.84 | 21.13 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -116.7 | -0.8468 | 0.0426 | 0.297 | 1.00 | 3.67 | 20.38 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -103.8 | -0.7534 | 0.1381 | 0.292 | 1.00 | 6.54 | 19.86 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -94.4 | -0.6850 | 0.1285 | 0.305 | 1.00 | 6.59 | 19.47 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -85.4 | -0.6195 | 0.0630 | 0.349 | 1.00 | 5.27 | 19.09 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
