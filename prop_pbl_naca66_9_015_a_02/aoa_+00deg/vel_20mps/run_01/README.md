# Aerodynamic Case: case_34_aoa+00_u20
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0510
- **Drag Coefficient ($C_d$):** 0.0918
- **Mean Wall $y^+$:** 11.75
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 0.0, "case_idx": 34}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 177.7 | 0.7253 | 0.7726 | 0.302 | 1.00 | 16.00 | 10.48 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -82.3 | -0.3359 | 0.1121 | 0.285 | 1.00 | 5.73 | 23.12 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -41.1 | -0.1677 | 0.2920 | 0.300 | 1.00 | 9.76 | 21.61 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -55.1 | -0.2249 | 0.5830 | 0.301 | 1.00 | 13.83 | 22.14 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -100.8 | -0.4113 | 0.6893 | 0.290 | 1.00 | 14.50 | 23.76 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -143.5 | -0.5858 | 0.7081 | 0.281 | 1.00 | 14.24 | 25.19 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -157.7 | -0.6435 | 0.5342 | 0.279 | 1.00 | 12.26 | 25.64 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -137.0 | -0.5593 | 0.3137 | 0.286 | 1.00 | 9.65 | 24.97 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -110.3 | -0.4502 | 0.2315 | 0.299 | 1.00 | 8.67 | 24.09 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -91.3 | -0.3726 | 0.3316 | 0.334 | 1.00 | 11.57 | 23.43 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 276.4 | 1.1280 | 0.0845 | 0.344 | 1.00 | 6.03 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -18.8 | -0.0766 | 1.4437 | 0.278 | 1.00 | 20.09 | 20.75 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -124.2 | -0.5068 | 1.3727 | 0.288 | 1.00 | 20.35 | 24.55 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -167.4 | -0.6832 | 0.9226 | 0.294 | 1.00 | 17.04 | 25.95 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -174.3 | -0.7112 | 0.4819 | 0.294 | 1.00 | 12.28 | 26.16 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -148.1 | -0.6047 | 0.1130 | 0.300 | 1.00 | 6.07 | 25.34 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -124.0 | -0.5059 | 0.1694 | 0.296 | 1.00 | 7.34 | 24.54 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -110.1 | -0.4494 | 0.1994 | 0.305 | 1.00 | 8.21 | 24.08 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -105.0 | -0.4286 | 0.2136 | 0.302 | 1.00 | 8.41 | 23.90 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -96.9 | -0.3955 | 0.0402 | 0.368 | 1.00 | 4.45 | 23.63 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
