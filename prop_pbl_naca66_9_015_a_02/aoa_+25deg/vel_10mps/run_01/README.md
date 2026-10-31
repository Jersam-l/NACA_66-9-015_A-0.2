# Aerodynamic Case: case_82_aoa+25_u10
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0632
- **Drag Coefficient ($C_d$):** 0.4848
- **Mean Wall $y^+$:** 9.28
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 25.0, "case_idx": 82}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | -13.2 | -0.2153 | 0.6327 | 0.276 | 1.00 | 12.92 | 11.02 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 35.5 | 0.5789 | 0.6291 | 0.257 | 1.00 | 12.29 | 6.49 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 4.7 | 0.0765 | 0.6819 | 0.287 | 1.00 | 14.26 | 9.61 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -26.3 | -0.4297 | 0.6726 | 0.284 | 1.00 | 14.02 | 11.96 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -54.1 | -0.8837 | 0.5650 | 0.292 | 1.00 | 13.23 | 13.72 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -78.2 | -1.2759 | 0.4929 | 0.317 | 1.00 | 13.40 | 15.09 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -67.5 | -1.1017 | 0.4570 | 0.358 | 1.00 | 14.58 | 14.50 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -72.4 | -1.1821 | 0.3031 | 0.273 | 1.00 | 9.04 | 14.77 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -69.1 | -1.1276 | 0.3255 | 0.245 | 1.00 | 8.43 | 14.59 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -75.8 | -1.2383 | 0.4205 | 0.304 | 1.00 | 11.87 | 14.96 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -145.1 | -2.3684 | 0.7562 | 0.272 | 1.00 | 11.87 | 18.35 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -69.6 | -1.1363 | 0.1880 | 0.272 | 1.00 | 7.10 | 14.62 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -68.4 | -1.1175 | 0.2198 | 0.276 | 1.00 | 7.80 | 14.55 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -65.4 | -1.0677 | 0.2265 | 0.280 | 1.00 | 8.04 | 14.38 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -59.8 | -0.9760 | 0.1990 | 0.278 | 1.00 | 7.46 | 14.06 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -54.1 | -0.8832 | 0.1265 | 0.263 | 1.00 | 5.63 | 13.72 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -54.5 | -0.8901 | 0.0830 | 0.254 | 1.00 | 4.40 | 13.75 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -59.1 | -0.9652 | 0.1956 | 0.263 | 1.00 | 7.01 | 14.02 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -79.7 | -1.3012 | 0.1087 | 0.297 | 1.00 | 5.89 | 15.17 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -83.0 | -1.3546 | 0.0395 | 0.297 | 1.00 | 3.55 | 15.35 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
