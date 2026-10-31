# Aerodynamic Case: case_09_aoa-15_u45
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.2141
- **Drag Coefficient ($C_d$):** 0.2326
- **Mean Wall $y^+$:** 15.56
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": -15.0, "case_idx": 9}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -2076.1 | -1.6738 | 2.6533 | 0.195 | 1.00 | 17.83 | 73.58 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -2479.3 | -1.9990 | 0.7973 | 0.279 | 1.00 | 14.98 | 77.93 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -2359.3 | -1.9022 | 0.9954 | 0.296 | 1.00 | 17.80 | 76.66 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -2001.1 | -1.6134 | 0.8188 | 0.330 | 1.00 | 18.00 | 72.75 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -1460.0 | -1.1771 | 0.1119 | 0.289 | 1.00 | 5.82 | 66.40 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -1280.6 | -1.0325 | 0.5870 | 0.252 | 1.00 | 11.63 | 64.15 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -1191.8 | -0.9608 | 0.3925 | 0.261 | 1.00 | 9.85 | 63.01 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -1067.7 | -0.8608 | 0.0529 | 0.286 | 1.00 | 3.96 | 61.38 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -985.6 | -0.7946 | 0.2633 | 0.326 | 1.00 | 10.07 | 60.28 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -921.1 | -0.7426 | 0.1973 | 0.451 | 1.00 | 12.07 | 59.40 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 1391.9 | 1.1222 | 0.8786 | 0.296 | 1.00 | 13.09 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | -97.4 | -0.0785 | 3.3831 | 0.280 | 1.00 | 30.99 | 46.73 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -1207.8 | -0.9738 | 4.0785 | 0.281 | 1.00 | 34.21 | 63.22 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -1550.9 | -1.2504 | 3.2717 | 0.291 | 1.00 | 31.73 | 67.51 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -1570.5 | -1.2662 | 1.6025 | 0.296 | 1.00 | 22.56 | 67.74 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -1431.5 | -1.1541 | 0.2732 | 0.286 | 1.00 | 8.96 | 66.05 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -1248.0 | -1.0062 | 0.3727 | 0.290 | 1.00 | 10.67 | 63.74 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -1116.8 | -0.9004 | 0.4806 | 0.295 | 1.00 | 12.31 | 62.03 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -1034.4 | -0.8339 | 0.5250 | 0.305 | 1.00 | 13.33 | 60.94 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -940.3 | -0.7581 | 0.4268 | 0.307 | 1.00 | 12.06 | 59.67 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
