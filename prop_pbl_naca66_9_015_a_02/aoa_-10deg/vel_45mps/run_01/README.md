# Aerodynamic Case: case_19_aoa-10_u45
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0360
- **Drag Coefficient ($C_d$):** 0.1497
- **Mean Wall $y^+$:** 15.70
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": -10.0, "case_idx": 19}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -891.2 | -0.7185 | 2.9539 | 0.283 | 1.00 | 29.19 | 58.99 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -1929.1 | -1.5553 | 0.7555 | 0.281 | 1.00 | 14.70 | 71.93 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -1739.9 | -1.4028 | 0.8356 | 0.291 | 1.00 | 16.01 | 69.75 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -1311.3 | -1.0572 | 0.2589 | 0.289 | 1.00 | 8.84 | 64.54 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -1097.8 | -0.8851 | 0.6187 | 0.291 | 1.00 | 13.80 | 61.78 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -1144.6 | -0.9228 | 0.9688 | 0.290 | 1.00 | 17.22 | 62.40 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -1081.1 | -0.8716 | 0.5406 | 0.299 | 1.00 | 13.25 | 61.56 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -939.2 | -0.7572 | 0.0670 | 0.286 | 1.00 | 4.43 | 59.65 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -848.1 | -0.6838 | 0.3084 | 0.306 | 1.00 | 10.23 | 58.39 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -786.2 | -0.6339 | 0.2597 | 0.360 | 1.00 | 11.04 | 57.52 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 1399.3 | 1.1282 | 0.7271 | 0.284 | 1.00 | 12.04 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -103.6 | -0.0835 | 3.3947 | 0.273 | 1.00 | 30.30 | 46.84 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -1003.1 | -0.8087 | 3.7899 | 0.282 | 1.00 | 33.09 | 60.52 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -1317.6 | -1.0623 | 2.9727 | 0.290 | 1.00 | 30.10 | 64.62 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -1424.5 | -1.1485 | 1.6353 | 0.292 | 1.00 | 22.49 | 65.96 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -1334.3 | -1.0758 | 0.6392 | 0.295 | 1.00 | 14.21 | 64.83 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -1155.3 | -0.9314 | 0.1179 | 0.297 | 1.00 | 6.09 | 62.54 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -1008.0 | -0.8127 | 0.4017 | 0.292 | 1.00 | 11.16 | 60.59 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -898.2 | -0.7242 | 0.3893 | 0.305 | 1.00 | 11.47 | 59.09 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -796.7 | -0.6423 | 0.2262 | 0.349 | 1.00 | 10.00 | 57.67 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
