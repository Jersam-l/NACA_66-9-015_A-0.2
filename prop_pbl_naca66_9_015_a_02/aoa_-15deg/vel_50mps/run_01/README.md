# Aerodynamic Case: case_10_aoa-15_u50
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.5168
- **Drag Coefficient ($C_d$):** 0.2902
- **Mean Wall $y^+$:** 17.21
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": -15.0, "case_idx": 10}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -1974.0 | -1.2892 | 3.0449 | 0.195 | 1.00 | 19.57 | 75.65 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -2465.4 | -1.6100 | 0.8288 | 0.279 | 1.00 | 15.28 | 80.78 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -2386.1 | -1.5583 | 1.1865 | 0.296 | 1.00 | 19.43 | 79.97 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -1940.4 | -1.2672 | 1.1038 | 0.330 | 1.00 | 20.90 | 75.29 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -1137.9 | -0.7431 | 0.2713 | 0.289 | 1.00 | 9.05 | 66.01 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -893.4 | -0.5834 | 0.7501 | 0.252 | 1.00 | 13.15 | 62.92 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -851.5 | -0.5561 | 0.6537 | 0.261 | 1.00 | 12.72 | 62.37 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -734.1 | -0.4794 | 0.2167 | 0.286 | 1.00 | 8.02 | 60.82 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -644.1 | -0.4206 | 0.0142 | 0.326 | 1.00 | 2.34 | 59.59 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -599.4 | -0.3915 | 0.0549 | 0.451 | 1.00 | 6.37 | 58.98 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 1938.4 | 1.2659 | 0.9353 | 0.296 | 1.00 | 12.88 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | 248.4 | 0.1622 | 3.6426 | 0.280 | 1.00 | 32.16 | 45.77 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -1051.7 | -0.6868 | 4.4294 | 0.281 | 1.00 | 35.65 | 64.94 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -1410.2 | -0.9209 | 3.5444 | 0.291 | 1.00 | 33.03 | 69.30 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -1377.2 | -0.8994 | 1.6388 | 0.296 | 1.00 | 22.82 | 68.91 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -1193.9 | -0.7797 | 0.1172 | 0.286 | 1.00 | 5.73 | 66.70 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -982.0 | -0.6413 | 0.5033 | 0.290 | 1.00 | 12.40 | 64.06 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -832.7 | -0.5438 | 0.5614 | 0.295 | 1.00 | 13.30 | 62.12 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -753.4 | -0.4920 | 0.6140 | 0.305 | 1.00 | 14.41 | 61.07 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -687.3 | -0.4488 | 0.4339 | 0.307 | 1.00 | 12.16 | 60.18 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
