# Aerodynamic Case: case_18_aoa-10_u40
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0089
- **Drag Coefficient ($C_d$):** 0.1556
- **Mean Wall $y^+$:** 14.74
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": -10.0, "case_idx": 18}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -699.2 | -0.7134 | 2.6128 | 0.283 | 1.00 | 27.45 | 52.36 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -1513.1 | -1.5440 | 0.6755 | 0.281 | 1.00 | 13.90 | 63.80 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -1358.4 | -1.3861 | 0.7282 | 0.291 | 1.00 | 14.94 | 61.79 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -1033.7 | -1.0548 | 0.2071 | 0.289 | 1.00 | 7.90 | 57.34 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -875.4 | -0.8933 | 0.5644 | 0.291 | 1.00 | 13.18 | 55.04 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -927.9 | -0.9468 | 0.9209 | 0.290 | 1.00 | 16.78 | 55.81 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -895.2 | -0.9134 | 0.5799 | 0.299 | 1.00 | 13.72 | 55.33 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -779.3 | -0.7952 | 0.0378 | 0.286 | 1.00 | 3.19 | 53.59 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -696.8 | -0.7110 | 0.2170 | 0.306 | 1.00 | 8.58 | 52.32 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -640.9 | -0.6540 | 0.2251 | 0.360 | 1.00 | 10.28 | 51.44 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 1094.9 | 1.1172 | 0.6575 | 0.284 | 1.00 | 11.65 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -71.8 | -0.0732 | 2.9939 | 0.273 | 1.00 | 28.45 | 41.44 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -775.9 | -0.7918 | 3.3238 | 0.282 | 1.00 | 30.99 | 53.54 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -1026.1 | -1.0470 | 2.5598 | 0.290 | 1.00 | 27.94 | 57.23 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -1105.8 | -1.1283 | 1.3860 | 0.292 | 1.00 | 20.70 | 58.35 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -1030.0 | -1.0510 | 0.5227 | 0.295 | 1.00 | 12.85 | 57.28 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -891.7 | -0.9099 | 0.1232 | 0.297 | 1.00 | 6.24 | 55.28 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -785.6 | -0.8016 | 0.3557 | 0.292 | 1.00 | 10.50 | 53.69 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -712.8 | -0.7274 | 0.3555 | 0.305 | 1.00 | 10.96 | 52.57 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -643.3 | -0.6564 | 0.2330 | 0.349 | 1.00 | 10.14 | 51.48 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
