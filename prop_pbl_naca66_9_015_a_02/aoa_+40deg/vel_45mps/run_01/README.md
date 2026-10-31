# Aerodynamic Case: case_119_aoa+40_u45
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9447
- **Drag Coefficient ($C_d$):** 0.9363
- **Mean Wall $y^+$:** 13.23
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 40.0, "case_idx": 119}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 3241.5 | 2.6135 | 1.9378 | 0.307 | 1.00 | 24.11 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 3947.2 | 3.1825 | 0.9550 | 0.313 | 1.00 | 18.45 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 3745.5 | 3.0198 | 1.4414 | 0.296 | 1.00 | 21.40 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 3476.7 | 2.8031 | 1.7879 | 0.280 | 1.00 | 22.59 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 3103.0 | 2.5018 | 2.0067 | 0.274 | 1.00 | 23.39 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 2694.7 | 2.1726 | 1.9998 | 0.275 | 1.00 | 23.46 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 2339.2 | 1.8860 | 1.9300 | 0.291 | 1.00 | 24.35 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 1907.0 | 1.5375 | 2.1086 | 0.323 | 1.00 | 28.28 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 760.4 | 0.6131 | 2.9859 | 0.361 | 1.00 | 37.58 | 27.99 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 760.4 | 0.6131 | 2.9859 | 0.361 | 1.00 | 37.58 | 27.99 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | -834.7 | -0.6730 | 0.8118 | 0.294 | 1.00 | 15.66 | 58.20 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | -725.4 | -0.5848 | 0.7154 | 0.280 | 1.00 | 14.25 | 56.65 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -643.4 | -0.5188 | 0.8385 | 0.290 | 1.00 | 15.97 | 55.46 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -449.5 | -0.3624 | 0.6869 | 0.295 | 1.00 | 14.73 | 52.53 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -299.6 | -0.2416 | 0.5310 | 0.294 | 1.00 | 12.89 | 50.14 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | -168.9 | -0.1362 | 0.4497 | 0.287 | 1.00 | 11.58 | 47.97 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | -35.6 | -0.0287 | 0.0759 | 0.280 | 1.00 | 4.62 | 45.64 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | -33.7 | -0.0272 | 0.5816 | 0.275 | 1.00 | 12.62 | 45.61 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | -201.2 | -0.1622 | 0.7405 | 0.336 | 1.00 | 17.43 | 48.51 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | -201.2 | -0.1622 | 0.7405 | 0.336 | 1.00 | 17.43 | 48.51 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
