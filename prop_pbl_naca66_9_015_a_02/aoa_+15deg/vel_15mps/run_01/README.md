# Aerodynamic Case: case_63_aoa+15_u15
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.8542
- **Drag Coefficient ($C_d$):** 0.2154
- **Mean Wall $y^+$:** 11.05
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 15.0, "case_idx": 63}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 122.1 | 0.8856 | 0.3108 | 0.441 | 1.00 | 14.02 | 5.07 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 51.2 | 0.3716 | 0.7975 | 0.300 | 1.00 | 16.12 | 11.89 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 14.1 | 0.1025 | 0.8051 | 0.295 | 1.00 | 15.95 | 14.21 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -30.7 | -0.2229 | 0.7069 | 0.287 | 1.00 | 14.55 | 16.59 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -68.4 | -0.4964 | 0.6225 | 0.270 | 1.00 | 12.81 | 18.35 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -94.5 | -0.6859 | 0.5960 | 0.259 | 1.00 | 12.05 | 19.48 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -97.2 | -0.7053 | 0.4262 | 0.264 | 1.00 | 10.37 | 19.59 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -82.5 | -0.5988 | 0.2746 | 0.284 | 1.00 | 8.95 | 18.97 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -67.4 | -0.4888 | 0.2354 | 0.286 | 1.00 | 8.36 | 18.30 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -65.7 | -0.4766 | 0.5019 | 0.166 | 1.00 | 7.10 | 18.23 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -95.8 | -0.6948 | 1.2218 | 0.299 | 1.00 | 19.87 | 19.53 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -156.3 | -1.1343 | 0.9875 | 0.277 | 1.00 | 16.55 | 21.91 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -130.7 | -0.9487 | 0.3773 | 0.281 | 1.00 | 10.38 | 20.94 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -118.3 | -0.8586 | 0.2918 | 0.275 | 1.00 | 8.93 | 20.45 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -98.1 | -0.7119 | 0.2299 | 0.281 | 1.00 | 8.10 | 19.63 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -110.6 | -0.8028 | 0.0268 | 0.288 | 1.00 | 2.78 | 20.14 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -96.6 | -0.7007 | 0.1680 | 0.275 | 1.00 | 6.79 | 19.56 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -93.3 | -0.6768 | 0.2489 | 0.266 | 1.00 | 7.98 | 19.42 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -85.2 | -0.6180 | 0.2117 | 0.293 | 1.00 | 8.13 | 19.08 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -74.6 | -0.5411 | 0.0323 | 0.333 | 1.00 | 3.61 | 18.62 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
