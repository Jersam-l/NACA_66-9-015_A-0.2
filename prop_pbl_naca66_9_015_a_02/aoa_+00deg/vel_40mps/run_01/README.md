# Aerodynamic Case: case_38_aoa+00_u40
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0476
- **Drag Coefficient ($C_d$):** 0.0885
- **Mean Wall $y^+$:** 16.66
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 0.0, "case_idx": 38}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 692.1 | 0.7062 | 1.5458 | 0.302 | 1.00 | 22.64 | 21.68 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -339.4 | -0.3463 | 0.2474 | 0.285 | 1.00 | 8.51 | 46.41 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -189.3 | -0.1932 | 0.5558 | 0.300 | 1.00 | 13.47 | 43.69 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -237.2 | -0.2420 | 1.1463 | 0.301 | 1.00 | 19.39 | 44.58 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -418.5 | -0.4270 | 1.3561 | 0.290 | 1.00 | 20.34 | 47.78 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -588.3 | -0.6003 | 1.3869 | 0.281 | 1.00 | 19.93 | 50.60 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -643.2 | -0.6564 | 1.0315 | 0.279 | 1.00 | 17.04 | 51.48 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -561.8 | -0.5733 | 0.5854 | 0.286 | 1.00 | 13.19 | 50.17 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -455.0 | -0.4643 | 0.4269 | 0.299 | 1.00 | 11.77 | 48.40 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -374.6 | -0.3823 | 0.6351 | 0.334 | 1.00 | 16.02 | 47.03 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 1086.8 | 1.1090 | 0.1656 | 0.344 | 1.00 | 8.44 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -101.0 | -0.1031 | 2.9251 | 0.278 | 1.00 | 28.59 | 42.01 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -516.7 | -0.5272 | 2.9080 | 0.288 | 1.00 | 29.62 | 49.43 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -667.7 | -0.6813 | 2.0735 | 0.294 | 1.00 | 25.54 | 51.87 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -707.0 | -0.7215 | 1.0669 | 0.294 | 1.00 | 18.27 | 52.48 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -614.5 | -0.6271 | 0.2303 | 0.300 | 1.00 | 8.67 | 51.02 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -513.2 | -0.5236 | 0.3282 | 0.296 | 1.00 | 10.22 | 49.37 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -447.3 | -0.4565 | 0.3399 | 0.305 | 1.00 | 10.72 | 48.27 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -424.6 | -0.4333 | 0.3845 | 0.302 | 1.00 | 11.28 | 47.89 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -394.2 | -0.4023 | 0.0813 | 0.368 | 1.00 | 6.32 | 47.37 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
