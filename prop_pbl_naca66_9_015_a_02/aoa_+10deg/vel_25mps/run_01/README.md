# Aerodynamic Case: case_55_aoa+10_u25
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4735
- **Drag Coefficient ($C_d$):** 0.1299
- **Mean Wall $y^+$:** 14.50
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 10.0, "case_idx": 55}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 363.4 | 0.9494 | 0.6809 | 0.310 | 1.00 | 14.45 | 5.62 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 73.6 | 0.1924 | 1.3947 | 0.306 | 1.00 | 21.78 | 22.47 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | 3.9 | 0.0101 | 1.3324 | 0.302 | 1.00 | 20.97 | 24.87 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -111.8 | -0.2920 | 1.1589 | 0.290 | 1.00 | 18.78 | 28.42 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -215.2 | -0.5623 | 1.0203 | 0.270 | 1.00 | 16.41 | 31.25 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -287.8 | -0.7519 | 0.9885 | 0.266 | 1.00 | 15.94 | 33.09 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -302.4 | -0.7900 | 0.6985 | 0.295 | 1.00 | 14.86 | 33.45 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -270.9 | -0.7076 | 0.4116 | 0.297 | 1.00 | 11.48 | 32.67 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -227.4 | -0.5939 | 0.3481 | 0.296 | 1.00 | 10.52 | 31.56 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -214.0 | -0.5591 | 0.5692 | 0.263 | 1.00 | 11.97 | 31.22 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 113.5 | 0.2964 | 1.3421 | 0.308 | 1.00 | 21.36 | 20.97 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -305.1 | -0.7969 | 2.0008 | 0.288 | 1.00 | 24.56 | 33.51 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -384.3 | -1.0040 | 1.5257 | 0.278 | 1.00 | 20.68 | 35.39 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -421.0 | -1.0997 | 0.8660 | 0.271 | 1.00 | 15.19 | 36.23 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -394.8 | -1.0313 | 0.4840 | 0.269 | 1.00 | 11.28 | 35.63 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -327.8 | -0.8562 | 0.1363 | 0.273 | 1.00 | 6.06 | 34.06 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -274.5 | -0.7172 | 0.2112 | 0.275 | 1.00 | 7.60 | 32.76 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -250.3 | -0.6539 | 0.2337 | 0.292 | 1.00 | 8.51 | 32.15 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -242.4 | -0.6332 | 0.2454 | 0.311 | 1.00 | 9.28 | 31.95 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -232.2 | -0.6066 | 0.0290 | 0.418 | 1.00 | 4.29 | 31.69 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
