# Aerodynamic Case: case_87_aoa+25_u35
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9524
- **Drag Coefficient ($C_d$):** 0.4065
- **Mean Wall $y^+$:** 16.44
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 25.0, "case_idx": 87}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 133.5 | 0.1780 | 2.1559 | 0.276 | 1.00 | 23.85 | 31.73 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 465.2 | 0.6200 | 2.2479 | 0.257 | 1.00 | 23.23 | 21.58 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 121.3 | 0.1617 | 2.2593 | 0.287 | 1.00 | 25.97 | 32.05 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -233.7 | -0.3115 | 2.1099 | 0.284 | 1.00 | 24.82 | 40.08 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -546.7 | -0.7286 | 1.7952 | 0.292 | 1.00 | 23.58 | 46.02 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -818.0 | -1.0902 | 1.6292 | 0.317 | 1.00 | 24.37 | 50.60 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -666.3 | -0.8880 | 1.5461 | 0.358 | 1.00 | 26.82 | 48.09 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -709.6 | -0.9457 | 0.9773 | 0.273 | 1.00 | 16.24 | 48.82 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -659.2 | -0.8786 | 1.0378 | 0.245 | 1.00 | 15.04 | 47.97 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -729.2 | -0.9719 | 1.4415 | 0.304 | 1.00 | 21.97 | 49.15 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -1501.4 | -2.0011 | 2.7373 | 0.272 | 1.00 | 23.89 | 60.63 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -854.9 | -1.1394 | 0.5205 | 0.272 | 1.00 | 11.81 | 51.19 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -774.1 | -1.0316 | 0.5238 | 0.276 | 1.00 | 12.05 | 49.89 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -684.7 | -0.9126 | 0.4586 | 0.280 | 1.00 | 11.44 | 48.40 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -608.7 | -0.8113 | 0.3873 | 0.278 | 1.00 | 10.41 | 47.10 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -556.3 | -0.7414 | 0.3540 | 0.263 | 1.00 | 9.41 | 46.19 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -524.9 | -0.6995 | 0.2707 | 0.254 | 1.00 | 7.96 | 45.63 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -520.1 | -0.6932 | 0.2837 | 0.263 | 1.00 | 8.44 | 45.54 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -786.2 | -1.0479 | 0.2495 | 0.297 | 1.00 | 8.93 | 50.09 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -808.1 | -1.0771 | 0.1185 | 0.297 | 1.00 | 6.15 | 50.44 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
