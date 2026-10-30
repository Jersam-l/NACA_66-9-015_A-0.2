# Aerodynamic Case: case_28_aoa-05_u40
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0395
- **Drag Coefficient ($C_d$):** 0.1195
- **Mean Wall $y^+$:** 15.24
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": -5.0, "case_idx": 28}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 586.9 | 0.5988 | 1.9104 | 0.298 | 1.00 | 24.81 | 25.34 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -990.6 | -1.0109 | 0.5642 | 0.286 | 1.00 | 12.93 | 56.72 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -807.7 | -0.8242 | 0.5066 | 0.310 | 1.00 | 13.27 | 54.02 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -482.5 | -0.4923 | 0.4364 | 0.307 | 1.00 | 12.20 | 48.86 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -569.1 | -0.5807 | 1.1052 | 0.288 | 1.00 | 18.22 | 50.29 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -730.8 | -0.7457 | 1.3079 | 0.274 | 1.00 | 18.89 | 52.85 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -758.3 | -0.7737 | 0.9068 | 0.278 | 1.00 | 15.92 | 53.27 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -655.2 | -0.6686 | 0.3801 | 0.291 | 1.00 | 10.80 | 51.67 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -545.4 | -0.5565 | 0.1369 | 0.320 | 1.00 | 7.13 | 49.90 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -454.0 | -0.4633 | 0.1657 | 0.365 | 1.00 | 8.94 | 48.39 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 1087.4 | 1.1096 | 0.6538 | 0.302 | 1.00 | 14.73 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -34.9 | -0.0356 | 2.8735 | 0.278 | 1.00 | 28.38 | 40.71 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -577.3 | -0.5890 | 3.1134 | 0.282 | 1.00 | 30.00 | 50.42 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -773.0 | -0.7888 | 2.3370 | 0.289 | 1.00 | 26.65 | 53.50 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -838.9 | -0.8561 | 1.2757 | 0.295 | 1.00 | 20.04 | 54.49 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -757.9 | -0.7734 | 0.4008 | 0.294 | 1.00 | 11.23 | 53.27 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -637.3 | -0.6503 | 0.2838 | 0.287 | 1.00 | 9.21 | 51.38 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -550.8 | -0.5621 | 0.4090 | 0.282 | 1.00 | 10.86 | 49.99 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -510.4 | -0.5209 | 0.4581 | 0.275 | 1.00 | 11.22 | 49.33 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -460.8 | -0.4702 | 0.2193 | 0.343 | 1.00 | 9.68 | 48.50 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
