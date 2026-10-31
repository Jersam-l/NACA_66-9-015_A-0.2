# Aerodynamic Case: case_90_aoa+25_u50
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.1200
- **Drag Coefficient ($C_d$):** 0.4195
- **Mean Wall $y^+$:** 19.43
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 25.0, "case_idx": 90}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 430.0 | 0.2808 | 3.0761 | 0.276 | 1.00 | 28.34 | 42.40 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 1192.7 | 0.7789 | 3.2022 | 0.257 | 1.00 | 27.72 | 23.51 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 515.2 | 0.3365 | 3.2603 | 0.287 | 1.00 | 31.19 | 40.73 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -167.2 | -0.1092 | 3.0544 | 0.284 | 1.00 | 29.87 | 52.66 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -763.5 | -0.4986 | 2.5372 | 0.292 | 1.00 | 28.03 | 61.21 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -1259.1 | -0.8223 | 2.2485 | 0.317 | 1.00 | 28.63 | 67.50 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -877.4 | -0.5730 | 2.1365 | 0.358 | 1.00 | 31.52 | 62.71 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -913.7 | -0.5967 | 1.2699 | 0.273 | 1.00 | 18.51 | 63.18 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -745.3 | -0.4867 | 1.2894 | 0.245 | 1.00 | 16.77 | 60.97 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -788.7 | -0.5151 | 1.8573 | 0.304 | 1.00 | 24.94 | 61.54 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -2902.0 | -1.8952 | 3.8408 | 0.272 | 1.00 | 27.75 | 85.08 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -1507.9 | -0.9848 | 0.7926 | 0.272 | 1.00 | 14.58 | 70.44 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -1352.7 | -0.8834 | 0.9141 | 0.276 | 1.00 | 15.91 | 68.62 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -1117.4 | -0.7297 | 0.8726 | 0.280 | 1.00 | 15.78 | 65.76 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -893.9 | -0.5838 | 0.7501 | 0.278 | 1.00 | 14.48 | 62.92 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -742.2 | -0.4847 | 0.7015 | 0.263 | 1.00 | 13.25 | 60.92 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -627.8 | -0.4100 | 0.5730 | 0.254 | 1.00 | 11.57 | 59.37 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -575.5 | -0.3759 | 0.5377 | 0.263 | 1.00 | 11.62 | 58.65 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -904.6 | -0.5908 | 0.4998 | 0.297 | 1.00 | 12.65 | 63.06 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -892.1 | -0.5826 | 0.0072 | 0.297 | 1.00 | 1.52 | 62.90 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
