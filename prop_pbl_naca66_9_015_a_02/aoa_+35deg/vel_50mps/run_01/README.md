# Aerodynamic Case: case_110_aoa+35_u50
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9247
- **Drag Coefficient ($C_d$):** 0.7176
- **Mean Wall $y^+$:** 12.81
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 35.0, "case_idx": 110}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 4434.3 | 2.8959 | 0.1807 | 0.335 | 1.00 | 6.15 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 4226.3 | 2.7601 | 1.1808 | 0.316 | 1.00 | 20.66 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 3976.0 | 2.5966 | 1.6315 | 0.312 | 1.00 | 24.04 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 3668.6 | 2.3958 | 1.9704 | 0.297 | 1.00 | 25.09 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 3251.6 | 2.1235 | 2.1534 | 0.285 | 1.00 | 25.20 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 2752.3 | 1.7974 | 2.1782 | 0.287 | 1.00 | 25.53 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 2337.1 | 1.5263 | 2.0379 | 0.284 | 1.00 | 24.40 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 1853.8 | 1.2107 | 2.1676 | 0.303 | 1.00 | 26.90 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 777.2 | 0.5076 | 2.8251 | 0.360 | 1.00 | 36.50 | 35.09 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 336.5 | 0.2198 | 2.9721 | 0.392 | 1.00 | 40.73 | 44.16 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -739.0 | -0.4826 | 0.7281 | 0.271 | 1.00 | 13.84 | 60.88 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -680.7 | -0.4446 | 0.7499 | 0.294 | 1.00 | 15.33 | 60.09 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -519.2 | -0.3391 | 0.4879 | 0.292 | 1.00 | 12.27 | 57.86 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -442.2 | -0.2888 | 0.3020 | 0.287 | 1.00 | 9.51 | 56.76 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -422.5 | -0.2759 | 0.0040 | 0.293 | 1.00 | 0.83 | 56.48 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -467.1 | -0.3051 | 0.1916 | 0.294 | 1.00 | 7.77 | 57.12 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | -536.4 | -0.3503 | 0.1932 | 0.296 | 1.00 | 7.82 | 58.10 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | -612.4 | -0.3999 | 0.4425 | 0.302 | 1.00 | 12.08 | 59.16 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | -636.2 | -0.4154 | 0.2737 | 0.344 | 1.00 | 10.54 | 59.49 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | -777.7 | -0.5079 | 0.2097 | 0.353 | 1.00 | 9.75 | 61.40 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
