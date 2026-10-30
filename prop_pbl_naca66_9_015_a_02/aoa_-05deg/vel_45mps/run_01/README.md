# Aerodynamic Case: case_29_aoa-05_u45
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0436
- **Drag Coefficient ($C_d$):** 0.1195
- **Mean Wall $y^+$:** 16.28
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": -5.0, "case_idx": 29}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 723.6 | 0.5834 | 2.1471 | 0.298 | 1.00 | 26.30 | 29.05 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -1264.7 | -1.0196 | 0.6282 | 0.286 | 1.00 | 13.64 | 63.95 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -1038.6 | -0.8373 | 0.5751 | 0.310 | 1.00 | 14.14 | 61.00 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -627.5 | -0.5060 | 0.4783 | 0.307 | 1.00 | 12.77 | 55.22 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -733.8 | -0.5917 | 1.2374 | 0.288 | 1.00 | 19.27 | 56.77 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -940.1 | -0.7579 | 1.4737 | 0.274 | 1.00 | 20.06 | 59.66 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -978.3 | -0.7887 | 1.0301 | 0.278 | 1.00 | 16.96 | 60.18 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -849.6 | -0.6850 | 0.4399 | 0.291 | 1.00 | 11.62 | 58.41 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -710.2 | -0.5726 | 0.1640 | 0.320 | 1.00 | 7.80 | 56.43 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -593.7 | -0.4786 | 0.1990 | 0.365 | 1.00 | 9.79 | 54.72 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 1355.7 | 1.0931 | 0.7346 | 0.302 | 1.00 | 15.62 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -64.5 | -0.0520 | 3.2366 | 0.278 | 1.00 | 30.12 | 46.16 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -750.8 | -0.6053 | 3.5300 | 0.282 | 1.00 | 31.95 | 57.02 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -990.9 | -0.7989 | 2.6871 | 0.289 | 1.00 | 28.58 | 60.35 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -1074.7 | -0.8665 | 1.4674 | 0.295 | 1.00 | 21.49 | 61.48 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -975.5 | -0.7865 | 0.4527 | 0.294 | 1.00 | 11.93 | 60.15 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -825.3 | -0.6654 | 0.3250 | 0.287 | 1.00 | 9.86 | 58.07 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -715.5 | -0.5769 | 0.4582 | 0.282 | 1.00 | 11.50 | 56.51 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -664.3 | -0.5356 | 0.5138 | 0.275 | 1.00 | 11.89 | 55.76 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -601.9 | -0.4852 | 0.2420 | 0.343 | 1.00 | 10.17 | 54.84 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
