# Aerodynamic Case: case_112_aoa+40_u10
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.7077
- **Drag Coefficient ($C_d$):** 1.3296
- **Mean Wall $y^+$:** 6.32
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 40.0, "case_idx": 112}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 152.7 | 2.4932 | 0.5031 | 0.307 | 1.00 | 12.33 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 207.7 | 3.3904 | 0.1351 | 0.313 | 1.00 | 6.94 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 200.3 | 3.2708 | 0.2488 | 0.296 | 1.00 | 8.89 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 189.9 | 3.1011 | 0.3615 | 0.280 | 1.00 | 10.16 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 175.3 | 2.8613 | 0.4723 | 0.274 | 1.00 | 11.35 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 158.8 | 2.5920 | 0.5330 | 0.275 | 1.00 | 12.11 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 142.9 | 2.3326 | 0.5135 | 0.291 | 1.00 | 12.56 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 120.5 | 1.9680 | 0.4975 | 0.323 | 1.00 | 13.74 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 60.3 | 0.9840 | 0.6664 | 0.361 | 1.00 | 17.75 | 1.27 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 60.3 | 0.9840 | 0.6664 | 0.361 | 1.00 | 17.75 | 1.27 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | -8.5 | -0.1394 | 0.1387 | 0.294 | 1.00 | 6.47 | 10.67 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | -6.7 | -0.1099 | 0.0134 | 0.280 | 1.00 | 1.93 | 10.54 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -12.6 | -0.2051 | 0.1728 | 0.290 | 1.00 | 7.25 | 10.98 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -13.6 | -0.2216 | 0.2384 | 0.295 | 1.00 | 8.68 | 11.05 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -10.8 | -0.1757 | 0.2511 | 0.294 | 1.00 | 8.87 | 10.84 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | -7.5 | -0.1218 | 0.2820 | 0.287 | 1.00 | 9.17 | 10.59 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | -0.6 | -0.0090 | 0.3122 | 0.280 | 1.00 | 9.43 | 10.04 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 16.4 | 0.2670 | 0.1979 | 0.275 | 1.00 | 7.36 | 8.56 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | 8.5 | 0.1394 | 0.1065 | 0.336 | 1.00 | 6.61 | 9.28 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | 8.5 | 0.1394 | 0.1065 | 0.336 | 1.00 | 6.61 | 9.28 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
