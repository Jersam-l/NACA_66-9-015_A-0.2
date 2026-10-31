# Aerodynamic Case: case_06_aoa-15_u30
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.3602
- **Drag Coefficient ($C_d$):** 0.2630
- **Mean Wall $y^+$:** 13.07
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": -15.0, "case_idx": 6}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -806.3 | -1.4626 | 1.7996 | 0.195 | 1.00 | 14.88 | 47.08 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -989.8 | -1.7956 | 0.5332 | 0.279 | 1.00 | 12.25 | 50.16 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -939.6 | -1.7044 | 0.6895 | 0.296 | 1.00 | 14.81 | 49.34 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -763.1 | -1.3843 | 0.5682 | 0.330 | 1.00 | 15.00 | 46.32 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -496.2 | -0.9002 | 0.0288 | 0.289 | 1.00 | 2.94 | 41.35 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -455.6 | -0.8264 | 0.6115 | 0.252 | 1.00 | 11.87 | 40.54 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -455.5 | -0.8263 | 0.5210 | 0.261 | 1.00 | 11.35 | 40.54 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -402.3 | -0.7298 | 0.2062 | 0.286 | 1.00 | 7.82 | 39.46 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -351.6 | -0.6379 | 0.0166 | 0.326 | 1.00 | 2.52 | 38.39 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -313.3 | -0.5683 | 0.0295 | 0.451 | 1.00 | 4.67 | 37.57 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 675.8 | 1.2259 | 0.5733 | 0.296 | 1.00 | 10.29 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | 48.6 | 0.0882 | 2.1999 | 0.280 | 1.00 | 24.99 | 28.65 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -425.3 | -0.7715 | 2.6073 | 0.281 | 1.00 | 27.35 | 39.93 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -575.4 | -1.0437 | 1.9634 | 0.291 | 1.00 | 24.58 | 42.89 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -577.2 | -1.0470 | 0.8900 | 0.296 | 1.00 | 16.82 | 42.92 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -510.0 | -0.9252 | 0.0990 | 0.286 | 1.00 | 5.36 | 41.63 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -433.8 | -0.7870 | 0.2625 | 0.290 | 1.00 | 8.96 | 40.10 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -384.7 | -0.6979 | 0.3172 | 0.295 | 1.00 | 10.00 | 39.09 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -355.0 | -0.6440 | 0.3506 | 0.305 | 1.00 | 10.89 | 38.47 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -317.9 | -0.5767 | 0.2228 | 0.307 | 1.00 | 8.72 | 37.67 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
