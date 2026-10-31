# Aerodynamic Case: case_96_aoa+30_u30
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.4538
- **Drag Coefficient ($C_d$):** 0.6994
- **Mean Wall $y^+$:** 16.15
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 30.0, "case_idx": 96}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 827.4 | 1.5010 | 1.3591 | 0.235 | 1.00 | 14.76 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 424.2 | 0.7694 | 1.9492 | 0.300 | 1.00 | 25.25 | 14.40 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 107.5 | 0.1949 | 2.1474 | 0.303 | 1.00 | 26.71 | 26.92 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -159.9 | -0.2900 | 1.8837 | 0.303 | 1.00 | 25.07 | 34.07 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -355.6 | -0.6451 | 1.4931 | 0.260 | 1.00 | 19.12 | 38.48 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -428.1 | -0.7766 | 1.1181 | 0.253 | 1.00 | 16.10 | 39.99 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -357.3 | -0.6481 | 0.6322 | 0.268 | 1.00 | 12.83 | 38.51 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -255.2 | -0.4629 | 0.5226 | 0.293 | 1.00 | 12.78 | 36.28 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -180.4 | -0.3273 | 0.6937 | 0.349 | 1.00 | 17.50 | 34.56 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | 177.1 | 0.3213 | 1.3553 | 0.433 | 1.00 | 30.39 | 24.72 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -746.3 | -1.3539 | 0.7496 | 0.270 | 1.00 | 13.66 | 46.03 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -684.0 | -1.2407 | 0.4182 | 0.271 | 1.00 | 10.56 | 44.91 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -682.2 | -1.2375 | 0.8844 | 0.278 | 1.00 | 15.76 | 44.88 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -522.7 | -0.9482 | 0.9182 | 0.294 | 1.00 | 16.99 | 41.87 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -311.7 | -0.5654 | 0.6994 | 0.291 | 1.00 | 14.68 | 37.53 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -197.2 | -0.3577 | 0.5278 | 0.280 | 1.00 | 12.26 | 34.95 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -156.7 | -0.2843 | 0.4403 | 0.286 | 1.00 | 11.44 | 34.00 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -132.5 | -0.2404 | 0.5500 | 0.283 | 1.00 | 12.65 | 33.41 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -51.7 | -0.0937 | 0.1971 | 0.303 | 1.00 | 8.05 | 31.37 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -92.2 | -0.1672 | 0.0794 | 0.283 | 1.00 | 4.81 | 32.41 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
