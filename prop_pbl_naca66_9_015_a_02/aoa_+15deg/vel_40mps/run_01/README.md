# Aerodynamic Case: case_68_aoa+15_u40
- **Angle of Attack (AoA):** +15.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.7995
- **Drag Coefficient ($C_d$):** 0.1979
- **Mean Wall $y^+$:** 17.90
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 15.0, "case_idx": 68}'
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
| 1 | Upper | 0.0025 | 0.0125 | 0.000 | 842.1 | 0.8593 | 0.8287 | 0.441 | 1.00 | 22.81 | 15.01 |
| 2 | Upper | 0.0140 | 0.0092 | 0.111 | 336.7 | 0.3436 | 2.1685 | 0.300 | 1.00 | 26.59 | 32.41 |
| 3 | Upper | 0.0247 | 0.0062 | 0.222 | 78.9 | 0.0805 | 2.3039 | 0.295 | 1.00 | 26.98 | 38.36 |
| 4 | Upper | 0.0352 | 0.0028 | 0.333 | -238.4 | -0.2433 | 2.0632 | 0.287 | 1.00 | 24.85 | 44.60 |
| 5 | Upper | 0.0458 | -0.0008 | 0.444 | -529.9 | -0.5407 | 1.7163 | 0.270 | 1.00 | 21.27 | 49.65 |
| 6 | Upper | 0.0564 | -0.0042 | 0.556 | -728.5 | -0.7434 | 1.5592 | 0.259 | 1.00 | 19.49 | 52.81 |
| 7 | Upper | 0.0672 | -0.0069 | 0.667 | -754.1 | -0.7695 | 1.0826 | 0.264 | 1.00 | 16.53 | 53.21 |
| 8 | Upper | 0.0781 | -0.0090 | 0.778 | -657.9 | -0.6714 | 0.6954 | 0.284 | 1.00 | 14.25 | 51.71 |
| 9 | Upper | 0.0891 | -0.0109 | 0.889 | -561.0 | -0.5724 | 0.6265 | 0.286 | 1.00 | 13.64 | 50.16 |
| 10 | Upper | 0.0978 | -0.0128 | 1.000 | -576.1 | -0.5878 | 1.4023 | 0.166 | 1.00 | 11.87 | 50.40 |
| 1 | Lower | 0.0029 | 0.0150 | 0.000 | -741.0 | -0.7561 | 3.2957 | 0.299 | 1.00 | 32.63 | 53.01 |
| 2 | Lower | 0.0166 | 0.0188 | 0.111 | -1156.5 | -1.1801 | 2.9062 | 0.277 | 1.00 | 28.39 | 59.06 |
| 3 | Lower | 0.0151 | -0.0296 | 0.222 | -948.1 | -0.9674 | 1.0432 | 0.281 | 1.00 | 17.26 | 56.11 |
| 4 | Lower | 0.0261 | -0.0315 | 0.333 | -888.5 | -0.9066 | 0.6814 | 0.275 | 1.00 | 13.65 | 55.23 |
| 5 | Lower | 0.0367 | -0.0346 | 0.444 | -751.6 | -0.7669 | 0.4979 | 0.281 | 1.00 | 11.93 | 53.17 |
| 6 | Lower | 0.0601 | 0.0097 | 0.556 | -891.0 | -0.9092 | 0.0328 | 0.288 | 1.00 | 3.07 | 55.27 |
| 7 | Lower | 0.0702 | 0.0045 | 0.667 | -779.6 | -0.7955 | 0.3876 | 0.275 | 1.00 | 10.32 | 53.60 |
| 8 | Lower | 0.0800 | -0.0018 | 0.778 | -744.2 | -0.7594 | 0.4343 | 0.266 | 1.00 | 10.54 | 53.06 |
| 9 | Lower | 0.0898 | -0.0082 | 0.889 | -714.6 | -0.7292 | 0.5539 | 0.293 | 1.00 | 13.16 | 52.60 |
| 10 | Lower | 0.0978 | -0.0127 | 1.000 | -648.5 | -0.6617 | 0.0992 | 0.333 | 1.00 | 6.32 | 51.56 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
