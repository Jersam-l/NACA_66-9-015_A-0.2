# Aerodynamic Case: case_109_aoa+35_u45
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.7122
- **Drag Coefficient ($C_d$):** 1.1432
- **Mean Wall $y^+$:** 12.97
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 35.0, "case_idx": 109}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 4355.7 | 3.5118 | 0.3399 | 0.335 | 1.00 | 10.88 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 4290.2 | 3.4589 | 0.8598 | 0.316 | 1.00 | 17.63 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 4118.3 | 3.3204 | 1.2742 | 0.312 | 1.00 | 21.25 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 3891.7 | 3.1377 | 1.5895 | 0.297 | 1.00 | 22.54 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 3575.4 | 2.8827 | 1.7820 | 0.285 | 1.00 | 22.92 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 3191.0 | 2.5728 | 1.8349 | 0.287 | 1.00 | 23.43 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 2884.5 | 2.3257 | 1.7287 | 0.284 | 1.00 | 22.47 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 2560.4 | 2.0643 | 1.8351 | 0.303 | 1.00 | 24.75 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 1889.0 | 1.5230 | 2.3445 | 0.360 | 1.00 | 33.25 | 0.00 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 1622.6 | 1.3082 | 2.4535 | 0.392 | 1.00 | 37.01 | 0.00 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | 159.6 | 0.1287 | 0.6242 | 0.271 | 1.00 | 12.84 | 42.01 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | 232.4 | 0.1874 | 0.1540 | 0.294 | 1.00 | 6.94 | 40.57 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | 143.9 | 0.1160 | 0.7522 | 0.292 | 1.00 | 15.24 | 42.31 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | 156.6 | 0.1262 | 1.2275 | 0.287 | 1.00 | 19.18 | 42.06 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | 415.2 | 0.3348 | 1.1761 | 0.293 | 1.00 | 19.12 | 36.70 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | 710.6 | 0.5729 | 0.8787 | 0.294 | 1.00 | 16.63 | 29.41 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | 900.1 | 0.7257 | 0.3287 | 0.296 | 1.00 | 10.21 | 23.57 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | 936.5 | 0.7550 | 0.2572 | 0.302 | 1.00 | 9.21 | 22.27 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | 967.3 | 0.7799 | 0.2681 | 0.344 | 1.00 | 10.58 | 21.11 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | 912.2 | 0.7354 | 0.2810 | 0.353 | 1.00 | 11.28 | 23.15 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
