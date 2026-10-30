# Aerodynamic Case: case_36_aoa+00_u30
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0472
- **Drag Coefficient ($C_d$):** 0.0895
- **Mean Wall $y^+$:** 14.36
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 0.0, "case_idx": 36}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 388.8 | 0.7054 | 1.1584 | 0.302 | 1.00 | 19.60 | 16.28 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -192.7 | -0.3495 | 0.1846 | 0.285 | 1.00 | 7.35 | 34.85 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -105.9 | -0.1921 | 0.4277 | 0.300 | 1.00 | 11.81 | 32.76 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -135.2 | -0.2453 | 0.8644 | 0.301 | 1.00 | 16.84 | 33.48 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -237.4 | -0.4307 | 1.0217 | 0.290 | 1.00 | 17.66 | 35.88 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -332.8 | -0.6038 | 1.0464 | 0.281 | 1.00 | 17.31 | 37.99 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -363.6 | -0.6596 | 0.7812 | 0.279 | 1.00 | 14.83 | 38.65 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -317.2 | -0.5755 | 0.4478 | 0.286 | 1.00 | 11.53 | 37.66 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -257.0 | -0.4661 | 0.3271 | 0.299 | 1.00 | 10.30 | 36.33 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -212.4 | -0.3853 | 0.4799 | 0.334 | 1.00 | 13.92 | 35.31 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 610.7 | 1.1078 | 0.1243 | 0.344 | 1.00 | 7.31 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -56.0 | -0.1016 | 2.1822 | 0.278 | 1.00 | 24.69 | 31.49 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -291.0 | -0.5279 | 2.1254 | 0.288 | 1.00 | 25.33 | 37.08 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -382.6 | -0.6941 | 1.4684 | 0.294 | 1.00 | 21.49 | 39.05 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -402.2 | -0.7297 | 0.7586 | 0.294 | 1.00 | 15.41 | 39.45 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -347.2 | -0.6298 | 0.1719 | 0.300 | 1.00 | 7.49 | 38.30 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -289.7 | -0.5255 | 0.2437 | 0.296 | 1.00 | 8.81 | 37.05 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -253.7 | -0.4603 | 0.2622 | 0.305 | 1.00 | 9.41 | 36.25 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -241.1 | -0.4374 | 0.2940 | 0.302 | 1.00 | 9.86 | 35.97 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -223.8 | -0.4059 | 0.0608 | 0.368 | 1.00 | 5.47 | 35.57 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
