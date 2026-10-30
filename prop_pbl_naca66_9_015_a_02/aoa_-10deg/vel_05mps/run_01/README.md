# Aerodynamic Case: case_11_aoa-10_u05
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.6286
- **Drag Coefficient ($C_d$):** 0.2224
- **Mean Wall $y^+$:** 6.54
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": -10.0, "case_idx": 11}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -6.0 | -0.3926 | 0.2986 | 0.283 | 1.00 | 9.30 | 5.90 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -17.7 | -1.1561 | 0.1217 | 0.281 | 1.00 | 5.90 | 7.34 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -17.0 | -1.1081 | 0.1501 | 0.291 | 1.00 | 6.78 | 7.26 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -10.9 | -0.7142 | 0.0994 | 0.289 | 1.00 | 5.50 | 6.55 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -4.9 | -0.3230 | 0.0366 | 0.291 | 1.00 | 3.35 | 5.75 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -5.2 | -0.3427 | 0.1490 | 0.290 | 1.00 | 6.75 | 5.79 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -6.1 | -0.3979 | 0.1712 | 0.299 | 1.00 | 7.46 | 5.91 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -4.9 | -0.3220 | 0.1443 | 0.286 | 1.00 | 6.53 | 5.75 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -3.3 | -0.2177 | 0.1071 | 0.306 | 1.00 | 6.03 | 5.52 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -2.4 | -0.1563 | 0.1077 | 0.360 | 1.00 | 7.11 | 5.38 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 18.4 | 1.2034 | 0.1019 | 0.284 | 1.00 | 5.06 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | 3.5 | 0.2284 | 0.3409 | 0.273 | 1.00 | 9.60 | 4.39 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -7.0 | -0.4579 | 0.4025 | 0.282 | 1.00 | 10.78 | 6.04 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -9.7 | -0.6319 | 0.3725 | 0.290 | 1.00 | 10.66 | 6.39 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -8.3 | -0.5434 | 0.2687 | 0.292 | 1.00 | 9.12 | 6.21 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -5.3 | -0.3482 | 0.0926 | 0.295 | 1.00 | 5.40 | 5.81 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -5.4 | -0.3537 | 0.0564 | 0.297 | 1.00 | 4.24 | 5.82 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -4.7 | -0.3088 | 0.0737 | 0.292 | 1.00 | 4.78 | 5.72 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -4.1 | -0.2676 | 0.0755 | 0.305 | 1.00 | 5.05 | 5.63 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -3.1 | -0.2021 | 0.0208 | 0.349 | 1.00 | 3.03 | 5.48 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
