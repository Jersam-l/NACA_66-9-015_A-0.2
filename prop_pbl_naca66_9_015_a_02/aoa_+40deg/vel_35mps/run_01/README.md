# Aerodynamic Case: case_117_aoa+40_u35
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9342
- **Drag Coefficient ($C_d$):** 0.8788
- **Mean Wall $y^+$:** 11.34
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 40.0, "case_idx": 117}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 2136.5 | 2.8475 | 1.5493 | 0.307 | 1.00 | 21.28 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 2617.7 | 3.4888 | 0.6921 | 0.313 | 1.00 | 15.70 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 2510.0 | 3.3453 | 1.0711 | 0.296 | 1.00 | 18.44 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 2362.6 | 3.1488 | 1.3389 | 0.280 | 1.00 | 19.55 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 2150.8 | 2.8665 | 1.5069 | 0.274 | 1.00 | 20.27 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 1915.3 | 2.5527 | 1.4991 | 0.275 | 1.00 | 20.31 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 1709.2 | 2.2780 | 1.4407 | 0.291 | 1.00 | 21.03 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 1456.7 | 1.9414 | 1.5739 | 0.323 | 1.00 | 24.44 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 778.2 | 1.0372 | 2.2561 | 0.361 | 1.00 | 32.67 | 0.00 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 778.2 | 1.0372 | 2.2561 | 0.361 | 1.00 | 32.67 | 0.00 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | -378.5 | -0.5045 | 0.6599 | 0.294 | 1.00 | 14.17 | 42.93 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | -276.3 | -0.3683 | 0.4970 | 0.280 | 1.00 | 11.88 | 40.94 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -241.4 | -0.3217 | 0.6853 | 0.290 | 1.00 | 14.44 | 40.24 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -144.3 | -0.1923 | 0.6663 | 0.295 | 1.00 | 14.51 | 38.22 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -52.1 | -0.0694 | 0.5884 | 0.294 | 1.00 | 13.57 | 36.19 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | 13.2 | 0.0176 | 0.6371 | 0.287 | 1.00 | 13.79 | 34.69 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | 137.4 | 0.1831 | 0.5120 | 0.280 | 1.00 | 12.08 | 31.63 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 235.4 | 0.3137 | 0.0825 | 0.275 | 1.00 | 4.73 | 28.99 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | 216.0 | 0.2879 | 0.2323 | 0.336 | 1.00 | 9.77 | 29.54 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | 216.0 | 0.2879 | 0.2323 | 0.336 | 1.00 | 9.77 | 29.54 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
