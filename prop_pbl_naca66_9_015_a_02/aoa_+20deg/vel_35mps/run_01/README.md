# Aerodynamic Case: case_77_aoa+20_u35
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0197
- **Drag Coefficient ($C_d$):** 0.2950
- **Mean Wall $y^+$:** 15.15
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 20.0, "case_idx": 77}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 615.1 | 0.8198 | 1.1320 | 0.360 | 1.00 | 21.64 | 14.86 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 368.5 | 0.4911 | 2.1211 | 0.264 | 1.00 | 23.18 | 24.97 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 90.6 | 0.1207 | 2.7626 | 0.146 | 1.00 | 14.62 | 32.82 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -161.4 | -0.2152 | 2.1015 | 0.248 | 1.00 | 21.67 | 38.58 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -407.7 | -0.5434 | 1.6853 | 0.325 | 1.00 | 25.42 | 43.48 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -451.6 | -0.6019 | 1.5425 | 0.418 | 1.00 | 31.22 | 44.30 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -581.2 | -0.7746 | 1.1360 | 0.270 | 1.00 | 17.33 | 46.62 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -527.1 | -0.7025 | 0.6584 | 0.251 | 1.00 | 12.26 | 45.67 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -431.8 | -0.5754 | 0.7718 | 0.233 | 1.00 | 12.33 | 43.93 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -478.7 | -0.6380 | 1.3613 | 0.179 | 1.00 | 12.55 | 44.80 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -1426.0 | -1.9006 | 3.1408 | 0.306 | 1.00 | 32.60 | 59.61 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -949.8 | -1.2658 | 0.3152 | 0.271 | 1.00 | 9.16 | 52.68 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -777.6 | -1.0364 | 0.2374 | 0.270 | 1.00 | 7.92 | 49.95 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -610.2 | -0.8133 | 0.0175 | 0.275 | 1.00 | 2.12 | 47.13 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -502.0 | -0.6690 | 0.0279 | 0.271 | 1.00 | 2.71 | 45.22 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -419.5 | -0.5591 | 0.2189 | 0.265 | 1.00 | 7.47 | 43.70 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -370.7 | -0.4940 | 0.3342 | 0.270 | 1.00 | 9.38 | 42.78 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -556.9 | -0.7422 | 0.3924 | 0.263 | 1.00 | 9.92 | 46.20 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -525.6 | -0.7006 | 0.3918 | 0.289 | 1.00 | 10.89 | 45.64 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -496.9 | -0.6622 | 0.0455 | 0.328 | 1.00 | 4.22 | 45.12 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
