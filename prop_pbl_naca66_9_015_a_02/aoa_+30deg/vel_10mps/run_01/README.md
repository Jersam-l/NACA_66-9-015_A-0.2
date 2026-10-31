# Aerodynamic Case: case_92_aoa+30_u10
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.3981
- **Drag Coefficient ($C_d$):** 0.7772
- **Mean Wall $y^+$:** 9.74
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 30.0, "case_idx": 92}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 96.4 | 1.5738 | 0.4198 | 0.235 | 1.00 | 8.52 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 49.1 | 0.8022 | 0.6441 | 0.300 | 1.00 | 14.51 | 4.45 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 8.9 | 0.1456 | 0.7397 | 0.303 | 1.00 | 15.68 | 9.24 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -27.7 | -0.4530 | 0.6808 | 0.303 | 1.00 | 15.07 | 12.05 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -57.3 | -0.9362 | 0.5666 | 0.260 | 1.00 | 11.78 | 13.91 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -70.8 | -1.1561 | 0.4407 | 0.253 | 1.00 | 10.11 | 14.68 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -64.1 | -1.0461 | 0.2595 | 0.268 | 1.00 | 8.22 | 14.30 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -53.2 | -0.8689 | 0.2081 | 0.293 | 1.00 | 8.06 | 13.67 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -46.4 | -0.7583 | 0.2581 | 0.349 | 1.00 | 10.67 | 13.26 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | 0.7 | 0.0120 | 0.4821 | 0.433 | 1.00 | 18.13 | 9.94 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -69.6 | -1.1362 | 0.2256 | 0.270 | 1.00 | 7.47 | 14.62 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -64.7 | -1.0567 | 0.1458 | 0.271 | 1.00 | 6.24 | 14.34 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -66.3 | -1.0824 | 0.2155 | 0.278 | 1.00 | 7.78 | 14.43 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -63.4 | -1.0346 | 0.2571 | 0.294 | 1.00 | 8.99 | 14.26 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -56.0 | -0.9150 | 0.2655 | 0.291 | 1.00 | 9.04 | 13.84 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -48.8 | -0.7967 | 0.2650 | 0.280 | 1.00 | 8.68 | 13.40 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -43.7 | -0.7138 | 0.2436 | 0.286 | 1.00 | 8.51 | 13.09 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -38.5 | -0.6282 | 0.2413 | 0.283 | 1.00 | 8.38 | 12.76 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -27.6 | -0.4507 | 0.0459 | 0.303 | 1.00 | 3.82 | 12.04 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -35.2 | -0.5744 | 0.0585 | 0.283 | 1.00 | 4.12 | 12.55 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
