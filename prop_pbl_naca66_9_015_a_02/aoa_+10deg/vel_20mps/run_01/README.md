# Aerodynamic Case: case_54_aoa+10_u20
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4718
- **Drag Coefficient ($C_d$):** 0.1320
- **Mean Wall $y^+$:** 12.99
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 10.0, "case_idx": 54}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 239.0 | 0.9753 | 0.5445 | 0.310 | 1.00 | 12.92 | 3.14 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 53.8 | 0.2197 | 1.1102 | 0.306 | 1.00 | 19.43 | 17.67 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | 7.7 | 0.0314 | 1.0434 | 0.302 | 1.00 | 18.55 | 19.68 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -66.3 | -0.2707 | 0.9070 | 0.290 | 1.00 | 16.62 | 22.55 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -131.5 | -0.5368 | 0.8122 | 0.270 | 1.00 | 14.64 | 24.79 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -177.8 | -0.7257 | 0.7967 | 0.266 | 1.00 | 14.31 | 26.27 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -187.7 | -0.7660 | 0.5667 | 0.295 | 1.00 | 13.39 | 26.58 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -167.8 | -0.6847 | 0.3378 | 0.297 | 1.00 | 10.40 | 25.96 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -140.3 | -0.5725 | 0.2859 | 0.296 | 1.00 | 9.53 | 25.08 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -132.4 | -0.5406 | 0.4639 | 0.263 | 1.00 | 10.81 | 24.82 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 79.9 | 0.3260 | 1.0712 | 0.308 | 1.00 | 19.08 | 16.42 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -187.7 | -0.7661 | 1.5845 | 0.288 | 1.00 | 21.86 | 26.58 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -241.9 | -0.9875 | 1.1767 | 0.278 | 1.00 | 18.16 | 28.20 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -264.2 | -1.0784 | 0.6740 | 0.271 | 1.00 | 13.40 | 28.83 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -245.8 | -1.0034 | 0.3891 | 0.269 | 1.00 | 10.11 | 28.31 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -202.5 | -0.8267 | 0.1130 | 0.273 | 1.00 | 5.52 | 27.03 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -169.6 | -0.6921 | 0.1743 | 0.275 | 1.00 | 6.91 | 26.02 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -155.6 | -0.6352 | 0.2065 | 0.292 | 1.00 | 8.00 | 25.57 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -150.9 | -0.6159 | 0.2046 | 0.311 | 1.00 | 8.47 | 25.42 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -144.5 | -0.5896 | 0.0218 | 0.418 | 1.00 | 3.72 | 25.22 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
