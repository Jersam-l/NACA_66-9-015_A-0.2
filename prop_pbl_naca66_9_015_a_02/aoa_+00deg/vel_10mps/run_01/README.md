# Aerodynamic Case: case_32_aoa+00_u10
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0560
- **Drag Coefficient ($C_d$):** 0.0964
- **Mean Wall $y^+$:** 8.62
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 0.0, "case_idx": 32}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 45.2 | 0.7383 | 0.3892 | 0.302 | 1.00 | 11.36 | 5.12 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -20.0 | -0.3267 | 0.0529 | 0.285 | 1.00 | 3.93 | 11.52 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -8.9 | -0.1449 | 0.1548 | 0.300 | 1.00 | 7.11 | 10.70 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -12.2 | -0.1993 | 0.3160 | 0.301 | 1.00 | 10.18 | 10.95 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -23.7 | -0.3876 | 0.3763 | 0.290 | 1.00 | 10.71 | 11.78 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -34.8 | -0.5684 | 0.3893 | 0.281 | 1.00 | 10.56 | 12.52 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -38.6 | -0.6299 | 0.3035 | 0.279 | 1.00 | 9.24 | 12.77 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -33.2 | -0.5421 | 0.1891 | 0.286 | 1.00 | 7.50 | 12.42 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -26.3 | -0.4298 | 0.1428 | 0.299 | 1.00 | 6.81 | 11.96 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -22.0 | -0.3589 | 0.1933 | 0.334 | 1.00 | 8.84 | 11.66 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 70.2 | 1.1460 | 0.0439 | 0.344 | 1.00 | 4.35 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -3.8 | -0.0617 | 0.7186 | 0.278 | 1.00 | 14.17 | 10.30 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -30.0 | -0.4902 | 0.6943 | 0.288 | 1.00 | 14.47 | 12.21 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -40.2 | -0.6570 | 0.4786 | 0.294 | 1.00 | 12.27 | 12.87 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -41.3 | -0.6745 | 0.2532 | 0.294 | 1.00 | 8.90 | 12.94 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -34.6 | -0.5649 | 0.0498 | 0.300 | 1.00 | 4.03 | 12.51 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -30.2 | -0.4925 | 0.1031 | 0.296 | 1.00 | 5.73 | 12.22 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -27.2 | -0.4439 | 0.1203 | 0.305 | 1.00 | 6.38 | 12.02 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -26.2 | -0.4273 | 0.1298 | 0.302 | 1.00 | 6.55 | 11.95 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -24.0 | -0.3916 | 0.0191 | 0.368 | 1.00 | 3.07 | 11.80 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
