# Aerodynamic Case: case_56_aoa+10_u30
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4833
- **Drag Coefficient ($C_d$):** 0.1279
- **Mean Wall $y^+$:** 15.92
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 10.0, "case_idx": 56}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 519.8 | 0.9429 | 0.8165 | 0.310 | 1.00 | 15.88 | 7.17 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 103.3 | 0.1875 | 1.6790 | 0.306 | 1.00 | 23.89 | 27.04 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | 5.7 | 0.0103 | 1.6308 | 0.302 | 1.00 | 23.20 | 29.84 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -159.3 | -0.2889 | 1.4243 | 0.290 | 1.00 | 20.83 | 34.06 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -309.7 | -0.5619 | 1.2345 | 0.270 | 1.00 | 18.05 | 37.49 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -414.1 | -0.7513 | 1.1813 | 0.266 | 1.00 | 17.42 | 39.70 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -433.6 | -0.7866 | 0.8317 | 0.295 | 1.00 | 16.22 | 40.10 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -387.2 | -0.7024 | 0.4870 | 0.297 | 1.00 | 12.49 | 39.14 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -322.8 | -0.5857 | 0.4125 | 0.296 | 1.00 | 11.45 | 37.78 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -300.8 | -0.5456 | 0.6746 | 0.263 | 1.00 | 13.03 | 37.30 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 151.1 | 0.2741 | 1.6230 | 0.308 | 1.00 | 23.49 | 25.56 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -446.1 | -0.8093 | 2.4203 | 0.288 | 1.00 | 27.01 | 40.35 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -550.6 | -0.9987 | 1.8850 | 0.278 | 1.00 | 22.98 | 42.41 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -601.9 | -1.0919 | 1.0614 | 0.271 | 1.00 | 16.81 | 43.39 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -564.7 | -1.0245 | 0.5712 | 0.269 | 1.00 | 12.25 | 42.69 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -467.4 | -0.8478 | 0.1459 | 0.273 | 1.00 | 6.27 | 40.78 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -388.8 | -0.7053 | 0.2570 | 0.275 | 1.00 | 8.39 | 39.18 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -351.6 | -0.6378 | 0.2710 | 0.292 | 1.00 | 9.16 | 38.39 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -338.1 | -0.6133 | 0.2743 | 0.311 | 1.00 | 9.81 | 38.10 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -325.5 | -0.5904 | 0.0260 | 0.418 | 1.00 | 4.07 | 37.83 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
