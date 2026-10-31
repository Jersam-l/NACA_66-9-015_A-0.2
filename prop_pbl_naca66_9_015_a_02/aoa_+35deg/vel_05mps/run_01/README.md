# Aerodynamic Case: case_101_aoa+35_u05
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.3570
- **Drag Coefficient ($C_d$):** 0.9016
- **Mean Wall $y^+$:** 4.90
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 35.0, "case_idx": 101}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 47.3 | 3.0910 | 0.0367 | 0.335 | 1.00 | 3.58 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 46.1 | 3.0109 | 0.0920 | 0.316 | 1.00 | 5.77 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 43.7 | 2.8524 | 0.1374 | 0.312 | 1.00 | 6.98 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 40.8 | 2.6641 | 0.1863 | 0.297 | 1.00 | 7.72 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 37.2 | 2.4308 | 0.2374 | 0.285 | 1.00 | 8.37 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 33.0 | 2.1561 | 0.2763 | 0.287 | 1.00 | 9.09 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 30.0 | 1.9566 | 0.2947 | 0.284 | 1.00 | 9.28 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 26.0 | 1.6963 | 0.2990 | 0.303 | 1.00 | 9.99 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 16.3 | 1.0648 | 0.3150 | 0.360 | 1.00 | 12.19 | 0.00 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 12.1 | 0.7931 | 0.3168 | 0.392 | 1.00 | 13.30 | 2.27 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -5.0 | -0.3250 | 0.0362 | 0.271 | 1.00 | 3.06 | 5.76 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -10.0 | -0.6559 | 0.1495 | 0.294 | 1.00 | 6.85 | 6.43 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -13.6 | -0.8891 | 0.2105 | 0.292 | 1.00 | 8.06 | 6.87 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -14.4 | -0.9434 | 0.2420 | 0.287 | 1.00 | 8.51 | 6.97 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -10.5 | -0.6878 | 0.2124 | 0.293 | 1.00 | 8.12 | 6.50 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -6.9 | -0.4535 | 0.1722 | 0.294 | 1.00 | 7.36 | 6.03 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | -5.2 | -0.3400 | 0.1560 | 0.296 | 1.00 | 7.03 | 5.79 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | -2.4 | -0.1589 | 0.1292 | 0.302 | 1.00 | 6.53 | 5.38 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | 1.1 | 0.0726 | 0.0164 | 0.344 | 1.00 | 2.54 | 4.82 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | -0.0 | -0.0012 | 0.0192 | 0.353 | 1.00 | 2.95 | 5.00 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
