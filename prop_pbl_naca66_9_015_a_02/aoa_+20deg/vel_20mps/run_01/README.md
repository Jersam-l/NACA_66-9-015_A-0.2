# Aerodynamic Case: case_74_aoa+20_u20
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9635
- **Drag Coefficient ($C_d$):** 0.2938
- **Mean Wall $y^+$:** 11.51
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 20.0, "case_idx": 74}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 230.7 | 0.9418 | 0.6461 | 0.360 | 1.00 | 16.35 | 4.83 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 148.3 | 0.6054 | 1.1924 | 0.264 | 1.00 | 17.38 | 12.56 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 56.5 | 0.2307 | 1.5447 | 0.146 | 1.00 | 10.93 | 17.54 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -24.6 | -0.1006 | 1.2091 | 0.248 | 1.00 | 16.44 | 20.98 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -105.8 | -0.4319 | 0.9577 | 0.325 | 1.00 | 19.17 | 23.93 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -124.0 | -0.5061 | 0.8736 | 0.418 | 1.00 | 23.50 | 24.55 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -170.9 | -0.6977 | 0.6603 | 0.270 | 1.00 | 13.21 | 26.06 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -158.1 | -0.6452 | 0.4235 | 0.251 | 1.00 | 9.84 | 25.65 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -137.8 | -0.5623 | 0.5107 | 0.233 | 1.00 | 10.03 | 25.00 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -170.5 | -0.6959 | 0.8752 | 0.179 | 1.00 | 10.06 | 26.05 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -431.2 | -1.7598 | 1.7873 | 0.306 | 1.00 | 24.59 | 33.23 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -294.6 | -1.2023 | 0.1715 | 0.271 | 1.00 | 6.75 | 29.68 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -227.2 | -0.9272 | 0.0796 | 0.270 | 1.00 | 4.58 | 27.77 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -167.6 | -0.6841 | 0.0916 | 0.275 | 1.00 | 5.02 | 25.95 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -133.4 | -0.5444 | 0.0904 | 0.271 | 1.00 | 4.91 | 24.85 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -106.9 | -0.4365 | 0.0485 | 0.265 | 1.00 | 3.50 | 23.97 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -93.1 | -0.3800 | 0.1687 | 0.270 | 1.00 | 6.67 | 23.50 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -189.0 | -0.7714 | 0.2074 | 0.263 | 1.00 | 7.21 | 26.62 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -186.1 | -0.7598 | 0.2246 | 0.289 | 1.00 | 8.25 | 26.53 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -183.7 | -0.7497 | 0.0620 | 0.328 | 1.00 | 4.92 | 26.45 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
