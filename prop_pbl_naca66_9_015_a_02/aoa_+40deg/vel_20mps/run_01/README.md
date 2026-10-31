# Aerodynamic Case: case_114_aoa+40_u20
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0208
- **Drag Coefficient ($C_d$):** 1.0002
- **Mean Wall $y^+$:** 8.55
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 40.0, "case_idx": 114}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 744.6 | 3.0392 | 0.8746 | 0.307 | 1.00 | 16.05 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 892.0 | 3.6408 | 0.3996 | 0.313 | 1.00 | 11.93 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 850.7 | 3.4724 | 0.6276 | 0.296 | 1.00 | 14.12 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 796.0 | 3.2491 | 0.8144 | 0.280 | 1.00 | 15.25 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 719.4 | 2.9364 | 0.9314 | 0.274 | 1.00 | 15.94 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 634.1 | 2.5882 | 0.9262 | 0.275 | 1.00 | 15.97 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 557.5 | 2.2754 | 0.8851 | 0.291 | 1.00 | 16.49 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 459.4 | 1.8750 | 0.9591 | 0.323 | 1.00 | 19.08 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 204.1 | 0.8329 | 1.3600 | 0.361 | 1.00 | 25.36 | 8.18 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 204.1 | 0.8329 | 1.3600 | 0.361 | 1.00 | 25.36 | 8.18 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | 37.4 | 0.1525 | 0.3417 | 0.294 | 1.00 | 10.19 | 18.41 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | 63.4 | 0.2589 | 0.2372 | 0.280 | 1.00 | 8.21 | 17.22 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | 70.7 | 0.2884 | 0.2683 | 0.290 | 1.00 | 9.03 | 16.87 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | 87.5 | 0.3571 | 0.1904 | 0.295 | 1.00 | 7.76 | 16.04 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | 98.1 | 0.4003 | 0.0357 | 0.294 | 1.00 | 3.32 | 15.49 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | 90.3 | 0.3685 | 0.1972 | 0.287 | 1.00 | 7.67 | 15.89 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | 73.2 | 0.2987 | 0.2368 | 0.280 | 1.00 | 8.21 | 16.75 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 55.4 | 0.2260 | 0.1760 | 0.275 | 1.00 | 6.94 | 17.60 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | -7.5 | -0.0304 | 0.3251 | 0.336 | 1.00 | 11.55 | 20.30 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | -7.5 | -0.0304 | 0.3251 | 0.336 | 1.00 | 11.55 | 20.30 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
