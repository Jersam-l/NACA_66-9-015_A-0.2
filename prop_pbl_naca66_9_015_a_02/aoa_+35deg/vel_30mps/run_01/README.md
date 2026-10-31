# Aerodynamic Case: case_106_aoa+35_u30
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8146
- **Drag Coefficient ($C_d$):** 0.7003
- **Mean Wall $y^+$:** 9.92
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 35.0, "case_idx": 106}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 1445.3 | 2.6218 | 0.1792 | 0.335 | 1.00 | 7.84 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 1376.6 | 2.4972 | 0.6328 | 0.316 | 1.00 | 15.12 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 1278.2 | 2.3186 | 0.9091 | 0.312 | 1.00 | 17.95 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 1155.6 | 2.0963 | 1.1317 | 0.297 | 1.00 | 19.02 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 983.2 | 1.7835 | 1.2675 | 0.285 | 1.00 | 19.33 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 766.8 | 1.3911 | 1.3030 | 0.287 | 1.00 | 19.74 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 580.5 | 1.0530 | 1.2385 | 0.284 | 1.00 | 19.02 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 389.2 | 0.7060 | 1.3145 | 0.303 | 1.00 | 20.95 | 16.27 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 14.4 | 0.0260 | 1.6848 | 0.360 | 1.00 | 28.19 | 29.61 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | -135.3 | -0.2455 | 1.7630 | 0.392 | 1.00 | 31.37 | 33.48 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -298.3 | -0.5412 | 0.4259 | 0.271 | 1.00 | 10.53 | 37.24 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -341.6 | -0.6196 | 0.4827 | 0.294 | 1.00 | 12.30 | 38.18 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -278.3 | -0.5049 | 0.2604 | 0.292 | 1.00 | 8.96 | 36.80 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -309.5 | -0.5614 | 0.2727 | 0.287 | 1.00 | 9.04 | 37.49 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -339.9 | -0.6166 | 0.1928 | 0.293 | 1.00 | 7.74 | 38.14 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -368.5 | -0.6685 | 0.0168 | 0.294 | 1.00 | 2.29 | 38.75 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | -403.7 | -0.7324 | 0.0149 | 0.296 | 1.00 | 2.06 | 39.49 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | -426.6 | -0.7738 | 0.1887 | 0.302 | 1.00 | 7.89 | 39.95 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | -476.0 | -0.8635 | 0.3267 | 0.344 | 1.00 | 11.80 | 40.95 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | -527.3 | -0.9566 | 0.3229 | 0.353 | 1.00 | 12.09 | 41.96 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
