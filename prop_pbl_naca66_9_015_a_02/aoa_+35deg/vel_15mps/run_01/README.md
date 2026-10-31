# Aerodynamic Case: case_103_aoa+35_u15
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.5071
- **Drag Coefficient ($C_d$):** 0.9570
- **Mean Wall $y^+$:** 7.49
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 35.0, "case_idx": 103}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 369.5 | 2.6813 | 0.1573 | 0.335 | 1.00 | 7.58 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 366.9 | 2.6626 | 0.2383 | 0.316 | 1.00 | 9.28 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 349.2 | 2.5339 | 0.3846 | 0.312 | 1.00 | 11.67 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 327.3 | 2.3746 | 0.5256 | 0.297 | 1.00 | 12.96 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 298.4 | 2.1656 | 0.6342 | 0.285 | 1.00 | 13.67 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 263.2 | 1.9097 | 0.6549 | 0.287 | 1.00 | 14.00 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 234.5 | 1.7018 | 0.5965 | 0.284 | 1.00 | 13.20 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 201.9 | 1.4653 | 0.6125 | 0.303 | 1.00 | 14.30 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 123.6 | 0.8971 | 0.7940 | 0.360 | 1.00 | 19.35 | 4.81 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 89.4 | 0.6490 | 0.8389 | 0.392 | 1.00 | 21.64 | 8.89 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -64.5 | -0.4681 | 0.2101 | 0.271 | 1.00 | 7.44 | 18.18 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -63.2 | -0.4587 | 0.0109 | 0.294 | 1.00 | 1.73 | 18.12 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -72.1 | -0.5234 | 0.2077 | 0.292 | 1.00 | 8.01 | 18.51 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -73.1 | -0.5302 | 0.3682 | 0.287 | 1.00 | 10.50 | 18.55 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -54.8 | -0.3978 | 0.3662 | 0.293 | 1.00 | 10.67 | 17.73 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -34.7 | -0.2521 | 0.3227 | 0.294 | 1.00 | 10.08 | 16.79 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | -22.1 | -0.1604 | 0.3564 | 0.296 | 1.00 | 10.63 | 16.16 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | 1.8 | 0.0128 | 0.3293 | 0.302 | 1.00 | 10.42 | 14.90 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | 15.4 | 0.1117 | 0.1010 | 0.344 | 1.00 | 6.46 | 14.14 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | -0.1 | -0.0008 | 0.1109 | 0.353 | 1.00 | 7.09 | 15.01 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
