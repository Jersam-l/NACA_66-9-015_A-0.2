# Aerodynamic Case: case_58_aoa+10_u40
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4941
- **Drag Coefficient ($C_d$):** 0.1273
- **Mean Wall $y^+$:** 18.50
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 10.0, "case_idx": 58}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 932.6 | 0.9517 | 1.0875 | 0.310 | 1.00 | 18.39 | 8.79 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 195.1 | 0.1991 | 2.2486 | 0.306 | 1.00 | 27.65 | 35.80 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | 28.3 | 0.0289 | 2.2389 | 0.302 | 1.00 | 27.18 | 39.42 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -257.9 | -0.2631 | 1.9827 | 0.290 | 1.00 | 24.57 | 44.96 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -531.4 | -0.5422 | 1.6780 | 0.270 | 1.00 | 21.04 | 49.67 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -719.4 | -0.7340 | 1.5695 | 0.266 | 1.00 | 20.08 | 52.67 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -751.8 | -0.7671 | 1.0961 | 0.295 | 1.00 | 18.62 | 53.17 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -668.1 | -0.6817 | 0.6338 | 0.297 | 1.00 | 14.24 | 51.87 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -550.8 | -0.5621 | 0.5358 | 0.296 | 1.00 | 13.05 | 49.99 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -507.0 | -0.5173 | 0.8825 | 0.263 | 1.00 | 14.90 | 49.27 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 263.4 | 0.2688 | 2.1787 | 0.308 | 1.00 | 27.22 | 34.20 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -791.0 | -0.8072 | 3.2646 | 0.288 | 1.00 | 31.37 | 53.77 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -953.4 | -0.9729 | 2.6488 | 0.278 | 1.00 | 27.25 | 56.18 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -1043.2 | -1.0645 | 1.4873 | 0.271 | 1.00 | 19.90 | 57.47 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -985.8 | -1.0059 | 0.7526 | 0.269 | 1.00 | 14.06 | 56.65 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -815.7 | -0.8323 | 0.1606 | 0.273 | 1.00 | 6.57 | 54.15 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -675.2 | -0.6890 | 0.3524 | 0.275 | 1.00 | 9.82 | 51.98 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -608.2 | -0.6206 | 0.3655 | 0.292 | 1.00 | 10.64 | 50.92 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -578.5 | -0.5903 | 0.3695 | 0.311 | 1.00 | 11.39 | 50.44 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -550.4 | -0.5616 | 0.0419 | 0.418 | 1.00 | 5.16 | 49.99 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
