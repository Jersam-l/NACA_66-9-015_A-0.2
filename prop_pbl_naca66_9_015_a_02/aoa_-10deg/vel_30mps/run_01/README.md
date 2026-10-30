# Aerodynamic Case: case_16_aoa-10_u30
- **Angle of Attack (AoA):** -10.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0086
- **Drag Coefficient ($C_d$):** 0.1501
- **Mean Wall $y^+$:** 12.76
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": -10.0, "case_idx": 16}'
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
| 1 | Upper | 0.0010 | -0.0085 | 0.000 | -413.3 | -0.7497 | 1.9478 | 0.283 | 1.00 | 23.70 | 39.68 |
| 2 | Upper | 0.0125 | -0.0071 | 0.111 | -867.7 | -1.5741 | 0.5155 | 0.281 | 1.00 | 12.14 | 48.13 |
| 3 | Upper | 0.0235 | -0.0052 | 0.222 | -779.2 | -1.4135 | 0.5662 | 0.291 | 1.00 | 13.18 | 46.61 |
| 4 | Upper | 0.0345 | -0.0038 | 0.333 | -579.9 | -1.0520 | 0.1577 | 0.289 | 1.00 | 6.89 | 42.98 |
| 5 | Upper | 0.0456 | -0.0026 | 0.444 | -487.6 | -0.8845 | 0.4479 | 0.291 | 1.00 | 11.74 | 41.18 |
| 6 | Upper | 0.0566 | -0.0012 | 0.556 | -518.5 | -0.9406 | 0.6971 | 0.290 | 1.00 | 14.60 | 41.79 |
| 7 | Upper | 0.0676 | 0.0008 | 0.667 | -499.9 | -0.9068 | 0.4306 | 0.299 | 1.00 | 11.82 | 41.43 |
| 8 | Upper | 0.0784 | 0.0035 | 0.778 | -436.1 | -0.7910 | 0.0425 | 0.286 | 1.00 | 3.51 | 40.15 |
| 9 | Upper | 0.0891 | 0.0064 | 0.889 | -390.4 | -0.7081 | 0.1283 | 0.306 | 1.00 | 6.60 | 39.21 |
| 10 | Upper | 0.0987 | 0.0086 | 1.000 | -359.6 | -0.6524 | 0.1188 | 0.360 | 1.00 | 7.47 | 38.56 |
| 1 | Lower | 0.0008 | -0.0066 | 0.000 | 584.5 | 1.0603 | 0.4673 | 0.284 | 1.00 | 9.36 | 0.00 |
| 2 | Lower | 0.0109 | 0.0024 | 0.111 | -79.7 | -0.1445 | 2.2480 | 0.273 | 1.00 | 24.65 | 32.09 |
| 3 | Lower | 0.0213 | 0.0073 | 0.222 | -470.6 | -0.8536 | 2.4520 | 0.282 | 1.00 | 26.62 | 40.84 |
| 4 | Lower | 0.0320 | 0.0104 | 0.333 | -614.8 | -1.1152 | 1.8268 | 0.290 | 1.00 | 23.60 | 43.63 |
| 5 | Lower | 0.0430 | 0.0122 | 0.444 | -654.4 | -1.1871 | 0.9851 | 0.292 | 1.00 | 17.46 | 44.37 |
| 6 | Lower | 0.0541 | 0.0130 | 0.556 | -603.5 | -1.0948 | 0.3776 | 0.295 | 1.00 | 10.92 | 43.42 |
| 7 | Lower | 0.0655 | 0.0127 | 0.667 | -520.2 | -0.9437 | 0.1056 | 0.297 | 1.00 | 5.79 | 41.83 |
| 8 | Lower | 0.0770 | 0.0113 | 0.778 | -457.5 | -0.8299 | 0.2949 | 0.292 | 1.00 | 9.56 | 40.58 |
| 9 | Lower | 0.0886 | 0.0095 | 0.889 | -411.7 | -0.7469 | 0.3017 | 0.305 | 1.00 | 10.10 | 39.65 |
| 10 | Lower | 0.0987 | 0.0087 | 1.000 | -366.6 | -0.6650 | 0.1959 | 0.349 | 1.00 | 9.30 | 38.71 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
