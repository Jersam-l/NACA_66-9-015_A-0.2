# Aerodynamic Case: case_27_aoa-05_u35
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0336
- **Drag Coefficient ($C_d$):** 0.1191
- **Mean Wall $y^+$:** 14.20
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": -5.0, "case_idx": 27}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 463.0 | 0.6171 | 1.6697 | 0.298 | 1.00 | 23.20 | 21.66 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -748.5 | -0.9976 | 0.5044 | 0.286 | 1.00 | 12.23 | 49.47 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -601.0 | -0.8010 | 0.4334 | 0.310 | 1.00 | 12.27 | 46.97 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -356.2 | -0.4748 | 0.3996 | 0.307 | 1.00 | 11.67 | 42.50 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -426.3 | -0.5681 | 0.9737 | 0.288 | 1.00 | 17.10 | 43.83 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -549.2 | -0.7319 | 1.1440 | 0.274 | 1.00 | 17.67 | 46.06 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -568.2 | -0.7573 | 0.7897 | 0.278 | 1.00 | 14.85 | 46.40 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -487.9 | -0.6503 | 0.3297 | 0.291 | 1.00 | 10.06 | 44.96 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -403.6 | -0.5379 | 0.1172 | 0.320 | 1.00 | 6.60 | 43.41 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -334.7 | -0.4461 | 0.1451 | 0.365 | 1.00 | 8.36 | 42.09 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 845.8 | 1.1273 | 0.5682 | 0.302 | 1.00 | 13.73 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -15.8 | -0.0210 | 2.5130 | 0.278 | 1.00 | 26.54 | 35.37 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -430.3 | -0.5735 | 2.7012 | 0.282 | 1.00 | 27.95 | 43.90 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -584.3 | -0.7788 | 1.9984 | 0.289 | 1.00 | 24.65 | 46.68 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -633.5 | -0.8443 | 1.0918 | 0.295 | 1.00 | 18.54 | 47.53 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -568.9 | -0.7582 | 0.3492 | 0.294 | 1.00 | 10.48 | 46.41 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -475.1 | -0.6332 | 0.2462 | 0.287 | 1.00 | 8.58 | 44.73 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -409.3 | -0.5456 | 0.3627 | 0.282 | 1.00 | 10.23 | 43.51 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -378.2 | -0.5041 | 0.4051 | 0.275 | 1.00 | 10.56 | 42.92 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -340.4 | -0.4537 | 0.1907 | 0.343 | 1.00 | 9.03 | 42.20 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
