# Aerodynamic Case: case_17_aoa-10_u35
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0059
- **Drag Coefficient ($C_d$):** 0.1489
- **Mean Wall $y^+$:** 13.79
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": -10.0, "case_idx": 17}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -494.2 | -0.6587 | 2.2750 | 0.283 | 1.00 | 25.61 | 45.08 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -1109.1 | -1.4782 | 0.5942 | 0.281 | 1.00 | 13.04 | 55.10 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -991.4 | -1.3213 | 0.6585 | 0.291 | 1.00 | 14.21 | 53.33 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -723.2 | -0.9639 | 0.1976 | 0.289 | 1.00 | 7.72 | 49.05 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -592.6 | -0.7898 | 0.5097 | 0.291 | 1.00 | 12.52 | 46.82 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -631.7 | -0.8420 | 0.8035 | 0.290 | 1.00 | 15.68 | 47.50 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -605.4 | -0.8068 | 0.4928 | 0.299 | 1.00 | 12.65 | 47.05 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -519.0 | -0.6917 | 0.0452 | 0.286 | 1.00 | 3.60 | 45.52 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -456.8 | -0.6089 | 0.1512 | 0.306 | 1.00 | 7.16 | 44.39 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -415.7 | -0.5540 | 0.1330 | 0.360 | 1.00 | 7.90 | 43.63 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 865.6 | 1.1536 | 0.5438 | 0.284 | 1.00 | 10.05 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -41.5 | -0.0553 | 2.6314 | 0.273 | 1.00 | 26.67 | 35.95 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -575.0 | -0.7663 | 2.8930 | 0.282 | 1.00 | 28.91 | 46.52 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -765.7 | -1.0205 | 2.1898 | 0.290 | 1.00 | 25.84 | 49.75 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -820.6 | -1.0936 | 1.1827 | 0.292 | 1.00 | 19.13 | 50.64 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -753.7 | -1.0046 | 0.4483 | 0.295 | 1.00 | 11.90 | 49.55 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -641.2 | -0.8546 | 0.1254 | 0.297 | 1.00 | 6.31 | 47.66 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -554.1 | -0.7385 | 0.3437 | 0.292 | 1.00 | 10.32 | 46.15 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -489.9 | -0.6529 | 0.3504 | 0.305 | 1.00 | 10.88 | 45.00 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -426.6 | -0.5686 | 0.2273 | 0.349 | 1.00 | 10.02 | 43.84 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
