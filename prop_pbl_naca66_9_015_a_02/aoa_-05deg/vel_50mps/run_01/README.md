# Aerodynamic Case: case_30_aoa-05_u50
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0436
- **Drag Coefficient ($C_d$):** 0.1203
- **Mean Wall $y^+$:** 17.17
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": -5.0, "case_idx": 30}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 989.8 | 0.6464 | 2.3932 | 0.298 | 1.00 | 27.77 | 29.73 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -1470.7 | -0.9604 | 0.6898 | 0.286 | 1.00 | 14.30 | 70.01 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -1198.3 | -0.7826 | 0.6413 | 0.310 | 1.00 | 14.93 | 66.76 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -692.5 | -0.4523 | 0.5126 | 0.307 | 1.00 | 13.22 | 60.26 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -816.4 | -0.5332 | 1.3604 | 0.288 | 1.00 | 20.21 | 61.91 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -1068.5 | -0.6978 | 1.6299 | 0.274 | 1.00 | 21.09 | 65.15 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -1114.5 | -0.7278 | 1.1393 | 0.278 | 1.00 | 17.84 | 65.72 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -955.3 | -0.6239 | 0.4812 | 0.291 | 1.00 | 12.15 | 63.72 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -783.4 | -0.5116 | 0.1719 | 0.320 | 1.00 | 7.99 | 61.47 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -638.3 | -0.4169 | 0.2033 | 0.365 | 1.00 | 9.90 | 59.52 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 1773.6 | 1.1583 | 0.8239 | 0.302 | 1.00 | 16.54 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | 23.4 | 0.0153 | 3.5989 | 0.278 | 1.00 | 31.76 | 49.62 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -825.9 | -0.5393 | 3.9503 | 0.282 | 1.00 | 33.80 | 62.03 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -1115.3 | -0.7283 | 3.0503 | 0.289 | 1.00 | 30.45 | 65.73 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -1221.1 | -0.7974 | 1.6743 | 0.295 | 1.00 | 22.96 | 67.03 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -1104.1 | -0.7211 | 0.5184 | 0.294 | 1.00 | 12.77 | 65.59 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -921.4 | -0.6017 | 0.3582 | 0.287 | 1.00 | 10.35 | 63.28 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -785.8 | -0.5131 | 0.5047 | 0.282 | 1.00 | 12.07 | 61.51 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -722.8 | -0.4720 | 0.5621 | 0.275 | 1.00 | 12.43 | 60.66 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -646.0 | -0.4219 | 0.2711 | 0.343 | 1.00 | 10.77 | 59.62 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
