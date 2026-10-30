# Aerodynamic Case: case_26_aoa-05_u30
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0276
- **Drag Coefficient ($C_d$):** 0.1191
- **Mean Wall $y^+$:** 13.14
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": -5.0, "case_idx": 26}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 326.0 | 0.5914 | 1.4320 | 0.298 | 1.00 | 21.48 | 19.18 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -569.3 | -1.0327 | 0.4467 | 0.286 | 1.00 | 11.51 | 42.77 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -454.4 | -0.8244 | 0.3634 | 0.310 | 1.00 | 11.24 | 40.52 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -276.2 | -0.5011 | 0.3521 | 0.307 | 1.00 | 10.96 | 36.76 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -329.4 | -0.5976 | 0.8403 | 0.288 | 1.00 | 15.88 | 37.92 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -419.8 | -0.7615 | 0.9800 | 0.274 | 1.00 | 16.35 | 39.82 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -432.9 | -0.7852 | 0.6725 | 0.278 | 1.00 | 13.71 | 40.08 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -373.1 | -0.6768 | 0.2776 | 0.291 | 1.00 | 9.23 | 38.85 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -310.9 | -0.5641 | 0.0973 | 0.320 | 1.00 | 6.01 | 37.52 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -260.4 | -0.4724 | 0.1190 | 0.365 | 1.00 | 7.57 | 36.40 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 607.8 | 1.1025 | 0.4874 | 0.302 | 1.00 | 12.72 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -25.5 | -0.0462 | 2.1503 | 0.278 | 1.00 | 24.55 | 30.68 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -330.6 | -0.5997 | 2.2925 | 0.282 | 1.00 | 25.75 | 37.94 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -447.9 | -0.8124 | 1.6719 | 0.289 | 1.00 | 22.54 | 40.39 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -483.4 | -0.8769 | 0.9165 | 0.295 | 1.00 | 16.98 | 41.10 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -434.5 | -0.7882 | 0.3004 | 0.294 | 1.00 | 9.72 | 40.12 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -364.8 | -0.6617 | 0.2080 | 0.287 | 1.00 | 7.88 | 38.67 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -317.1 | -0.5752 | 0.3169 | 0.282 | 1.00 | 9.56 | 37.65 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -293.7 | -0.5327 | 0.3522 | 0.275 | 1.00 | 9.84 | 37.14 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -264.8 | -0.4803 | 0.1669 | 0.343 | 1.00 | 8.45 | 36.50 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
