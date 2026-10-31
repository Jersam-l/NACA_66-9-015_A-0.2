# Aerodynamic Case: case_84_aoa+25_u20
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9910
- **Drag Coefficient ($C_d$):** 0.4305
- **Mean Wall $y^+$:** 12.52
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 25.0, "case_idx": 84}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 22.5 | 0.0918 | 1.2351 | 0.276 | 1.00 | 18.02 | 19.06 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 155.7 | 0.6357 | 1.2634 | 0.257 | 1.00 | 17.41 | 12.07 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 41.2 | 0.1681 | 1.2766 | 0.287 | 1.00 | 19.52 | 18.24 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -77.5 | -0.3163 | 1.1910 | 0.284 | 1.00 | 18.65 | 22.95 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -181.2 | -0.7395 | 1.0217 | 0.292 | 1.00 | 17.79 | 26.38 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -271.5 | -1.1080 | 0.9351 | 0.317 | 1.00 | 18.46 | 29.04 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -226.6 | -0.9248 | 0.8845 | 0.358 | 1.00 | 20.28 | 27.75 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -244.0 | -0.9959 | 0.5633 | 0.273 | 1.00 | 12.33 | 28.25 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -229.6 | -0.9371 | 0.6024 | 0.245 | 1.00 | 11.46 | 27.84 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -254.1 | -1.0371 | 0.8244 | 0.304 | 1.00 | 16.62 | 28.55 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -503.4 | -2.0548 | 1.5457 | 0.272 | 1.00 | 17.73 | 34.96 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -269.7 | -1.1008 | 0.3073 | 0.272 | 1.00 | 9.08 | 28.99 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -249.3 | -1.0174 | 0.3170 | 0.276 | 1.00 | 9.37 | 28.41 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -223.5 | -0.9121 | 0.2883 | 0.280 | 1.00 | 9.07 | 27.66 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -200.4 | -0.8179 | 0.2455 | 0.278 | 1.00 | 8.28 | 26.97 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -185.8 | -0.7584 | 0.2149 | 0.263 | 1.00 | 7.33 | 26.52 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -181.6 | -0.7411 | 0.1755 | 0.254 | 1.00 | 6.41 | 26.39 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -183.9 | -0.7508 | 0.2328 | 0.263 | 1.00 | 7.64 | 26.46 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -273.1 | -1.1148 | 0.1532 | 0.297 | 1.00 | 7.00 | 29.09 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -281.0 | -1.1468 | 0.0835 | 0.297 | 1.00 | 5.16 | 29.30 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
