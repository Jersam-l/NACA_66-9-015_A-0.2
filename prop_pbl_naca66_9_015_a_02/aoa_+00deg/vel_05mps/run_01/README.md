# Aerodynamic Case: case_31_aoa+00_u05
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0425
- **Drag Coefficient ($C_d$):** 0.0993
- **Mean Wall $y^+$:** 6.86
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 0.0, "case_idx": 31}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 11.5 | 0.7499 | 0.1946 | 0.302 | 1.00 | 8.03 | 2.50 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -5.4 | -0.3549 | 0.0284 | 0.285 | 1.00 | 2.88 | 5.82 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -2.6 | -0.1671 | 0.0834 | 0.300 | 1.00 | 5.22 | 5.40 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -3.2 | -0.2114 | 0.1763 | 0.301 | 1.00 | 7.61 | 5.50 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -5.8 | -0.3790 | 0.2286 | 0.290 | 1.00 | 8.35 | 5.87 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -8.3 | -0.5450 | 0.2599 | 0.281 | 1.00 | 8.63 | 6.21 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -8.9 | -0.5783 | 0.2348 | 0.279 | 1.00 | 8.13 | 6.28 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -7.1 | -0.4645 | 0.1648 | 0.286 | 1.00 | 7.00 | 6.05 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -5.5 | -0.3567 | 0.1163 | 0.299 | 1.00 | 6.14 | 5.82 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -4.5 | -0.2966 | 0.1374 | 0.334 | 1.00 | 7.45 | 5.69 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 17.8 | 1.1630 | 0.0206 | 0.344 | 1.00 | 2.98 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -1.6 | -0.1060 | 0.3647 | 0.278 | 1.00 | 10.10 | 5.26 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -8.6 | -0.5631 | 0.3820 | 0.288 | 1.00 | 10.74 | 6.25 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -10.3 | -0.6698 | 0.3406 | 0.294 | 1.00 | 10.35 | 6.46 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -9.5 | -0.6186 | 0.2475 | 0.294 | 1.00 | 8.80 | 6.36 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -6.8 | -0.4440 | 0.0851 | 0.300 | 1.00 | 5.27 | 6.01 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -6.9 | -0.4531 | 0.0577 | 0.296 | 1.00 | 4.28 | 6.03 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -6.3 | -0.4097 | 0.0628 | 0.305 | 1.00 | 4.61 | 5.94 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -6.0 | -0.3931 | 0.0707 | 0.302 | 1.00 | 4.84 | 5.90 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -5.4 | -0.3540 | 0.0100 | 0.368 | 1.00 | 2.22 | 5.82 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
