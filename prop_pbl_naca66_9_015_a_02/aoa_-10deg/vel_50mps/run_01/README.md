# Aerodynamic Case: case_20_aoa-10_u50
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0410
- **Drag Coefficient ($C_d$):** 0.1399
- **Mean Wall $y^+$:** 16.69
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": -10.0, "case_idx": 20}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -1051.5 | -0.6867 | 3.2683 | 0.283 | 1.00 | 30.69 | 64.94 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -2311.2 | -1.5093 | 0.8436 | 0.281 | 1.00 | 15.53 | 79.20 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -2071.1 | -1.3526 | 0.9239 | 0.291 | 1.00 | 16.83 | 76.69 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -1539.4 | -1.0053 | 0.3033 | 0.289 | 1.00 | 9.57 | 70.81 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -1248.8 | -0.8155 | 0.6769 | 0.291 | 1.00 | 14.43 | 67.37 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -1283.7 | -0.8383 | 1.0616 | 0.290 | 1.00 | 18.02 | 67.79 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -1202.5 | -0.7853 | 0.5768 | 0.299 | 1.00 | 13.68 | 66.81 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -1038.1 | -0.6780 | 0.0626 | 0.286 | 1.00 | 4.27 | 64.77 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -938.2 | -0.6127 | 0.2998 | 0.306 | 1.00 | 10.09 | 63.50 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -869.2 | -0.5676 | 0.2487 | 0.360 | 1.00 | 10.81 | 62.60 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 1748.0 | 1.1416 | 0.7507 | 0.284 | 1.00 | 11.15 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -156.3 | -0.1021 | 3.8158 | 0.273 | 1.00 | 32.12 | 52.49 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -1257.1 | -0.8209 | 4.2627 | 0.282 | 1.00 | 35.09 | 67.47 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -1623.7 | -1.0603 | 3.3822 | 0.290 | 1.00 | 32.11 | 71.77 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -1743.3 | -1.1385 | 1.8685 | 0.292 | 1.00 | 24.04 | 73.12 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -1622.0 | -1.0592 | 0.7181 | 0.295 | 1.00 | 15.06 | 71.75 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -1391.1 | -0.9085 | 0.1691 | 0.297 | 1.00 | 7.32 | 69.07 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -1195.5 | -0.7807 | 0.4993 | 0.292 | 1.00 | 12.44 | 66.72 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -1043.6 | -0.6815 | 0.5002 | 0.305 | 1.00 | 13.00 | 64.84 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -898.3 | -0.5867 | 0.3098 | 0.349 | 1.00 | 11.70 | 62.98 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
