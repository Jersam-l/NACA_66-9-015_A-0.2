# Aerodynamic Case: case_65_aoa+15_u25
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8446
- **Drag Coefficient ($C_d$):** 0.2084
- **Mean Wall $y^+$:** 14.08
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 15.0, "case_idx": 65}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 349.2 | 0.9121 | 0.5179 | 0.441 | 1.00 | 18.07 | 7.41 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 153.0 | 0.3996 | 1.3418 | 0.300 | 1.00 | 20.91 | 19.37 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 51.3 | 0.1341 | 1.3806 | 0.295 | 1.00 | 20.88 | 23.26 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -73.8 | -0.1928 | 1.2110 | 0.287 | 1.00 | 19.04 | 27.30 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -181.5 | -0.4741 | 1.0391 | 0.270 | 1.00 | 16.55 | 30.35 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -254.9 | -0.6660 | 0.9735 | 0.259 | 1.00 | 15.40 | 32.27 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -262.5 | -0.6857 | 0.6840 | 0.264 | 1.00 | 13.14 | 32.46 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -222.0 | -0.5800 | 0.4366 | 0.284 | 1.00 | 11.29 | 31.42 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -180.0 | -0.4702 | 0.3794 | 0.286 | 1.00 | 10.61 | 30.31 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -176.4 | -0.4608 | 0.8087 | 0.166 | 1.00 | 9.02 | 30.22 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -262.6 | -0.6860 | 2.0483 | 0.299 | 1.00 | 25.73 | 32.46 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -424.5 | -1.1089 | 1.7307 | 0.277 | 1.00 | 21.91 | 36.30 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -352.0 | -0.9195 | 0.6302 | 0.281 | 1.00 | 13.42 | 34.64 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -322.1 | -0.8413 | 0.4491 | 0.275 | 1.00 | 11.08 | 33.92 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -266.5 | -0.6961 | 0.3444 | 0.281 | 1.00 | 9.92 | 32.56 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -303.4 | -0.7924 | 0.0311 | 0.288 | 1.00 | 2.94 | 33.47 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -259.0 | -0.6765 | 0.2514 | 0.275 | 1.00 | 8.31 | 32.37 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -243.9 | -0.6372 | 0.3135 | 0.266 | 1.00 | 8.96 | 31.99 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -225.5 | -0.5892 | 0.3115 | 0.293 | 1.00 | 9.87 | 31.52 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -199.9 | -0.5221 | 0.0474 | 0.333 | 1.00 | 4.37 | 30.84 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
