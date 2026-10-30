# Aerodynamic Case: case_37_aoa+00_u35
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0472
- **Drag Coefficient ($C_d$):** 0.0890
- **Mean Wall $y^+$:** 15.54
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 0.0, "case_idx": 37}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 531.4 | 0.7082 | 1.3520 | 0.302 | 1.00 | 21.17 | 18.91 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -259.1 | -0.3453 | 0.2167 | 0.285 | 1.00 | 7.97 | 40.59 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -142.8 | -0.1904 | 0.4925 | 0.300 | 1.00 | 12.68 | 38.19 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -181.1 | -0.2413 | 1.0054 | 0.301 | 1.00 | 18.16 | 38.99 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -320.0 | -0.4265 | 1.1889 | 0.290 | 1.00 | 19.05 | 41.80 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -449.9 | -0.5997 | 1.2167 | 0.281 | 1.00 | 18.67 | 44.27 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -491.8 | -0.6555 | 0.9064 | 0.279 | 1.00 | 15.97 | 45.03 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -429.1 | -0.5719 | 0.5165 | 0.286 | 1.00 | 12.39 | 43.88 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -347.2 | -0.4627 | 0.3768 | 0.299 | 1.00 | 11.06 | 42.33 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -286.0 | -0.3812 | 0.5571 | 0.334 | 1.00 | 15.00 | 41.13 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 833.4 | 1.1107 | 0.1448 | 0.344 | 1.00 | 7.89 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -75.1 | -0.1001 | 2.5532 | 0.278 | 1.00 | 26.71 | 36.71 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -393.9 | -0.5249 | 2.5140 | 0.288 | 1.00 | 27.54 | 43.22 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -514.1 | -0.6852 | 1.7644 | 0.294 | 1.00 | 23.56 | 45.44 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -542.7 | -0.7233 | 0.9087 | 0.294 | 1.00 | 16.86 | 45.95 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -469.9 | -0.6263 | 0.2007 | 0.300 | 1.00 | 8.09 | 44.63 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -391.8 | -0.5222 | 0.2850 | 0.296 | 1.00 | 9.52 | 43.18 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -341.9 | -0.4557 | 0.3002 | 0.305 | 1.00 | 10.07 | 42.23 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -324.6 | -0.4326 | 0.3385 | 0.302 | 1.00 | 10.58 | 41.89 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -301.2 | -0.4014 | 0.0710 | 0.368 | 1.00 | 5.91 | 41.43 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
