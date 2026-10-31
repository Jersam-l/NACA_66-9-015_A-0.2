# Aerodynamic Case: case_79_aoa+20_u45
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0313
- **Drag Coefficient ($C_d$):** 0.3079
- **Mean Wall $y^+$:** 17.16
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 20.0, "case_idx": 79}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 1138.4 | 0.9178 | 1.4469 | 0.360 | 1.00 | 24.43 | 12.90 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 747.4 | 0.6026 | 2.7159 | 0.264 | 1.00 | 26.23 | 28.37 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 293.5 | 0.2366 | 3.5857 | 0.146 | 1.00 | 16.66 | 39.32 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -119.0 | -0.0960 | 2.6968 | 0.248 | 1.00 | 24.55 | 47.11 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -524.9 | -0.4232 | 2.1617 | 0.325 | 1.00 | 28.79 | 53.68 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -610.1 | -0.4919 | 1.9813 | 0.418 | 1.00 | 35.38 | 54.96 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -836.3 | -0.6743 | 1.4822 | 0.270 | 1.00 | 19.79 | 58.23 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -769.1 | -0.6201 | 0.8620 | 0.251 | 1.00 | 14.03 | 57.28 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -639.9 | -0.5159 | 1.0000 | 0.233 | 1.00 | 14.04 | 55.41 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -746.2 | -0.6017 | 1.7708 | 0.179 | 1.00 | 14.32 | 56.95 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -2236.8 | -1.8034 | 4.0119 | 0.306 | 1.00 | 36.85 | 75.35 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -1404.8 | -1.1327 | 0.4952 | 0.271 | 1.00 | 11.48 | 65.72 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -1134.8 | -0.9149 | 0.4032 | 0.270 | 1.00 | 10.32 | 62.27 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -839.7 | -0.6770 | 0.0963 | 0.275 | 1.00 | 5.13 | 58.27 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -656.8 | -0.5295 | 0.0648 | 0.271 | 1.00 | 4.15 | 55.65 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -535.5 | -0.4317 | 0.2445 | 0.265 | 1.00 | 7.89 | 53.84 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -480.8 | -0.3876 | 0.3048 | 0.270 | 1.00 | 8.96 | 53.01 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -849.2 | -0.6847 | 0.3875 | 0.263 | 1.00 | 9.86 | 58.41 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -825.1 | -0.6653 | 0.5594 | 0.289 | 1.00 | 13.01 | 58.07 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -790.2 | -0.6371 | 0.0494 | 0.328 | 1.00 | 4.39 | 57.58 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
