# Aerodynamic Case: case_40_aoa+00_u50
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0483
- **Drag Coefficient ($C_d$):** 0.0879
- **Mean Wall $y^+$:** 18.73
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 0.0, "case_idx": 40}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 1060.1 | 0.6923 | 1.9337 | 0.302 | 1.00 | 25.32 | 27.73 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -550.0 | -0.3592 | 0.3064 | 0.285 | 1.00 | 9.47 | 58.29 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -319.1 | -0.2084 | 0.6798 | 0.300 | 1.00 | 14.89 | 54.96 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -388.3 | -0.2536 | 1.4276 | 0.301 | 1.00 | 21.64 | 55.98 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -671.1 | -0.4382 | 1.6901 | 0.290 | 1.00 | 22.71 | 59.96 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -936.8 | -0.6118 | 1.7261 | 0.281 | 1.00 | 22.23 | 63.48 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -1023.3 | -0.6683 | 1.2805 | 0.279 | 1.00 | 18.99 | 64.58 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -897.5 | -0.5861 | 0.7220 | 0.286 | 1.00 | 14.64 | 62.97 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -731.1 | -0.4775 | 0.5266 | 0.299 | 1.00 | 13.07 | 60.78 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -604.6 | -0.3948 | 0.7921 | 0.334 | 1.00 | 17.89 | 59.05 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 1677.4 | 1.0955 | 0.2072 | 0.344 | 1.00 | 9.44 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -181.7 | -0.1187 | 3.6706 | 0.278 | 1.00 | 32.03 | 52.88 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -830.5 | -0.5424 | 3.7059 | 0.288 | 1.00 | 33.44 | 62.10 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -1048.4 | -0.6846 | 2.7241 | 0.294 | 1.00 | 29.27 | 64.90 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -1113.7 | -0.7273 | 1.4058 | 0.294 | 1.00 | 20.97 | 65.71 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -976.3 | -0.6376 | 0.2942 | 0.300 | 1.00 | 9.79 | 63.98 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -821.5 | -0.5365 | 0.4179 | 0.296 | 1.00 | 11.53 | 61.98 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -717.5 | -0.4685 | 0.4222 | 0.305 | 1.00 | 11.94 | 60.59 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -681.9 | -0.4453 | 0.4787 | 0.302 | 1.00 | 12.59 | 60.11 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -634.8 | -0.4145 | 0.1018 | 0.368 | 1.00 | 7.08 | 59.47 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
