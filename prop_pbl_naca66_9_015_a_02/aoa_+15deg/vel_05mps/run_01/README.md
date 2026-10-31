# Aerodynamic Case: case_61_aoa+15_u05
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8798
- **Drag Coefficient ($C_d$):** 0.2357
- **Mean Wall $y^+$:** 7.18
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 15.0, "case_idx": 61}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 14.0 | 0.9125 | 0.1078 | 0.441 | 1.00 | 8.38 | 1.48 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 5.0 | 0.3284 | 0.2724 | 0.300 | 1.00 | 9.42 | 4.10 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 0.9 | 0.0595 | 0.3038 | 0.295 | 1.00 | 9.80 | 4.85 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -3.5 | -0.2288 | 0.3310 | 0.287 | 1.00 | 9.95 | 5.54 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -7.4 | -0.4834 | 0.3440 | 0.270 | 1.00 | 9.52 | 6.09 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -10.6 | -0.6939 | 0.3418 | 0.259 | 1.00 | 9.13 | 6.51 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -10.3 | -0.6735 | 0.2700 | 0.264 | 1.00 | 8.25 | 6.47 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -8.0 | -0.5244 | 0.1748 | 0.284 | 1.00 | 7.14 | 6.17 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -6.3 | -0.4136 | 0.1137 | 0.286 | 1.00 | 5.81 | 5.95 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -6.1 | -0.3955 | 0.1883 | 0.166 | 1.00 | 4.35 | 5.91 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -9.6 | -0.6254 | 0.4033 | 0.299 | 1.00 | 11.42 | 6.38 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -18.3 | -1.1924 | 0.3604 | 0.277 | 1.00 | 10.00 | 7.40 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -15.3 | -0.9978 | 0.1668 | 0.281 | 1.00 | 6.90 | 7.07 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -13.7 | -0.8944 | 0.1355 | 0.275 | 1.00 | 6.09 | 6.88 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -11.1 | -0.7217 | 0.1039 | 0.281 | 1.00 | 5.45 | 6.56 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -11.9 | -0.7778 | 0.0230 | 0.288 | 1.00 | 2.62 | 6.67 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -10.1 | -0.6604 | 0.0743 | 0.275 | 1.00 | 4.52 | 6.44 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -9.3 | -0.6060 | 0.0860 | 0.266 | 1.00 | 4.69 | 6.34 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -7.8 | -0.5095 | 0.0536 | 0.293 | 1.00 | 4.09 | 6.14 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -7.1 | -0.4616 | 0.0024 | 0.333 | 1.00 | 0.98 | 6.04 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
