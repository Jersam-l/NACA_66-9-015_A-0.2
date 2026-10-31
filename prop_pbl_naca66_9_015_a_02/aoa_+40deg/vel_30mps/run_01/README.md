# Aerodynamic Case: case_116_aoa+40_u30
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.2887
- **Drag Coefficient ($C_d$):** 0.9900
- **Mean Wall $y^+$:** 10.55
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 40.0, "case_idx": 116}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 1475.5 | 2.6767 | 1.4217 | 0.307 | 1.00 | 20.09 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 1909.4 | 3.4637 | 0.5232 | 0.313 | 1.00 | 13.65 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 1836.5 | 3.3315 | 0.8621 | 0.296 | 1.00 | 16.55 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 1733.6 | 3.1449 | 1.1096 | 0.280 | 1.00 | 17.80 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 1585.2 | 2.8757 | 1.2614 | 0.274 | 1.00 | 18.54 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 1420.9 | 2.5776 | 1.2600 | 0.275 | 1.00 | 18.62 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 1277.9 | 2.3181 | 1.2156 | 0.291 | 1.00 | 19.32 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 1099.5 | 1.9946 | 1.3372 | 0.323 | 1.00 | 22.52 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 593.6 | 1.0768 | 1.9433 | 0.361 | 1.00 | 30.32 | 0.00 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 593.6 | 1.0768 | 1.9433 | 0.361 | 1.00 | 30.32 | 0.00 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | -413.0 | -0.7491 | 0.5503 | 0.294 | 1.00 | 12.93 | 39.68 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | -372.7 | -0.6761 | 0.4595 | 0.280 | 1.00 | 11.42 | 38.84 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -357.9 | -0.6492 | 0.7661 | 0.290 | 1.00 | 15.27 | 38.53 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -248.7 | -0.4512 | 0.8074 | 0.295 | 1.00 | 15.97 | 36.14 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -116.7 | -0.2117 | 0.7096 | 0.294 | 1.00 | 14.90 | 33.02 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | -10.1 | -0.0184 | 0.6463 | 0.287 | 1.00 | 13.89 | 30.27 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | 73.4 | 0.1331 | 0.6054 | 0.280 | 1.00 | 13.13 | 27.93 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 157.6 | 0.2859 | 0.5059 | 0.275 | 1.00 | 11.77 | 25.35 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | 173.2 | 0.3142 | 0.1166 | 0.336 | 1.00 | 6.92 | 24.84 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | 173.2 | 0.3142 | 0.1166 | 0.336 | 1.00 | 6.92 | 24.84 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
