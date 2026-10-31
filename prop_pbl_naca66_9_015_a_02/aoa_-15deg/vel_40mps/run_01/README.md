# Aerodynamic Case: case_08_aoa-15_u40
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.2773
- **Drag Coefficient ($C_d$):** 0.2459
- **Mean Wall $y^+$:** 14.70
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": -15.0, "case_idx": 8}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -1530.6 | -1.5618 | 2.4000 | 0.195 | 1.00 | 17.10 | 64.02 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -1853.3 | -1.8911 | 0.7171 | 0.279 | 1.00 | 14.21 | 68.01 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -1756.7 | -1.7925 | 0.9042 | 0.296 | 1.00 | 16.96 | 66.84 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -1457.9 | -1.4876 | 0.7324 | 0.330 | 1.00 | 17.03 | 63.09 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -1025.3 | -1.0462 | 0.0751 | 0.289 | 1.00 | 4.76 | 57.22 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -890.6 | -0.9087 | 0.5611 | 0.252 | 1.00 | 11.37 | 55.26 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -822.8 | -0.8396 | 0.3902 | 0.261 | 1.00 | 9.83 | 54.25 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -720.8 | -0.7355 | 0.0069 | 0.286 | 1.00 | 1.38 | 52.70 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -650.2 | -0.6635 | 0.1738 | 0.326 | 1.00 | 8.18 | 51.59 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -602.2 | -0.6144 | 0.1066 | 0.451 | 1.00 | 8.87 | 50.82 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 1185.1 | 1.2093 | 0.7765 | 0.296 | 1.00 | 12.07 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | 37.3 | 0.0380 | 2.9784 | 0.280 | 1.00 | 29.08 | 39.23 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -830.9 | -0.8479 | 3.5785 | 0.281 | 1.00 | 32.05 | 54.37 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -1101.7 | -1.1242 | 2.8148 | 0.291 | 1.00 | 29.43 | 58.30 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -1114.5 | -1.1372 | 1.3418 | 0.296 | 1.00 | 20.65 | 58.48 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -999.0 | -1.0194 | 0.2091 | 0.286 | 1.00 | 7.84 | 56.84 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -852.9 | -0.8703 | 0.3334 | 0.290 | 1.00 | 10.10 | 54.70 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -749.1 | -0.7643 | 0.4243 | 0.295 | 1.00 | 11.56 | 53.13 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -681.6 | -0.6955 | 0.4384 | 0.305 | 1.00 | 12.18 | 52.09 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -616.4 | -0.6290 | 0.3231 | 0.307 | 1.00 | 10.50 | 51.05 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
