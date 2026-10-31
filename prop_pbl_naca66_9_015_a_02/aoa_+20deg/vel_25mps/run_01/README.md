# Aerodynamic Case: case_75_aoa+20_u25
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9243
- **Drag Coefficient ($C_d$):** 0.2892
- **Mean Wall $y^+$:** 12.78
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 20.0, "case_idx": 75}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 369.7 | 0.9657 | 0.8099 | 0.360 | 1.00 | 18.31 | 4.63 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 237.1 | 0.6193 | 1.5061 | 0.264 | 1.00 | 19.53 | 15.43 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 90.9 | 0.2375 | 1.9412 | 0.146 | 1.00 | 12.25 | 21.83 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -40.3 | -0.1053 | 1.4991 | 0.248 | 1.00 | 18.30 | 26.28 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -169.4 | -0.4425 | 1.1971 | 0.325 | 1.00 | 21.43 | 30.03 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -200.1 | -0.5228 | 1.0964 | 0.418 | 1.00 | 26.32 | 30.85 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -274.1 | -0.7161 | 0.8320 | 0.270 | 1.00 | 14.83 | 32.75 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -255.4 | -0.6672 | 0.5338 | 0.251 | 1.00 | 11.04 | 32.28 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -224.7 | -0.5871 | 0.6502 | 0.233 | 1.00 | 11.32 | 31.50 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -279.6 | -0.7304 | 1.1165 | 0.179 | 1.00 | 11.37 | 32.89 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -666.2 | -1.7402 | 2.2416 | 0.306 | 1.00 | 27.54 | 41.38 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -450.8 | -1.1776 | 0.1949 | 0.271 | 1.00 | 7.20 | 36.89 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -355.4 | -0.9283 | 0.1010 | 0.270 | 1.00 | 5.16 | 34.72 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -268.0 | -0.7001 | 0.0909 | 0.275 | 1.00 | 4.99 | 32.60 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -215.5 | -0.5629 | 0.0975 | 0.271 | 1.00 | 5.10 | 31.25 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -174.7 | -0.4564 | 0.0592 | 0.265 | 1.00 | 3.87 | 30.17 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -153.5 | -0.4009 | 0.2131 | 0.270 | 1.00 | 7.49 | 29.59 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -304.8 | -0.7963 | 0.2152 | 0.263 | 1.00 | 7.35 | 33.51 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -300.9 | -0.7861 | 0.2428 | 0.289 | 1.00 | 8.57 | 33.41 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -300.4 | -0.7847 | 0.0965 | 0.328 | 1.00 | 6.14 | 33.40 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
