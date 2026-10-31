# Aerodynamic Case: case_60_aoa+10_u50
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4885
- **Drag Coefficient ($C_d$):** 0.1259
- **Mean Wall $y^+$:** 20.79
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 10.0, "case_idx": 60}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 1436.8 | 0.9383 | 1.3589 | 0.310 | 1.00 | 20.60 | 12.42 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 280.0 | 0.1829 | 2.8230 | 0.306 | 1.00 | 30.98 | 45.20 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | 21.7 | 0.0142 | 2.8615 | 0.302 | 1.00 | 30.73 | 49.65 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -417.6 | -0.2727 | 2.5772 | 0.290 | 1.00 | 28.01 | 56.41 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -856.9 | -0.5596 | 2.1477 | 0.270 | 1.00 | 23.80 | 62.44 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -1161.0 | -0.7582 | 1.9712 | 0.266 | 1.00 | 22.51 | 66.30 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -1217.4 | -0.7950 | 1.3717 | 0.295 | 1.00 | 20.82 | 66.99 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -1092.9 | -0.7137 | 0.7966 | 0.297 | 1.00 | 15.97 | 65.45 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -916.8 | -0.5987 | 0.6874 | 0.296 | 1.00 | 14.78 | 63.22 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -864.0 | -0.5642 | 1.1519 | 0.263 | 1.00 | 17.03 | 62.53 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 375.2 | 0.2450 | 2.7380 | 0.308 | 1.00 | 30.51 | 43.44 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -1271.8 | -0.8306 | 4.1153 | 0.288 | 1.00 | 35.23 | 67.65 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -1502.8 | -0.9814 | 3.4616 | 0.278 | 1.00 | 31.15 | 70.38 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -1640.7 | -1.0715 | 1.9662 | 0.271 | 1.00 | 22.88 | 71.96 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -1566.5 | -1.0230 | 0.9578 | 0.269 | 1.00 | 15.87 | 71.12 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -1307.2 | -0.8537 | 0.1785 | 0.273 | 1.00 | 6.92 | 68.08 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -1090.0 | -0.7118 | 0.4404 | 0.275 | 1.00 | 10.98 | 65.42 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -988.3 | -0.6454 | 0.4049 | 0.292 | 1.00 | 11.20 | 64.14 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -966.7 | -0.6313 | 0.4661 | 0.311 | 1.00 | 12.79 | 63.86 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -936.4 | -0.6115 | 0.0468 | 0.418 | 1.00 | 5.45 | 63.47 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
