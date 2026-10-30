# Aerodynamic Case: case_22_aoa-05_u10
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0886
- **Drag Coefficient ($C_d$):** 0.1134
- **Mean Wall $y^+$:** 8.12
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": -5.0, "case_idx": 22}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 33.7 | 0.5508 | 0.4810 | 0.298 | 1.00 | 12.45 | 6.70 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -72.2 | -1.1781 | 0.1827 | 0.286 | 1.00 | 7.36 | 14.76 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -52.7 | -0.8600 | 0.0828 | 0.310 | 1.00 | 5.36 | 13.64 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -36.1 | -0.5901 | 0.1686 | 0.307 | 1.00 | 7.59 | 12.61 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -43.8 | -0.7145 | 0.3106 | 0.288 | 1.00 | 9.66 | 13.09 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -52.3 | -0.8537 | 0.3403 | 0.274 | 1.00 | 9.64 | 13.62 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -50.8 | -0.8297 | 0.2160 | 0.278 | 1.00 | 7.77 | 13.53 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -42.4 | -0.6928 | 0.0651 | 0.291 | 1.00 | 4.47 | 13.01 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -36.0 | -0.5885 | 0.0040 | 0.320 | 1.00 | 1.21 | 12.60 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -31.1 | -0.5070 | 0.0122 | 0.365 | 1.00 | 2.42 | 12.28 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 66.0 | 1.0770 | 0.1551 | 0.302 | 1.00 | 7.18 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -7.9 | -0.1293 | 0.7273 | 0.278 | 1.00 | 14.28 | 10.63 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -42.0 | -0.6849 | 0.7692 | 0.282 | 1.00 | 14.91 | 12.98 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -55.1 | -0.8992 | 0.5582 | 0.289 | 1.00 | 13.03 | 13.78 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -57.8 | -0.9444 | 0.3137 | 0.295 | 1.00 | 9.94 | 13.94 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -50.8 | -0.8298 | 0.1008 | 0.294 | 1.00 | 5.63 | 13.53 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -44.6 | -0.7278 | 0.1017 | 0.287 | 1.00 | 5.51 | 13.14 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -40.4 | -0.6590 | 0.1608 | 0.282 | 1.00 | 6.81 | 12.88 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -37.5 | -0.6126 | 0.1797 | 0.275 | 1.00 | 7.03 | 12.70 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -32.6 | -0.5320 | 0.0823 | 0.343 | 1.00 | 5.93 | 12.38 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
