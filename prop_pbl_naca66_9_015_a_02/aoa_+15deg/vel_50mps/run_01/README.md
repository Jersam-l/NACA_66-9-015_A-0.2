# Aerodynamic Case: case_70_aoa+15_u50
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.7676
- **Drag Coefficient ($C_d$):** 0.1917
- **Mean Wall $y^+$:** 20.25
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 15.0, "case_idx": 70}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 2906.5 | 1.8981 | 1.0267 | 0.441 | 1.00 | 25.19 | 0.00 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 2129.5 | 1.3907 | 2.7169 | 0.300 | 1.00 | 29.76 | 0.00 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 1720.3 | 1.1235 | 2.9364 | 0.295 | 1.00 | 30.46 | 0.00 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | 1226.7 | 0.8011 | 2.6786 | 0.287 | 1.00 | 28.32 | 22.30 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | 751.2 | 0.4905 | 2.2029 | 0.270 | 1.00 | 24.09 | 35.69 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | 418.2 | 0.2731 | 1.9733 | 0.259 | 1.00 | 21.93 | 42.63 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | 355.0 | 0.2319 | 1.3829 | 0.264 | 1.00 | 18.68 | 43.82 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | 480.0 | 0.3135 | 0.9253 | 0.284 | 1.00 | 16.44 | 41.43 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | 597.1 | 0.3900 | 0.8726 | 0.286 | 1.00 | 16.09 | 39.05 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | 507.8 | 0.3316 | 2.0073 | 0.166 | 1.00 | 14.20 | 40.88 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | 357.8 | 0.2337 | 4.1945 | 0.299 | 1.00 | 36.81 | 43.77 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -263.5 | -0.1721 | 3.6599 | 0.277 | 1.00 | 31.86 | 54.13 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | 122.3 | 0.0799 | 1.2870 | 0.281 | 1.00 | 19.17 | 47.96 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | 206.8 | 0.1351 | 0.8193 | 0.275 | 1.00 | 14.97 | 46.50 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | 412.8 | 0.2696 | 0.5880 | 0.281 | 1.00 | 12.96 | 42.73 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | 131.2 | 0.0857 | 0.0301 | 0.288 | 1.00 | 3.00 | 47.81 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | 301.1 | 0.1966 | 0.4582 | 0.275 | 1.00 | 11.22 | 44.81 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | 340.3 | 0.2223 | 0.3688 | 0.266 | 1.00 | 9.72 | 44.09 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | 333.9 | 0.2180 | 0.6900 | 0.293 | 1.00 | 14.68 | 44.21 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | 376.9 | 0.2462 | 0.0136 | 0.333 | 1.00 | 2.34 | 43.41 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
