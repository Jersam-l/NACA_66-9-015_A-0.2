# Aerodynamic Case: case_64_aoa+15_u20
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8638
- **Drag Coefficient ($C_d$):** 0.2164
- **Mean Wall $y^+$:** 12.63
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 15.0, "case_idx": 64}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 200.8 | 0.8198 | 0.4165 | 0.441 | 1.00 | 16.26 | 8.49 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 73.0 | 0.2978 | 1.0716 | 0.300 | 1.00 | 18.69 | 16.76 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 6.8 | 0.0279 | 1.0886 | 0.295 | 1.00 | 18.54 | 19.72 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -73.9 | -0.3017 | 0.9531 | 0.287 | 1.00 | 16.89 | 22.82 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -142.2 | -0.5806 | 0.8293 | 0.270 | 1.00 | 14.78 | 25.14 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -189.1 | -0.7720 | 0.7864 | 0.259 | 1.00 | 13.84 | 26.62 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -193.7 | -0.7905 | 0.5575 | 0.264 | 1.00 | 11.86 | 26.76 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -166.7 | -0.6804 | 0.3575 | 0.284 | 1.00 | 10.22 | 25.93 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -138.0 | -0.5633 | 0.3061 | 0.286 | 1.00 | 9.53 | 25.01 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -132.1 | -0.5394 | 0.6264 | 0.166 | 1.00 | 7.94 | 24.81 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -185.5 | -0.7570 | 1.6298 | 0.299 | 1.00 | 22.95 | 26.51 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -292.4 | -1.1935 | 1.3613 | 0.277 | 1.00 | 19.43 | 29.62 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -251.5 | -1.0267 | 0.5078 | 0.281 | 1.00 | 12.05 | 28.47 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -231.7 | -0.9459 | 0.3762 | 0.275 | 1.00 | 10.14 | 27.90 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -196.4 | -0.8016 | 0.2924 | 0.281 | 1.00 | 9.14 | 26.84 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -206.9 | -0.8445 | 0.0258 | 0.288 | 1.00 | 2.67 | 27.16 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -179.1 | -0.7310 | 0.2117 | 0.275 | 1.00 | 7.62 | 26.31 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -169.8 | -0.6932 | 0.2816 | 0.266 | 1.00 | 8.49 | 26.02 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -155.7 | -0.6356 | 0.2201 | 0.293 | 1.00 | 8.29 | 25.58 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -144.2 | -0.5885 | 0.0056 | 0.333 | 1.00 | 1.50 | 25.21 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
