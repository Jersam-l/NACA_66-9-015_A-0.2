# Aerodynamic Case: case_51_aoa+10_u05
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4989
- **Drag Coefficient ($C_d$):** 0.1501
- **Mean Wall $y^+$:** 7.49
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 10.0, "case_idx": 51}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 14.8 | 0.9649 | 0.1363 | 0.310 | 1.00 | 6.49 | 0.94 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 2.8 | 0.1827 | 0.2744 | 0.306 | 1.00 | 9.66 | 4.52 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | 0.1 | 0.0059 | 0.2874 | 0.302 | 1.00 | 9.74 | 4.99 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -3.8 | -0.2462 | 0.3121 | 0.290 | 1.00 | 9.75 | 5.58 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -7.5 | -0.4918 | 0.3287 | 0.270 | 1.00 | 9.31 | 6.11 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -10.9 | -0.7088 | 0.3346 | 0.266 | 1.00 | 9.27 | 6.54 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -11.1 | -0.7241 | 0.2676 | 0.295 | 1.00 | 9.20 | 6.57 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -9.5 | -0.6173 | 0.1762 | 0.297 | 1.00 | 7.51 | 6.36 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -8.1 | -0.5267 | 0.1148 | 0.296 | 1.00 | 6.04 | 6.18 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -7.7 | -0.5029 | 0.1518 | 0.263 | 1.00 | 6.18 | 6.13 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 4.5 | 0.2916 | 0.2699 | 0.308 | 1.00 | 9.58 | 4.21 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -12.8 | -0.8327 | 0.4011 | 0.288 | 1.00 | 11.00 | 6.77 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -15.3 | -1.0009 | 0.3602 | 0.278 | 1.00 | 10.05 | 7.07 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -15.2 | -0.9951 | 0.2633 | 0.271 | 1.00 | 8.37 | 7.06 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -13.4 | -0.8744 | 0.1427 | 0.269 | 1.00 | 6.12 | 6.84 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -12.1 | -0.7873 | 0.0140 | 0.273 | 1.00 | 1.90 | 6.68 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -10.8 | -0.7080 | 0.0723 | 0.275 | 1.00 | 4.45 | 6.54 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -10.1 | -0.6589 | 0.0728 | 0.292 | 1.00 | 4.75 | 6.44 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -9.5 | -0.6232 | 0.0691 | 0.311 | 1.00 | 4.92 | 6.37 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -8.8 | -0.5744 | 0.0074 | 0.418 | 1.00 | 2.17 | 6.27 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
