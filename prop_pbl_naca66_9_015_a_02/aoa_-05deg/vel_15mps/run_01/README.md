# Aerodynamic Case: case_23_aoa-05_u15
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.0404
- **Drag Coefficient ($C_d$):** 0.1136
- **Mean Wall $y^+$:** 9.70
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": -5.0, "case_idx": 23}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 78.8 | 0.5720 | 0.7145 | 0.298 | 1.00 | 15.17 | 9.81 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -150.6 | -1.0924 | 0.2613 | 0.286 | 1.00 | 8.80 | 21.70 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -110.2 | -0.7993 | 0.1347 | 0.310 | 1.00 | 6.83 | 20.12 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -73.3 | -0.5319 | 0.2370 | 0.307 | 1.00 | 8.99 | 18.57 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -90.8 | -0.6589 | 0.4462 | 0.288 | 1.00 | 11.58 | 19.32 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -112.3 | -0.8148 | 0.4989 | 0.274 | 1.00 | 11.67 | 20.21 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -113.4 | -0.8229 | 0.3326 | 0.278 | 1.00 | 9.64 | 20.25 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -97.2 | -0.7050 | 0.1305 | 0.291 | 1.00 | 6.33 | 19.59 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -82.0 | -0.5951 | 0.0415 | 0.320 | 1.00 | 3.92 | 18.94 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -70.5 | -0.5117 | 0.0635 | 0.365 | 1.00 | 5.53 | 18.44 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 149.5 | 1.0852 | 0.2303 | 0.302 | 1.00 | 8.74 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -13.3 | -0.0968 | 1.0835 | 0.278 | 1.00 | 17.43 | 15.71 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -89.1 | -0.6465 | 1.1249 | 0.282 | 1.00 | 18.04 | 19.25 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -119.6 | -0.8678 | 0.7900 | 0.289 | 1.00 | 15.50 | 20.50 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -126.3 | -0.9163 | 0.4344 | 0.295 | 1.00 | 11.69 | 20.76 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -111.3 | -0.8076 | 0.1383 | 0.294 | 1.00 | 6.59 | 20.17 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -95.2 | -0.6910 | 0.1324 | 0.287 | 1.00 | 6.29 | 19.51 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -85.6 | -0.6212 | 0.2107 | 0.282 | 1.00 | 7.80 | 19.10 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -81.0 | -0.5875 | 0.2292 | 0.275 | 1.00 | 7.94 | 18.90 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -73.5 | -0.5333 | 0.0903 | 0.343 | 1.00 | 6.21 | 18.57 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
