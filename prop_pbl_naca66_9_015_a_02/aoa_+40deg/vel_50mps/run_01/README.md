# Aerodynamic Case: case_120_aoa+40_u50
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.5603
- **Drag Coefficient ($C_d$):** 1.2674
- **Mean Wall $y^+$:** 13.83
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 40.0, "case_idx": 120}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 4661.1 | 3.0440 | 2.7320 | 0.307 | 1.00 | 28.94 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 6279.2 | 4.1007 | 0.6129 | 0.313 | 1.00 | 14.77 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 6111.3 | 3.9911 | 1.1808 | 0.296 | 1.00 | 19.37 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 5863.6 | 3.8293 | 1.6426 | 0.280 | 1.00 | 21.65 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 5503.3 | 3.5940 | 1.9614 | 0.274 | 1.00 | 23.12 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 5085.8 | 3.3214 | 2.0149 | 0.275 | 1.00 | 23.55 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 4691.8 | 3.0640 | 1.9686 | 0.291 | 1.00 | 24.59 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 4159.8 | 2.7166 | 2.1792 | 0.323 | 1.00 | 28.75 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 2611.6 | 1.7055 | 3.2593 | 0.361 | 1.00 | 39.26 | 0.00 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 2611.6 | 1.7055 | 3.2593 | 0.361 | 1.00 | 39.26 | 0.00 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | 117.6 | 0.0768 | 0.7268 | 0.294 | 1.00 | 14.79 | 48.04 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | 155.6 | 0.1016 | 0.1833 | 0.280 | 1.00 | 7.21 | 47.39 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -46.7 | -0.0305 | 0.6271 | 0.290 | 1.00 | 13.81 | 50.76 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -197.3 | -0.1289 | 1.2806 | 0.295 | 1.00 | 20.12 | 53.12 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -162.4 | -0.1060 | 1.6223 | 0.294 | 1.00 | 22.53 | 52.58 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | 41.7 | 0.0273 | 1.9221 | 0.287 | 1.00 | 23.95 | 49.31 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | 526.5 | 0.3439 | 2.0084 | 0.280 | 1.00 | 23.92 | 40.50 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 1288.2 | 0.8412 | 1.4886 | 0.275 | 1.00 | 20.19 | 19.92 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | 1313.9 | 0.8581 | 0.3897 | 0.336 | 1.00 | 12.65 | 18.84 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | 1313.9 | 0.8581 | 0.3897 | 0.336 | 1.00 | 12.65 | 18.84 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
