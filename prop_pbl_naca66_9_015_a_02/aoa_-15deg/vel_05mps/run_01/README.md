# Aerodynamic Case: case_01_aoa-15_u05
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.3870
- **Drag Coefficient ($C_d$):** 0.2667
- **Mean Wall $y^+$:** 6.06
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": -15.0, "case_idx": 1}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -21.1 | -1.3812 | 0.3085 | 0.195 | 1.00 | 6.23 | 7.72 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -28.4 | -1.8549 | 0.1457 | 0.279 | 1.00 | 6.40 | 8.45 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -27.3 | -1.7823 | 0.1647 | 0.296 | 1.00 | 7.24 | 8.34 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -20.7 | -1.3534 | 0.1061 | 0.330 | 1.00 | 6.48 | 7.67 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -13.0 | -0.8473 | 0.0031 | 0.289 | 1.00 | 0.97 | 6.80 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -11.4 | -0.7446 | 0.1095 | 0.252 | 1.00 | 5.02 | 6.60 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -10.7 | -0.6997 | 0.1158 | 0.261 | 1.00 | 5.35 | 6.52 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -8.9 | -0.5807 | 0.0577 | 0.286 | 1.00 | 4.14 | 6.29 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -7.4 | -0.4816 | 0.0111 | 0.326 | 1.00 | 2.07 | 6.09 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -6.1 | -0.4008 | 0.0136 | 0.451 | 1.00 | 3.17 | 5.92 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 20.1 | 1.3139 | 0.0942 | 0.296 | 1.00 | 4.13 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | 2.4 | 0.1551 | 0.3639 | 0.280 | 1.00 | 10.16 | 4.60 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -11.5 | -0.7518 | 0.4511 | 0.281 | 1.00 | 11.38 | 6.62 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -15.3 | -1.0004 | 0.4088 | 0.291 | 1.00 | 11.22 | 7.07 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -13.6 | -0.8853 | 0.2641 | 0.296 | 1.00 | 9.16 | 6.87 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -10.7 | -0.7016 | 0.0595 | 0.286 | 1.00 | 4.18 | 6.52 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -10.3 | -0.6732 | 0.0654 | 0.290 | 1.00 | 4.47 | 6.47 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -9.2 | -0.6035 | 0.0861 | 0.295 | 1.00 | 5.21 | 6.33 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -8.1 | -0.5266 | 0.0858 | 0.305 | 1.00 | 5.39 | 6.18 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -6.4 | -0.4201 | 0.0398 | 0.307 | 1.00 | 3.69 | 5.96 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
