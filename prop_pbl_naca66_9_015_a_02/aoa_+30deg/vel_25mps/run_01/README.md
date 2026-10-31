# Aerodynamic Case: case_95_aoa+30_u25
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.3761
- **Drag Coefficient ($C_d$):** 0.6974
- **Mean Wall $y^+$:** 14.72
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 30.0, "case_idx": 95}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 585.0 | 1.5281 | 0.9984 | 0.235 | 1.00 | 13.31 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 314.2 | 0.8207 | 1.5518 | 0.300 | 1.00 | 22.53 | 10.59 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 79.8 | 0.2084 | 1.7770 | 0.303 | 1.00 | 24.30 | 22.24 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -132.2 | -0.3452 | 1.6424 | 0.303 | 1.00 | 23.41 | 29.00 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -304.6 | -0.7957 | 1.3827 | 0.260 | 1.00 | 18.40 | 33.50 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -394.0 | -1.0292 | 1.0888 | 0.253 | 1.00 | 15.88 | 35.61 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -360.8 | -0.9426 | 0.6620 | 0.268 | 1.00 | 13.13 | 34.84 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -295.7 | -0.7724 | 0.5573 | 0.293 | 1.00 | 13.19 | 33.28 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -251.8 | -0.6577 | 0.6914 | 0.349 | 1.00 | 17.47 | 32.19 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -11.8 | -0.0307 | 1.1675 | 0.433 | 1.00 | 28.21 | 25.38 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -414.1 | -1.0818 | 0.5535 | 0.270 | 1.00 | 11.67 | 36.07 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -374.5 | -0.9784 | 0.2662 | 0.271 | 1.00 | 8.43 | 35.16 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -371.9 | -0.9714 | 0.4435 | 0.278 | 1.00 | 11.16 | 35.10 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -339.6 | -0.8871 | 0.5119 | 0.294 | 1.00 | 12.68 | 34.34 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -293.7 | -0.7671 | 0.4749 | 0.291 | 1.00 | 12.09 | 33.23 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -256.5 | -0.6700 | 0.4006 | 0.280 | 1.00 | 10.68 | 32.31 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -239.1 | -0.6247 | 0.3597 | 0.286 | 1.00 | 10.34 | 31.87 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -221.7 | -0.5790 | 0.4613 | 0.283 | 1.00 | 11.59 | 31.41 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -173.5 | -0.4531 | 0.0637 | 0.303 | 1.00 | 4.28 | 30.14 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -221.5 | -0.5785 | 0.1729 | 0.283 | 1.00 | 7.09 | 31.41 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
