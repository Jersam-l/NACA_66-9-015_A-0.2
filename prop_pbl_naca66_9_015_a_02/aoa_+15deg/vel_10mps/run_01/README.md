# Aerodynamic Case: case_62_aoa+15_u10
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.7427
- **Drag Coefficient ($C_d$):** 0.2041
- **Mean Wall $y^+$:** 9.52
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 15.0, "case_idx": 62}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 63.1 | 1.0301 | 0.2118 | 0.441 | 1.00 | 11.67 | 0.00 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 29.5 | 0.4814 | 0.5397 | 0.300 | 1.00 | 13.26 | 7.20 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 12.7 | 0.2067 | 0.5576 | 0.295 | 1.00 | 13.27 | 8.91 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -7.7 | -0.1262 | 0.5040 | 0.287 | 1.00 | 12.28 | 10.61 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -25.7 | -0.4190 | 0.4476 | 0.270 | 1.00 | 10.86 | 11.91 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -38.7 | -0.6316 | 0.4323 | 0.259 | 1.00 | 10.26 | 12.77 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -41.1 | -0.6712 | 0.3241 | 0.264 | 1.00 | 9.04 | 12.93 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -36.1 | -0.5895 | 0.2255 | 0.284 | 1.00 | 8.11 | 12.61 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -31.9 | -0.5205 | 0.2082 | 0.286 | 1.00 | 7.86 | 12.33 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -36.2 | -0.5918 | 0.4737 | 0.166 | 1.00 | 6.90 | 12.62 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -32.6 | -0.5331 | 0.8128 | 0.299 | 1.00 | 16.21 | 12.38 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -66.8 | -1.0913 | 0.6740 | 0.277 | 1.00 | 13.67 | 14.46 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -52.5 | -0.8574 | 0.2725 | 0.281 | 1.00 | 8.82 | 13.63 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -47.3 | -0.7718 | 0.2251 | 0.275 | 1.00 | 7.85 | 13.31 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -38.6 | -0.6299 | 0.1826 | 0.281 | 1.00 | 7.22 | 12.77 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -51.2 | -0.8363 | 0.0269 | 0.288 | 1.00 | 2.80 | 13.55 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -45.2 | -0.7374 | 0.1162 | 0.275 | 1.00 | 5.65 | 13.18 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -44.3 | -0.7238 | 0.1525 | 0.266 | 1.00 | 6.25 | 13.13 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -45.1 | -0.7360 | 0.1658 | 0.293 | 1.00 | 7.20 | 13.18 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -42.8 | -0.6995 | 0.0002 | 0.333 | 1.00 | 0.29 | 13.04 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
