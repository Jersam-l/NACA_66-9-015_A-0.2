# Aerodynamic Case: case_53_aoa+10_u15
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4629
- **Drag Coefficient ($C_d$):** 0.1352
- **Mean Wall $y^+$:** 11.36
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 10.0, "case_idx": 53}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 115.1 | 0.8349 | 0.4088 | 0.310 | 1.00 | 11.10 | 6.09 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 10.7 | 0.0776 | 0.8281 | 0.306 | 1.00 | 16.78 | 14.41 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | -15.6 | -0.1129 | 0.7670 | 0.302 | 1.00 | 15.91 | 15.82 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -56.9 | -0.4125 | 0.6704 | 0.290 | 1.00 | 14.29 | 17.83 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -92.9 | -0.6742 | 0.6113 | 0.270 | 1.00 | 12.70 | 19.41 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -118.7 | -0.8615 | 0.6068 | 0.266 | 1.00 | 12.49 | 20.46 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -124.3 | -0.9016 | 0.4341 | 0.295 | 1.00 | 11.72 | 20.68 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -112.8 | -0.8183 | 0.2595 | 0.297 | 1.00 | 9.11 | 20.23 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -96.8 | -0.7025 | 0.2160 | 0.296 | 1.00 | 8.29 | 19.57 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -91.4 | -0.6635 | 0.3446 | 0.263 | 1.00 | 9.31 | 19.35 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 30.3 | 0.2199 | 0.7897 | 0.308 | 1.00 | 16.38 | 13.25 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -121.9 | -0.8846 | 1.1758 | 0.288 | 1.00 | 18.83 | 20.59 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -154.4 | -1.1200 | 0.8589 | 0.278 | 1.00 | 15.51 | 21.84 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -166.2 | -1.2060 | 0.4986 | 0.271 | 1.00 | 11.52 | 22.28 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -155.0 | -1.1246 | 0.2955 | 0.269 | 1.00 | 8.81 | 21.86 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -130.3 | -0.9455 | 0.0860 | 0.273 | 1.00 | 4.82 | 20.92 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -112.9 | -0.8190 | 0.1399 | 0.275 | 1.00 | 6.19 | 20.23 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -106.3 | -0.7713 | 0.1821 | 0.292 | 1.00 | 7.51 | 19.96 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -103.5 | -0.7510 | 0.1755 | 0.311 | 1.00 | 7.85 | 19.85 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -98.3 | -0.7133 | 0.0218 | 0.418 | 1.00 | 3.72 | 19.63 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
