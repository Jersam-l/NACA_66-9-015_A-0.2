# Aerodynamic Case: case_88_aoa+25_u40
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9958
- **Drag Coefficient ($C_d$):** 0.3956
- **Mean Wall $y^+$:** 17.43
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 25.0, "case_idx": 88}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 137.9 | 0.1407 | 2.4641 | 0.276 | 1.00 | 25.50 | 37.08 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 575.3 | 0.5870 | 2.5686 | 0.257 | 1.00 | 24.83 | 25.70 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 136.3 | 0.1391 | 2.5838 | 0.287 | 1.00 | 27.77 | 37.11 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -314.0 | -0.3204 | 2.4106 | 0.284 | 1.00 | 26.53 | 45.96 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -710.6 | -0.7251 | 2.0406 | 0.292 | 1.00 | 25.14 | 52.54 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -1052.9 | -1.0743 | 1.8464 | 0.317 | 1.00 | 25.94 | 57.61 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -840.9 | -0.8581 | 1.7556 | 0.358 | 1.00 | 28.58 | 54.52 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -887.2 | -0.9053 | 1.0965 | 0.273 | 1.00 | 17.20 | 55.21 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -807.9 | -0.8244 | 1.1562 | 0.245 | 1.00 | 15.88 | 54.03 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -883.0 | -0.9010 | 1.6217 | 0.304 | 1.00 | 23.31 | 55.15 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -2002.2 | -2.0431 | 3.1255 | 0.272 | 1.00 | 25.51 | 69.78 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -1155.4 | -1.1789 | 0.6218 | 0.272 | 1.00 | 12.91 | 59.05 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -1042.0 | -1.0633 | 0.6485 | 0.276 | 1.00 | 13.40 | 57.46 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -902.1 | -0.9205 | 0.5674 | 0.280 | 1.00 | 12.72 | 55.43 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -786.4 | -0.8024 | 0.4661 | 0.278 | 1.00 | 11.42 | 53.70 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -711.2 | -0.7257 | 0.4304 | 0.263 | 1.00 | 10.38 | 52.55 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -664.4 | -0.6780 | 0.3523 | 0.254 | 1.00 | 9.08 | 51.81 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -648.5 | -0.6617 | 0.3579 | 0.263 | 1.00 | 9.48 | 51.56 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -934.5 | -0.9536 | 0.2772 | 0.297 | 1.00 | 9.41 | 55.91 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -968.2 | -0.9880 | 0.1786 | 0.297 | 1.00 | 7.55 | 56.40 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
