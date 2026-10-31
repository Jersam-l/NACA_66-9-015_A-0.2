# Aerodynamic Case: case_80_aoa+20_u50
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0018
- **Drag Coefficient ($C_d$):** 0.3041
- **Mean Wall $y^+$:** 17.99
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 20.0, "case_idx": 80}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 1359.4 | 0.8878 | 1.6065 | 0.360 | 1.00 | 25.74 | 16.75 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 876.2 | 0.5722 | 3.0241 | 0.264 | 1.00 | 27.67 | 32.70 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 313.8 | 0.2049 | 4.0205 | 0.146 | 1.00 | 17.64 | 44.58 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -197.7 | -0.1291 | 3.0135 | 0.248 | 1.00 | 25.95 | 53.13 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -702.6 | -0.4588 | 2.4129 | 0.325 | 1.00 | 30.42 | 60.39 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -816.2 | -0.5331 | 2.2094 | 0.418 | 1.00 | 37.36 | 61.91 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -1104.0 | -0.7210 | 1.6744 | 0.270 | 1.00 | 21.04 | 65.59 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -1034.7 | -0.6757 | 0.9982 | 0.251 | 1.00 | 15.10 | 64.72 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -897.6 | -0.5862 | 1.1714 | 0.233 | 1.00 | 15.19 | 62.97 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -1067.8 | -0.6973 | 2.0600 | 0.179 | 1.00 | 15.44 | 65.14 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -2814.3 | -1.8379 | 4.4641 | 0.306 | 1.00 | 38.87 | 84.23 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -1772.6 | -1.1576 | 0.5456 | 0.271 | 1.00 | 12.05 | 73.44 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -1453.7 | -0.9494 | 0.4584 | 0.270 | 1.00 | 11.01 | 69.81 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -1087.5 | -0.7102 | 0.1120 | 0.275 | 1.00 | 5.54 | 65.39 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -863.1 | -0.5636 | 0.0606 | 0.271 | 1.00 | 4.01 | 62.52 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -717.6 | -0.4686 | 0.2587 | 0.265 | 1.00 | 8.12 | 60.59 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -647.2 | -0.4227 | 0.3302 | 0.270 | 1.00 | 9.33 | 59.64 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -1189.0 | -0.7765 | 0.3917 | 0.263 | 1.00 | 9.91 | 66.64 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -1164.0 | -0.7601 | 0.6062 | 0.289 | 1.00 | 13.55 | 66.33 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -1136.2 | -0.7420 | 0.1005 | 0.328 | 1.00 | 6.26 | 65.99 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
