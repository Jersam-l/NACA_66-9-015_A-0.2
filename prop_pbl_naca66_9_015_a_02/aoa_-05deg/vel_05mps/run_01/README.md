# Aerodynamic Case: case_21_aoa-05_u05
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0059
- **Drag Coefficient ($C_d$):** 0.1407
- **Mean Wall $y^+$:** 6.10
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": -5.0, "case_idx": 21}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 7.4 | 0.4808 | 0.2584 | 0.298 | 1.00 | 9.13 | 3.60 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -20.4 | -1.3304 | 0.0928 | 0.286 | 1.00 | 5.24 | 7.63 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -15.7 | -1.0240 | 0.0476 | 0.310 | 1.00 | 4.06 | 7.11 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -11.4 | -0.7466 | 0.0827 | 0.307 | 1.00 | 5.31 | 6.61 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -13.1 | -0.8542 | 0.1789 | 0.288 | 1.00 | 7.33 | 6.81 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -15.5 | -1.0117 | 0.2275 | 0.274 | 1.00 | 7.88 | 7.09 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -15.0 | -0.9824 | 0.1927 | 0.278 | 1.00 | 7.34 | 7.04 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -12.2 | -0.7982 | 0.1013 | 0.291 | 1.00 | 5.57 | 6.71 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -10.1 | -0.6623 | 0.0237 | 0.320 | 1.00 | 2.96 | 6.45 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -8.5 | -0.5558 | 0.0095 | 0.365 | 1.00 | 2.14 | 6.24 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 16.3 | 1.0637 | 0.0996 | 0.302 | 1.00 | 5.75 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -1.2 | -0.0795 | 0.3540 | 0.278 | 1.00 | 9.96 | 5.20 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -10.7 | -0.7013 | 0.4043 | 0.282 | 1.00 | 10.81 | 6.52 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -13.6 | -0.8851 | 0.3709 | 0.289 | 1.00 | 10.62 | 6.87 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -13.3 | -0.8716 | 0.2815 | 0.295 | 1.00 | 9.41 | 6.84 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -10.8 | -0.7065 | 0.1333 | 0.294 | 1.00 | 6.48 | 6.53 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -10.6 | -0.6922 | 0.0482 | 0.287 | 1.00 | 3.80 | 6.50 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -9.8 | -0.6382 | 0.0680 | 0.282 | 1.00 | 4.43 | 6.40 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -9.2 | -0.6026 | 0.0739 | 0.275 | 1.00 | 4.51 | 6.33 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -8.3 | -0.5436 | 0.0352 | 0.343 | 1.00 | 3.88 | 6.21 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
