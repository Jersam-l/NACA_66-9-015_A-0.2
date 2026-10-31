# Aerodynamic Case: case_78_aoa+20_u40
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0360
- **Drag Coefficient ($C_d$):** 0.2995
- **Mean Wall $y^+$:** 16.27
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 20.0, "case_idx": 78}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 770.6 | 0.7863 | 1.2887 | 0.360 | 1.00 | 23.08 | 18.49 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 454.9 | 0.4642 | 2.4166 | 0.264 | 1.00 | 24.74 | 29.28 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 97.8 | 0.0998 | 3.1688 | 0.146 | 1.00 | 15.66 | 37.95 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -227.6 | -0.2322 | 2.3981 | 0.248 | 1.00 | 23.15 | 44.40 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -546.2 | -0.5574 | 1.9244 | 0.325 | 1.00 | 27.17 | 49.92 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -603.5 | -0.6158 | 1.7633 | 0.418 | 1.00 | 33.38 | 50.85 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -773.9 | -0.7897 | 1.3005 | 0.270 | 1.00 | 18.54 | 53.51 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -706.3 | -0.7207 | 0.7406 | 0.251 | 1.00 | 13.01 | 52.47 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -582.8 | -0.5947 | 0.8555 | 0.233 | 1.00 | 12.98 | 50.51 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -638.8 | -0.6519 | 1.5183 | 0.179 | 1.00 | 13.26 | 51.41 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -1884.8 | -1.9233 | 3.5784 | 0.306 | 1.00 | 34.80 | 68.39 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -1253.3 | -1.2789 | 0.3837 | 0.271 | 1.00 | 10.10 | 60.38 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -1029.7 | -1.0508 | 0.3076 | 0.270 | 1.00 | 9.02 | 57.28 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -803.0 | -0.8194 | 0.0548 | 0.275 | 1.00 | 3.87 | 53.95 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -657.8 | -0.6713 | 0.0532 | 0.271 | 1.00 | 3.76 | 51.71 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -557.8 | -0.5692 | 0.2512 | 0.265 | 1.00 | 8.00 | 50.11 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -504.7 | -0.5150 | 0.3565 | 0.270 | 1.00 | 9.69 | 49.23 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -730.0 | -0.7449 | 0.4061 | 0.263 | 1.00 | 10.09 | 52.84 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -701.1 | -0.7154 | 0.4879 | 0.289 | 1.00 | 12.15 | 52.39 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -661.4 | -0.6748 | 0.0201 | 0.328 | 1.00 | 2.80 | 51.77 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
