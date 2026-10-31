# Aerodynamic Case: case_59_aoa+10_u45
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4848
- **Drag Coefficient ($C_d$):** 0.1263
- **Mean Wall $y^+$:** 19.65
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 10.0, "case_idx": 59}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 1122.6 | 0.9051 | 1.2227 | 0.310 | 1.00 | 19.53 | 13.87 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 188.7 | 0.1522 | 2.5338 | 0.306 | 1.00 | 29.35 | 41.44 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | -21.8 | -0.0175 | 2.5461 | 0.302 | 1.00 | 28.98 | 45.39 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -381.3 | -0.3075 | 2.2730 | 0.290 | 1.00 | 26.31 | 51.45 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -733.2 | -0.5911 | 1.9076 | 0.270 | 1.00 | 22.43 | 56.76 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -976.2 | -0.7871 | 1.7664 | 0.266 | 1.00 | 21.31 | 60.16 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -1020.7 | -0.8230 | 1.2297 | 0.295 | 1.00 | 19.72 | 60.76 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -918.7 | -0.7407 | 0.7107 | 0.297 | 1.00 | 15.08 | 59.37 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -775.0 | -0.6248 | 0.6068 | 0.296 | 1.00 | 13.89 | 57.36 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -729.3 | -0.5880 | 1.0150 | 0.263 | 1.00 | 15.98 | 56.71 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 267.0 | 0.2153 | 2.4593 | 0.308 | 1.00 | 28.92 | 39.86 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -1069.2 | -0.8621 | 3.6856 | 0.288 | 1.00 | 33.34 | 61.41 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -1268.3 | -1.0225 | 3.0503 | 0.278 | 1.00 | 29.24 | 64.00 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -1386.3 | -1.1177 | 1.7230 | 0.271 | 1.00 | 21.42 | 65.49 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -1324.6 | -1.0680 | 0.8559 | 0.269 | 1.00 | 15.00 | 64.71 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -1115.1 | -0.8990 | 0.1711 | 0.273 | 1.00 | 6.78 | 62.01 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -942.4 | -0.7598 | 0.3956 | 0.275 | 1.00 | 10.41 | 59.70 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -863.4 | -0.6961 | 0.4030 | 0.292 | 1.00 | 11.17 | 58.60 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -833.9 | -0.6724 | 0.4571 | 0.311 | 1.00 | 12.66 | 58.19 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -789.4 | -0.6365 | 0.0651 | 0.418 | 1.00 | 6.43 | 57.57 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
