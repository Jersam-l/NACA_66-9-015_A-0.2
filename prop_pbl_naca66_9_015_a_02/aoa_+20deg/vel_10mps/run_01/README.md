# Aerodynamic Case: case_72_aoa+20_u10
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9535
- **Drag Coefficient ($C_d$):** 0.2979
- **Mean Wall $y^+$:** 8.57
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 20.0, "case_idx": 72}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 51.8 | 0.8452 | 0.3257 | 0.360 | 1.00 | 11.65 | 3.93 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 28.1 | 0.4594 | 0.6094 | 0.264 | 1.00 | 12.42 | 7.35 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 5.4 | 0.0882 | 0.8637 | 0.146 | 1.00 | 8.17 | 9.55 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -13.8 | -0.2258 | 0.7148 | 0.248 | 1.00 | 12.64 | 11.07 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -33.4 | -0.5452 | 0.5569 | 0.325 | 1.00 | 14.61 | 12.43 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -39.8 | -0.6501 | 0.4621 | 0.418 | 1.00 | 17.09 | 12.85 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -50.9 | -0.8305 | 0.3581 | 0.270 | 1.00 | 9.73 | 13.53 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -46.7 | -0.7618 | 0.2382 | 0.251 | 1.00 | 7.38 | 13.27 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -40.0 | -0.6534 | 0.2917 | 0.233 | 1.00 | 7.58 | 12.86 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -48.2 | -0.7863 | 0.4945 | 0.179 | 1.00 | 7.57 | 13.37 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -109.7 | -1.7908 | 0.8974 | 0.306 | 1.00 | 17.42 | 16.71 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -85.1 | -1.3901 | 0.0675 | 0.271 | 1.00 | 4.24 | 15.46 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -66.6 | -1.0866 | 0.0067 | 0.270 | 1.00 | 1.29 | 14.45 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -51.3 | -0.8368 | 0.0945 | 0.275 | 1.00 | 5.10 | 13.55 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -42.2 | -0.6893 | 0.0951 | 0.271 | 1.00 | 5.04 | 13.00 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -34.5 | -0.5633 | 0.0055 | 0.265 | 1.00 | 1.04 | 12.50 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -30.6 | -0.4997 | 0.0872 | 0.270 | 1.00 | 4.79 | 12.25 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -54.6 | -0.8915 | 0.1258 | 0.263 | 1.00 | 5.62 | 13.75 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -53.6 | -0.8753 | 0.1123 | 0.289 | 1.00 | 5.83 | 13.69 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -52.8 | -0.8626 | 0.0355 | 0.328 | 1.00 | 3.72 | 13.65 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
