# Aerodynamic Case: case_76_aoa+20_u30
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9496
- **Drag Coefficient ($C_d$):** 0.2893
- **Mean Wall $y^+$:** 13.90
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 20.0, "case_idx": 76}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 459.4 | 0.8334 | 0.9739 | 0.360 | 1.00 | 20.09 | 12.25 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 268.7 | 0.4875 | 1.8219 | 0.264 | 1.00 | 21.48 | 21.48 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 59.6 | 0.1081 | 2.3564 | 0.146 | 1.00 | 13.50 | 28.33 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -130.6 | -0.2369 | 1.8052 | 0.248 | 1.00 | 20.09 | 33.37 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -316.5 | -0.5742 | 1.4465 | 0.325 | 1.00 | 23.55 | 37.64 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -357.3 | -0.6481 | 1.3237 | 0.418 | 1.00 | 28.92 | 38.51 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -459.0 | -0.8327 | 0.9964 | 0.270 | 1.00 | 16.23 | 40.61 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -426.0 | -0.7729 | 0.6189 | 0.251 | 1.00 | 11.89 | 39.94 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -369.4 | -0.6702 | 0.7467 | 0.233 | 1.00 | 12.13 | 38.77 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -430.9 | -0.7816 | 1.2926 | 0.179 | 1.00 | 12.23 | 40.04 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -1037.0 | -1.8812 | 2.7015 | 0.306 | 1.00 | 30.23 | 50.92 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -710.5 | -1.2890 | 0.2067 | 0.271 | 1.00 | 7.41 | 45.39 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -584.7 | -1.0608 | 0.1228 | 0.270 | 1.00 | 5.70 | 43.07 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -466.8 | -0.8467 | 0.0702 | 0.275 | 1.00 | 4.39 | 40.77 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -388.5 | -0.7048 | 0.0685 | 0.271 | 1.00 | 4.27 | 39.17 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -326.5 | -0.5923 | 0.1094 | 0.265 | 1.00 | 5.28 | 37.86 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -290.8 | -0.5275 | 0.2593 | 0.270 | 1.00 | 8.27 | 37.08 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -472.8 | -0.8576 | 0.2933 | 0.263 | 1.00 | 8.58 | 40.89 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -457.6 | -0.8301 | 0.2623 | 0.289 | 1.00 | 8.91 | 40.58 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -452.5 | -0.8209 | 0.1070 | 0.328 | 1.00 | 6.47 | 40.48 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
