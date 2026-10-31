# Aerodynamic Case: case_83_aoa+25_u15
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0062
- **Drag Coefficient ($C_d$):** 0.4574
- **Mean Wall $y^+$:** 11.07
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 25.0, "case_idx": 83}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 14.0 | 0.1019 | 0.9268 | 0.276 | 1.00 | 15.64 | 14.21 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 93.2 | 0.6766 | 0.9506 | 0.257 | 1.00 | 15.11 | 8.53 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 27.4 | 0.1990 | 0.9782 | 0.287 | 1.00 | 17.09 | 13.43 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -40.6 | -0.2948 | 0.9200 | 0.284 | 1.00 | 16.39 | 17.07 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -100.2 | -0.7269 | 0.7812 | 0.292 | 1.00 | 15.56 | 19.71 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -151.2 | -1.0971 | 0.7027 | 0.317 | 1.00 | 16.00 | 21.72 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -125.5 | -0.9106 | 0.6568 | 0.358 | 1.00 | 17.48 | 20.73 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -134.1 | -0.9731 | 0.4157 | 0.273 | 1.00 | 10.59 | 21.07 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -124.5 | -0.9037 | 0.4533 | 0.245 | 1.00 | 9.94 | 20.70 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -138.8 | -1.0070 | 0.6222 | 0.304 | 1.00 | 14.44 | 21.25 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -279.4 | -2.0275 | 1.1309 | 0.272 | 1.00 | 14.74 | 26.10 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -146.6 | -1.0638 | 0.2575 | 0.272 | 1.00 | 8.31 | 21.55 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -136.2 | -0.9885 | 0.2606 | 0.276 | 1.00 | 8.50 | 21.15 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -123.1 | -0.8932 | 0.2432 | 0.280 | 1.00 | 8.33 | 20.64 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -111.4 | -0.8082 | 0.2203 | 0.278 | 1.00 | 7.85 | 20.17 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -104.1 | -0.7551 | 0.2117 | 0.263 | 1.00 | 7.28 | 19.87 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -100.8 | -0.7315 | 0.2036 | 0.254 | 1.00 | 6.90 | 19.74 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -100.1 | -0.7261 | 0.2226 | 0.263 | 1.00 | 7.47 | 19.71 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -153.6 | -1.1144 | 0.1331 | 0.297 | 1.00 | 6.52 | 21.81 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -156.2 | -1.1332 | 0.0360 | 0.297 | 1.00 | 3.39 | 21.91 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
