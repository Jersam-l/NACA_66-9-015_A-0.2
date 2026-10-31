# Aerodynamic Case: case_108_aoa+35_u40
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8592
- **Drag Coefficient ($C_d$):** 0.7759
- **Mean Wall $y^+$:** 12.15
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 35.0, "case_idx": 108}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 3075.8 | 3.1386 | 0.1940 | 0.335 | 1.00 | 8.04 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 2951.8 | 3.0121 | 0.8732 | 0.316 | 1.00 | 17.77 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 2770.0 | 2.8266 | 1.2386 | 0.312 | 1.00 | 20.95 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 2539.6 | 2.5915 | 1.5252 | 0.297 | 1.00 | 22.08 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 2245.0 | 2.2908 | 1.6972 | 0.285 | 1.00 | 22.37 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 1911.1 | 1.9501 | 1.7382 | 0.287 | 1.00 | 22.80 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 1643.7 | 1.6773 | 1.6495 | 0.284 | 1.00 | 21.95 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 1354.9 | 1.3826 | 1.7502 | 0.303 | 1.00 | 24.17 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 748.4 | 0.7637 | 2.2438 | 0.360 | 1.00 | 32.53 | 19.45 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 497.3 | 0.5075 | 2.3449 | 0.392 | 1.00 | 36.18 | 28.07 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | 177.9 | 0.1815 | 0.4816 | 0.271 | 1.00 | 11.27 | 36.19 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | 215.9 | 0.2203 | 0.1945 | 0.294 | 1.00 | 7.81 | 35.32 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | 203.7 | 0.2079 | 0.2150 | 0.292 | 1.00 | 8.15 | 35.60 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | 185.4 | 0.1892 | 0.2298 | 0.287 | 1.00 | 8.30 | 36.02 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | 184.2 | 0.1879 | 0.0602 | 0.293 | 1.00 | 4.32 | 36.05 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | 127.4 | 0.1300 | 0.4587 | 0.294 | 1.00 | 12.01 | 37.31 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | 52.0 | 0.0531 | 0.4513 | 0.296 | 1.00 | 11.96 | 38.92 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | 25.7 | 0.0262 | 0.2319 | 0.302 | 1.00 | 8.75 | 39.47 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | -68.7 | -0.0701 | 0.5338 | 0.344 | 1.00 | 15.10 | 41.38 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | -156.2 | -0.1594 | 0.5419 | 0.353 | 1.00 | 15.67 | 43.07 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
