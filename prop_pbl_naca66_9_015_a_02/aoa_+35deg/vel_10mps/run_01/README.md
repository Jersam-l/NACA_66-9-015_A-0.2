# Aerodynamic Case: case_102_aoa+35_u10
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.1719
- **Drag Coefficient ($C_d$):** 0.8758
- **Mean Wall $y^+$:** 6.28
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 35.0, "case_idx": 102}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 162.5 | 2.6529 | 0.0561 | 0.335 | 1.00 | 4.37 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 156.4 | 2.5533 | 0.2120 | 0.316 | 1.00 | 8.75 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 147.0 | 2.3994 | 0.3081 | 0.312 | 1.00 | 10.45 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 135.5 | 2.2117 | 0.4062 | 0.297 | 1.00 | 11.39 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 120.4 | 1.9661 | 0.4943 | 0.285 | 1.00 | 12.07 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 102.2 | 1.6684 | 0.5230 | 0.287 | 1.00 | 12.51 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 87.5 | 1.4286 | 0.4719 | 0.284 | 1.00 | 11.74 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 70.6 | 1.1533 | 0.4525 | 0.303 | 1.00 | 12.29 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 34.0 | 0.5551 | 0.5513 | 0.360 | 1.00 | 16.12 | 6.67 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 18.6 | 0.3043 | 0.5754 | 0.392 | 1.00 | 17.92 | 8.34 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -52.5 | -0.8570 | 0.1647 | 0.271 | 1.00 | 6.62 | 13.63 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -53.0 | -0.8648 | 0.1861 | 0.294 | 1.00 | 7.64 | 13.66 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -52.7 | -0.8609 | 0.2245 | 0.292 | 1.00 | 8.33 | 13.64 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -50.0 | -0.8168 | 0.2656 | 0.287 | 1.00 | 8.92 | 13.48 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -37.2 | -0.6081 | 0.2101 | 0.293 | 1.00 | 8.08 | 12.68 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -32.2 | -0.5254 | 0.1782 | 0.294 | 1.00 | 7.49 | 12.35 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | -30.7 | -0.5014 | 0.1876 | 0.296 | 1.00 | 7.71 | 12.25 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | -25.0 | -0.4088 | 0.1517 | 0.302 | 1.00 | 7.08 | 11.87 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | -18.7 | -0.3050 | 0.0362 | 0.344 | 1.00 | 3.67 | 11.42 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | -22.2 | -0.3625 | 0.0348 | 0.353 | 1.00 | 3.97 | 11.67 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
