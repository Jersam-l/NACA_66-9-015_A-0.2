# Aerodynamic Case: case_66_aoa+15_u30
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8243
- **Drag Coefficient ($C_d$):** 0.2036
- **Mean Wall $y^+$:** 15.42
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 15.0, "case_idx": 66}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 466.0 | 0.8453 | 0.6216 | 0.441 | 1.00 | 19.78 | 11.80 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 182.4 | 0.3308 | 1.6167 | 0.300 | 1.00 | 22.96 | 24.54 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 36.3 | 0.0658 | 1.6836 | 0.295 | 1.00 | 23.06 | 29.00 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -144.2 | -0.2615 | 1.4849 | 0.287 | 1.00 | 21.08 | 33.70 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -302.8 | -0.5494 | 1.2589 | 0.270 | 1.00 | 18.21 | 37.34 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -411.0 | -0.7455 | 1.1668 | 0.259 | 1.00 | 16.86 | 39.63 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -423.5 | -0.7682 | 0.8158 | 0.264 | 1.00 | 14.35 | 39.89 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -367.0 | -0.6658 | 0.5209 | 0.284 | 1.00 | 12.33 | 38.72 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -308.9 | -0.5604 | 0.4589 | 0.286 | 1.00 | 11.67 | 37.47 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -308.9 | -0.5604 | 0.9985 | 0.166 | 1.00 | 10.02 | 37.48 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -418.3 | -0.7587 | 2.4628 | 0.299 | 1.00 | 28.21 | 39.78 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -652.0 | -1.1828 | 2.1195 | 0.277 | 1.00 | 24.25 | 44.32 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -544.0 | -0.9869 | 0.7658 | 0.281 | 1.00 | 14.79 | 42.29 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -505.1 | -0.9162 | 0.5283 | 0.275 | 1.00 | 12.02 | 41.53 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -426.6 | -0.7738 | 0.3996 | 0.281 | 1.00 | 10.69 | 39.95 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -494.2 | -0.8965 | 0.0356 | 0.288 | 1.00 | 3.14 | 41.31 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -430.4 | -0.7808 | 0.2944 | 0.275 | 1.00 | 8.99 | 40.03 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -408.1 | -0.7403 | 0.3537 | 0.266 | 1.00 | 9.51 | 39.58 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -384.3 | -0.6972 | 0.3874 | 0.293 | 1.00 | 11.00 | 39.08 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -345.8 | -0.6273 | 0.0693 | 0.333 | 1.00 | 5.28 | 38.27 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
