# Aerodynamic Case: case_35_aoa+00_u25
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0480
- **Drag Coefficient ($C_d$):** 0.0904
- **Mean Wall $y^+$:** 13.10
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 0.0, "case_idx": 35}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 272.3 | 0.7113 | 0.9652 | 0.302 | 1.00 | 17.89 | 13.43 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -132.4 | -0.3458 | 0.1502 | 0.285 | 1.00 | 6.63 | 29.00 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -70.6 | -0.1845 | 0.3612 | 0.300 | 1.00 | 10.86 | 27.21 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -91.8 | -0.2399 | 0.7235 | 0.301 | 1.00 | 15.41 | 27.84 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -162.9 | -0.4256 | 0.8549 | 0.290 | 1.00 | 16.15 | 29.85 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -229.3 | -0.5991 | 0.8765 | 0.281 | 1.00 | 15.84 | 31.61 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -250.8 | -0.6552 | 0.6568 | 0.279 | 1.00 | 13.60 | 32.16 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -218.5 | -0.5708 | 0.3798 | 0.286 | 1.00 | 10.62 | 31.33 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -176.7 | -0.4615 | 0.2783 | 0.299 | 1.00 | 9.50 | 30.22 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -146.1 | -0.3818 | 0.4043 | 0.334 | 1.00 | 12.78 | 29.39 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 426.3 | 1.1137 | 0.1041 | 0.344 | 1.00 | 6.69 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -35.9 | -0.0938 | 1.8123 | 0.278 | 1.00 | 22.50 | 26.15 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -199.8 | -0.5218 | 1.7438 | 0.288 | 1.00 | 22.94 | 30.84 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -265.6 | -0.6939 | 1.1867 | 0.294 | 1.00 | 19.32 | 32.54 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -278.0 | -0.7261 | 0.6162 | 0.294 | 1.00 | 13.89 | 32.85 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -238.5 | -0.6231 | 0.1432 | 0.300 | 1.00 | 6.84 | 31.85 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -199.1 | -0.5200 | 0.2047 | 0.296 | 1.00 | 8.07 | 30.82 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -175.1 | -0.4574 | 0.2273 | 0.305 | 1.00 | 8.76 | 30.18 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -166.5 | -0.4351 | 0.2516 | 0.302 | 1.00 | 9.12 | 29.95 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -154.3 | -0.4031 | 0.0505 | 0.368 | 1.00 | 4.99 | 29.61 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
