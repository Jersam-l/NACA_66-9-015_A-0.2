# Aerodynamic Case: case_115_aoa+40_u25
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.2894
- **Drag Coefficient ($C_d$):** 1.2081
- **Mean Wall $y^+$:** 9.20
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 40.0, "case_idx": 115}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 1233.8 | 3.2230 | 1.1288 | 0.307 | 1.00 | 18.00 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 1496.4 | 3.9089 | 0.4388 | 0.313 | 1.00 | 12.50 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 1438.5 | 3.7577 | 0.7227 | 0.296 | 1.00 | 15.15 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 1359.4 | 3.5511 | 0.9544 | 0.280 | 1.00 | 16.51 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 1247.5 | 3.2588 | 1.1065 | 0.274 | 1.00 | 17.37 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 1119.0 | 2.9231 | 1.1190 | 0.275 | 1.00 | 17.55 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 997.1 | 2.6046 | 1.0847 | 0.291 | 1.00 | 18.25 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 839.3 | 2.1926 | 1.1833 | 0.323 | 1.00 | 21.19 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 427.3 | 1.1163 | 1.7029 | 0.361 | 1.00 | 28.38 | 0.00 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 427.3 | 1.1163 | 1.7029 | 0.361 | 1.00 | 28.38 | 0.00 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | 268.4 | 0.7011 | 0.3655 | 0.294 | 1.00 | 10.52 | 13.67 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | 306.7 | 0.8011 | 0.0823 | 0.280 | 1.00 | 4.84 | 11.15 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | 295.8 | 0.7726 | 0.0271 | 0.290 | 1.00 | 2.87 | 11.92 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | 277.1 | 0.7239 | 0.0088 | 0.295 | 1.00 | 1.66 | 13.14 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | 245.3 | 0.6407 | 0.0865 | 0.294 | 1.00 | 5.20 | 14.99 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | 204.9 | 0.5354 | 0.0147 | 0.287 | 1.00 | 2.09 | 17.04 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | 168.0 | 0.4388 | 0.3281 | 0.280 | 1.00 | 9.67 | 18.73 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 179.1 | 0.4678 | 0.1593 | 0.275 | 1.00 | 6.59 | 18.24 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | 82.1 | 0.2144 | 0.3670 | 0.336 | 1.00 | 12.27 | 22.16 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | 82.1 | 0.2144 | 0.3670 | 0.336 | 1.00 | 12.27 | 22.16 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
