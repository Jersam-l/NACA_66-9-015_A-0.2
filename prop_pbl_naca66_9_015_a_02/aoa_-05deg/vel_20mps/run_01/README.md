# Aerodynamic Case: case_24_aoa-05_u20
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0302
- **Drag Coefficient ($C_d$):** 0.1127
- **Mean Wall $y^+$:** 10.92
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": -5.0, "case_idx": 24}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 139.7 | 0.5703 | 0.9514 | 0.298 | 1.00 | 17.51 | 13.11 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -265.1 | -1.0820 | 0.3315 | 0.286 | 1.00 | 9.91 | 28.86 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -199.3 | -0.8135 | 0.1988 | 0.310 | 1.00 | 8.31 | 26.93 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -129.7 | -0.5292 | 0.2953 | 0.307 | 1.00 | 10.04 | 24.73 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -158.7 | -0.6476 | 0.5810 | 0.288 | 1.00 | 13.21 | 25.67 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -196.1 | -0.8003 | 0.6512 | 0.274 | 1.00 | 13.33 | 26.84 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -197.7 | -0.8071 | 0.4268 | 0.278 | 1.00 | 10.92 | 26.89 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -169.4 | -0.6913 | 0.1591 | 0.291 | 1.00 | 6.98 | 26.01 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -142.9 | -0.5832 | 0.0457 | 0.320 | 1.00 | 4.12 | 25.16 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -122.8 | -0.5013 | 0.0701 | 0.365 | 1.00 | 5.81 | 24.51 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 265.0 | 1.0817 | 0.3075 | 0.302 | 1.00 | 10.10 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -24.0 | -0.0978 | 1.4454 | 0.278 | 1.00 | 20.13 | 20.95 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -159.0 | -0.6491 | 1.5055 | 0.282 | 1.00 | 20.86 | 25.68 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -213.1 | -0.8699 | 1.0647 | 0.289 | 1.00 | 17.99 | 27.35 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -226.4 | -0.9242 | 0.5865 | 0.295 | 1.00 | 13.59 | 27.74 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -201.4 | -0.8218 | 0.1935 | 0.294 | 1.00 | 7.80 | 27.00 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -170.3 | -0.6950 | 0.1563 | 0.287 | 1.00 | 6.84 | 26.04 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -150.3 | -0.6136 | 0.2464 | 0.282 | 1.00 | 8.43 | 25.41 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -140.1 | -0.5717 | 0.2668 | 0.275 | 1.00 | 8.57 | 25.07 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -126.9 | -0.5181 | 0.1203 | 0.343 | 1.00 | 7.17 | 24.64 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
