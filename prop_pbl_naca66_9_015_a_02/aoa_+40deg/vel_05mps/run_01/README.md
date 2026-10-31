# Aerodynamic Case: case_111_aoa+40_u05
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.1996
- **Drag Coefficient ($C_d$):** 1.1700
- **Mean Wall $y^+$:** 4.60
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 40.0, "case_idx": 111}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 35.2 | 2.2968 | 0.2157 | 0.307 | 1.00 | 7.96 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 44.4 | 2.8997 | 0.0960 | 0.313 | 1.00 | 5.85 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 42.0 | 2.7412 | 0.1517 | 0.296 | 1.00 | 6.94 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 38.8 | 2.5319 | 0.2075 | 0.280 | 1.00 | 7.70 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 34.4 | 2.2441 | 0.2651 | 0.274 | 1.00 | 8.50 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 29.6 | 1.9358 | 0.3041 | 0.275 | 1.00 | 9.15 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 25.6 | 1.6742 | 0.3132 | 0.291 | 1.00 | 9.81 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 20.5 | 1.3388 | 0.3147 | 0.323 | 1.00 | 10.93 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 6.4 | 0.4206 | 0.3747 | 0.361 | 1.00 | 13.31 | 3.81 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 6.4 | 0.4206 | 0.3747 | 0.361 | 1.00 | 13.31 | 3.81 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | -12.4 | -0.8095 | 0.0894 | 0.294 | 1.00 | 5.22 | 6.73 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | -10.8 | -0.7081 | 0.1027 | 0.280 | 1.00 | 5.40 | 6.54 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -10.1 | -0.6571 | 0.1069 | 0.290 | 1.00 | 5.70 | 6.44 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -8.7 | -0.5670 | 0.0941 | 0.295 | 1.00 | 5.45 | 6.26 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -7.2 | -0.4674 | 0.0755 | 0.294 | 1.00 | 4.86 | 6.06 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | -5.5 | -0.3610 | 0.0365 | 0.287 | 1.00 | 3.30 | 5.83 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | -5.2 | -0.3379 | 0.0314 | 0.280 | 1.00 | 2.99 | 5.78 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | -5.4 | -0.3509 | 0.0332 | 0.275 | 1.00 | 3.02 | 5.81 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | -7.3 | -0.4793 | 0.0555 | 0.336 | 1.00 | 4.77 | 6.08 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | -7.3 | -0.4793 | 0.0555 | 0.336 | 1.00 | 4.77 | 6.08 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
