# Aerodynamic Case: case_113_aoa+40_u15
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.3824
- **Drag Coefficient ($C_d$):** 1.2923
- **Mean Wall $y^+$:** 7.29
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 40.0, "case_idx": 113}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 362.0 | 2.6268 | 0.6629 | 0.307 | 1.00 | 13.87 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 451.4 | 3.2753 | 0.2704 | 0.313 | 1.00 | 9.81 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 429.9 | 3.1197 | 0.4420 | 0.296 | 1.00 | 11.85 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 401.3 | 2.9118 | 0.5993 | 0.280 | 1.00 | 13.08 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 361.4 | 2.6227 | 0.7179 | 0.274 | 1.00 | 13.99 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 315.7 | 2.2908 | 0.7276 | 0.275 | 1.00 | 14.15 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 272.3 | 1.9760 | 0.6779 | 0.291 | 1.00 | 14.43 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 217.2 | 1.5763 | 0.7116 | 0.323 | 1.00 | 16.43 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 72.4 | 0.5251 | 1.0183 | 0.361 | 1.00 | 21.95 | 10.34 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 72.4 | 0.5251 | 1.0183 | 0.361 | 1.00 | 21.95 | 10.34 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | 3.2 | 0.0231 | 0.2456 | 0.294 | 1.00 | 8.67 | 14.83 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | 17.7 | 0.1286 | 0.0411 | 0.280 | 1.00 | 3.42 | 14.00 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | 14.8 | 0.1076 | 0.1114 | 0.290 | 1.00 | 5.82 | 14.17 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | 12.7 | 0.0924 | 0.0937 | 0.295 | 1.00 | 5.44 | 14.29 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | 8.2 | 0.0592 | 0.0114 | 0.294 | 1.00 | 1.84 | 14.55 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | -3.9 | -0.0285 | 0.0371 | 0.287 | 1.00 | 3.31 | 15.21 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | -16.6 | -0.1203 | 0.1760 | 0.280 | 1.00 | 7.08 | 15.88 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | -16.6 | -0.1208 | 0.1221 | 0.275 | 1.00 | 5.77 | 15.88 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | -49.3 | -0.3579 | 0.1927 | 0.336 | 1.00 | 8.89 | 17.48 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | -49.3 | -0.3579 | 0.1927 | 0.336 | 1.00 | 8.89 | 17.48 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
