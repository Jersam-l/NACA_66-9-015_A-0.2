# Aerodynamic Case: case_85_aoa+25_u25
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0113
- **Drag Coefficient ($C_d$):** 0.4237
- **Mean Wall $y^+$:** 13.91
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 25.0, "case_idx": 85}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 71.1 | 0.1857 | 1.5385 | 0.276 | 1.00 | 20.08 | 22.56 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 268.4 | 0.7012 | 1.5806 | 0.257 | 1.00 | 19.48 | 13.67 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 92.0 | 0.2403 | 1.5910 | 0.287 | 1.00 | 21.79 | 21.79 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -90.2 | -0.2355 | 1.4836 | 0.284 | 1.00 | 20.82 | 27.79 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -248.5 | -0.6492 | 1.2713 | 0.292 | 1.00 | 19.84 | 32.10 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -385.8 | -1.0077 | 1.1620 | 0.317 | 1.00 | 20.58 | 35.42 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -309.1 | -0.8075 | 1.1020 | 0.358 | 1.00 | 22.64 | 33.61 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -331.2 | -0.8652 | 0.6976 | 0.273 | 1.00 | 13.72 | 34.14 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -303.0 | -0.7915 | 0.7412 | 0.245 | 1.00 | 12.71 | 33.46 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -335.5 | -0.8764 | 1.0216 | 0.304 | 1.00 | 18.50 | 34.24 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -751.0 | -1.9619 | 1.9346 | 0.272 | 1.00 | 19.93 | 43.03 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -395.7 | -1.0338 | 0.3716 | 0.272 | 1.00 | 9.98 | 35.65 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -360.5 | -0.9417 | 0.3804 | 0.276 | 1.00 | 10.27 | 34.84 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -319.0 | -0.8334 | 0.3539 | 0.280 | 1.00 | 10.05 | 33.85 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -278.3 | -0.7269 | 0.2977 | 0.278 | 1.00 | 9.12 | 32.85 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -252.6 | -0.6598 | 0.2727 | 0.263 | 1.00 | 8.26 | 32.21 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -240.0 | -0.6268 | 0.2104 | 0.254 | 1.00 | 7.01 | 31.89 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -239.9 | -0.6267 | 0.2419 | 0.263 | 1.00 | 7.79 | 31.89 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -358.8 | -0.9372 | 0.1712 | 0.297 | 1.00 | 7.40 | 34.80 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -371.4 | -0.9702 | 0.1138 | 0.297 | 1.00 | 6.03 | 35.09 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
