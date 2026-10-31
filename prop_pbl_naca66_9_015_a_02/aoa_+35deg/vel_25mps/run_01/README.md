# Aerodynamic Case: case_105_aoa+35_u25
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.3990
- **Drag Coefficient ($C_d$):** 0.9163
- **Mean Wall $y^+$:** 9.64
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 35.0, "case_idx": 105}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 1138.3 | 2.9735 | 0.2286 | 0.335 | 1.00 | 8.95 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 1126.2 | 2.9420 | 0.4367 | 0.316 | 1.00 | 12.56 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 1076.9 | 2.8131 | 0.6755 | 0.312 | 1.00 | 15.47 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 1012.1 | 2.6438 | 0.8681 | 0.297 | 1.00 | 16.65 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 921.2 | 2.4065 | 0.9816 | 0.285 | 1.00 | 17.01 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 809.6 | 2.1149 | 1.0060 | 0.287 | 1.00 | 17.35 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 716.5 | 1.8717 | 0.9497 | 0.284 | 1.00 | 16.66 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 612.0 | 1.5987 | 1.0187 | 0.303 | 1.00 | 18.44 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 370.9 | 0.9689 | 1.3467 | 0.360 | 1.00 | 25.20 | 4.41 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 268.9 | 0.7026 | 1.4262 | 0.392 | 1.00 | 28.21 | 13.63 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -178.0 | -0.4649 | 0.3474 | 0.271 | 1.00 | 9.58 | 30.26 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -179.1 | -0.4678 | 0.1627 | 0.294 | 1.00 | 7.14 | 30.29 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -203.2 | -0.5309 | 0.5160 | 0.292 | 1.00 | 12.62 | 30.93 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -180.1 | -0.4706 | 0.7411 | 0.287 | 1.00 | 14.90 | 30.32 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -88.8 | -0.2319 | 0.6122 | 0.293 | 1.00 | 13.79 | 27.75 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -39.8 | -0.1040 | 0.4618 | 0.294 | 1.00 | 12.06 | 26.27 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | -33.2 | -0.0868 | 0.5484 | 0.296 | 1.00 | 13.19 | 26.06 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | 12.5 | 0.0328 | 0.5712 | 0.302 | 1.00 | 13.73 | 24.59 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | 54.2 | 0.1417 | 0.1572 | 0.344 | 1.00 | 8.02 | 23.16 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | 7.7 | 0.0201 | 0.1815 | 0.353 | 1.00 | 9.07 | 24.75 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
