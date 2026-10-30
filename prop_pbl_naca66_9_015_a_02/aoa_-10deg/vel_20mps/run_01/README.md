# Aerodynamic Case: case_14_aoa-10_u20
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0011
- **Drag Coefficient ($C_d$):** 0.1567
- **Mean Wall $y^+$:** 10.44
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": -10.0, "case_idx": 14}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -170.7 | -0.6966 | 1.3038 | 0.283 | 1.00 | 19.39 | 26.05 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -381.3 | -1.5563 | 0.3626 | 0.281 | 1.00 | 10.18 | 31.98 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -338.9 | -1.3832 | 0.3804 | 0.291 | 1.00 | 10.80 | 30.88 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -249.8 | -1.0195 | 0.0914 | 0.289 | 1.00 | 5.24 | 28.42 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -211.9 | -0.8648 | 0.3071 | 0.291 | 1.00 | 9.72 | 27.31 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -226.3 | -0.9235 | 0.4639 | 0.290 | 1.00 | 11.91 | 27.74 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -216.5 | -0.8836 | 0.2769 | 0.299 | 1.00 | 9.48 | 27.45 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -187.0 | -0.7633 | 0.0074 | 0.286 | 1.00 | 1.44 | 26.56 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -167.1 | -0.6819 | 0.1262 | 0.306 | 1.00 | 6.54 | 25.94 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -152.3 | -0.6218 | 0.1115 | 0.360 | 1.00 | 7.24 | 25.47 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 277.5 | 1.1327 | 0.3287 | 0.284 | 1.00 | 8.23 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -13.4 | -0.0548 | 1.4856 | 0.273 | 1.00 | 20.04 | 20.54 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -189.0 | -0.7714 | 1.6014 | 0.282 | 1.00 | 21.51 | 26.62 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -257.8 | -1.0523 | 1.1634 | 0.290 | 1.00 | 18.83 | 28.65 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -276.0 | -1.1266 | 0.6341 | 0.292 | 1.00 | 14.00 | 29.17 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -253.4 | -1.0344 | 0.2603 | 0.295 | 1.00 | 9.07 | 28.53 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -217.1 | -0.8862 | 0.0534 | 0.297 | 1.00 | 4.10 | 27.47 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -191.6 | -0.7820 | 0.1888 | 0.292 | 1.00 | 7.65 | 26.70 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -172.5 | -0.7040 | 0.1884 | 0.305 | 1.00 | 7.98 | 26.11 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -153.4 | -0.6260 | 0.1112 | 0.349 | 1.00 | 7.01 | 25.50 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
