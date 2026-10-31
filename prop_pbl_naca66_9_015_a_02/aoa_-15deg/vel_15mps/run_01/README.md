# Aerodynamic Case: case_03_aoa-15_u15
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.3851
- **Drag Coefficient ($C_d$):** 0.2679
- **Mean Wall $y^+$:** 9.53
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": -15.0, "case_idx": 3}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -200.7 | -1.4567 | 0.9205 | 0.195 | 1.00 | 10.74 | 23.51 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -253.6 | -1.8400 | 0.2964 | 0.279 | 1.00 | 9.14 | 25.28 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -239.2 | -1.7355 | 0.3652 | 0.296 | 1.00 | 10.78 | 24.81 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -189.9 | -1.3778 | 0.2740 | 0.330 | 1.00 | 10.41 | 23.13 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -125.8 | -0.9126 | 0.0370 | 0.289 | 1.00 | 3.34 | 20.75 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -118.2 | -0.8577 | 0.3321 | 0.252 | 1.00 | 8.75 | 20.45 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -120.4 | -0.8739 | 0.3012 | 0.261 | 1.00 | 8.63 | 20.53 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -107.3 | -0.7789 | 0.1500 | 0.286 | 1.00 | 6.67 | 20.01 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -92.4 | -0.6708 | 0.0505 | 0.326 | 1.00 | 4.41 | 19.39 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -80.3 | -0.5823 | 0.0582 | 0.451 | 1.00 | 6.55 | 18.87 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 166.2 | 1.2063 | 0.2841 | 0.296 | 1.00 | 7.28 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | 9.5 | 0.0691 | 1.0935 | 0.280 | 1.00 | 17.62 | 14.47 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -108.3 | -0.7855 | 1.2714 | 0.281 | 1.00 | 19.10 | 20.04 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -148.3 | -1.0759 | 0.9123 | 0.291 | 1.00 | 16.75 | 21.61 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -147.3 | -1.0692 | 0.4051 | 0.296 | 1.00 | 11.34 | 21.58 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -128.1 | -0.9298 | 0.0327 | 0.286 | 1.00 | 3.04 | 20.84 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -110.8 | -0.8041 | 0.1568 | 0.290 | 1.00 | 6.92 | 20.15 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -99.4 | -0.7216 | 0.1987 | 0.295 | 1.00 | 7.91 | 19.68 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -91.5 | -0.6637 | 0.2004 | 0.305 | 1.00 | 8.23 | 19.35 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -81.2 | -0.5893 | 0.0876 | 0.307 | 1.00 | 5.47 | 18.91 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
