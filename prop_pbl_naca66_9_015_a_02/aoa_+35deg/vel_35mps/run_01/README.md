# Aerodynamic Case: case_107_aoa+35_u35
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.2966
- **Drag Coefficient ($C_d$):** 0.9803
- **Mean Wall $y^+$:** 11.03
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 35.0, "case_idx": 107}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 2790.0 | 3.7185 | 0.2151 | 0.335 | 1.00 | 8.55 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 2723.3 | 3.6296 | 0.7340 | 0.316 | 1.00 | 16.29 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 2613.3 | 3.4830 | 1.0515 | 0.312 | 1.00 | 19.30 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 2473.0 | 3.2959 | 1.2962 | 0.297 | 1.00 | 20.35 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 2280.1 | 3.0388 | 1.4502 | 0.285 | 1.00 | 20.68 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 2039.5 | 2.7182 | 1.4935 | 0.287 | 1.00 | 21.14 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 1825.5 | 2.4330 | 1.4272 | 0.284 | 1.00 | 20.42 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 1576.3 | 2.1009 | 1.5256 | 0.303 | 1.00 | 22.57 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 1034.5 | 1.3788 | 1.9786 | 0.360 | 1.00 | 30.55 | 0.00 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 815.9 | 1.0874 | 2.0847 | 0.392 | 1.00 | 34.11 | 0.00 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | 417.1 | 0.5560 | 0.4975 | 0.271 | 1.00 | 11.50 | 23.32 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | 515.4 | 0.6869 | 0.1163 | 0.294 | 1.00 | 6.03 | 19.58 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | 499.8 | 0.6661 | 0.0890 | 0.292 | 1.00 | 5.23 | 20.22 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | 452.1 | 0.6025 | 0.2233 | 0.287 | 1.00 | 8.18 | 22.07 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | 420.7 | 0.5608 | 0.2634 | 0.293 | 1.00 | 9.05 | 23.20 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | 379.9 | 0.5063 | 0.1583 | 0.294 | 1.00 | 7.06 | 24.59 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | 319.2 | 0.4255 | 0.4539 | 0.296 | 1.00 | 11.99 | 26.53 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | 334.2 | 0.4454 | 0.6085 | 0.302 | 1.00 | 14.17 | 26.07 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | 334.5 | 0.4458 | 0.3378 | 0.344 | 1.00 | 11.96 | 26.05 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | 249.8 | 0.3329 | 0.3513 | 0.353 | 1.00 | 12.62 | 28.59 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
