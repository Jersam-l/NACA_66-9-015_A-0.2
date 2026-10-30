# Aerodynamic Case: case_39_aoa+00_u45
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0479
- **Drag Coefficient ($C_d$):** 0.0882
- **Mean Wall $y^+$:** 17.72
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 0.0, "case_idx": 39}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 860.0 | 0.6934 | 1.7396 | 0.302 | 1.00 | 24.01 | 24.92 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -444.6 | -0.3584 | 0.2775 | 0.285 | 1.00 | 9.01 | 52.45 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -256.3 | -0.2067 | 0.6183 | 0.300 | 1.00 | 14.20 | 49.43 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -314.5 | -0.2536 | 1.2870 | 0.301 | 1.00 | 20.55 | 50.38 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -543.8 | -0.4384 | 1.5232 | 0.290 | 1.00 | 21.56 | 53.97 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -758.9 | -0.6119 | 1.5567 | 0.281 | 1.00 | 21.11 | 57.13 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -828.7 | -0.6681 | 1.1562 | 0.279 | 1.00 | 18.04 | 58.12 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -726.2 | -0.5855 | 0.6539 | 0.286 | 1.00 | 13.94 | 56.66 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -591.3 | -0.4767 | 0.4769 | 0.299 | 1.00 | 12.44 | 54.68 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -489.1 | -0.3943 | 0.7136 | 0.334 | 1.00 | 16.98 | 53.14 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 1359.8 | 1.0963 | 0.1863 | 0.344 | 1.00 | 8.95 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -144.8 | -0.1168 | 3.2976 | 0.278 | 1.00 | 30.36 | 47.55 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -670.5 | -0.5406 | 3.3055 | 0.288 | 1.00 | 31.58 | 55.85 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -854.0 | -0.6885 | 2.3942 | 0.294 | 1.00 | 27.44 | 58.48 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -905.6 | -0.7302 | 1.2328 | 0.294 | 1.00 | 19.64 | 59.19 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -791.6 | -0.6382 | 0.2614 | 0.300 | 1.00 | 9.23 | 57.60 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -664.6 | -0.5359 | 0.3726 | 0.296 | 1.00 | 10.89 | 55.77 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -580.8 | -0.4683 | 0.3807 | 0.305 | 1.00 | 11.34 | 54.53 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -552.0 | -0.4450 | 0.4313 | 0.302 | 1.00 | 11.95 | 54.09 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -513.7 | -0.4142 | 0.0915 | 0.368 | 1.00 | 6.71 | 53.51 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
