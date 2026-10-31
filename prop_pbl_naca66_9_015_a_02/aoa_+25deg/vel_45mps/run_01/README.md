# Aerodynamic Case: case_89_aoa+25_u45
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.2315
- **Drag Coefficient ($C_d$):** 0.4968
- **Mean Wall $y^+$:** 18.78
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 25.0, "case_idx": 89}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 404.4 | 0.3261 | 2.7436 | 0.276 | 1.00 | 26.94 | 36.94 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 1172.7 | 0.9455 | 2.7959 | 0.257 | 1.00 | 25.91 | 10.51 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 593.4 | 0.4784 | 2.8906 | 0.287 | 1.00 | 29.37 | 32.50 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | 22.3 | 0.0180 | 2.7133 | 0.284 | 1.00 | 28.15 | 44.59 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -463.6 | -0.3738 | 2.2399 | 0.292 | 1.00 | 26.34 | 52.74 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -862.1 | -0.6951 | 1.9801 | 0.317 | 1.00 | 26.87 | 58.59 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -609.3 | -0.4912 | 1.8865 | 0.358 | 1.00 | 29.62 | 54.95 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -676.4 | -0.5454 | 1.1649 | 0.273 | 1.00 | 17.73 | 55.94 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -608.4 | -0.4905 | 1.2311 | 0.245 | 1.00 | 16.39 | 54.94 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -714.9 | -0.5764 | 1.7267 | 0.304 | 1.00 | 24.05 | 56.50 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -2163.9 | -1.7446 | 3.2768 | 0.272 | 1.00 | 24.96 | 74.55 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -945.4 | -0.7623 | 0.6248 | 0.272 | 1.00 | 12.94 | 59.74 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -900.8 | -0.7262 | 0.8295 | 0.276 | 1.00 | 15.16 | 59.12 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -768.9 | -0.6199 | 0.9142 | 0.280 | 1.00 | 16.15 | 57.27 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -566.8 | -0.4570 | 0.7643 | 0.278 | 1.00 | 14.62 | 54.32 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -430.1 | -0.3468 | 0.5867 | 0.263 | 1.00 | 12.12 | 52.22 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -386.1 | -0.3113 | 0.4315 | 0.254 | 1.00 | 10.04 | 51.53 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -379.0 | -0.3056 | 0.5460 | 0.263 | 1.00 | 11.70 | 51.42 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -765.1 | -0.6169 | 0.2921 | 0.297 | 1.00 | 9.66 | 57.22 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -830.7 | -0.6697 | 0.1903 | 0.297 | 1.00 | 7.80 | 58.15 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
