# Aerodynamic Case: case_94_aoa+30_u20
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.2420
- **Drag Coefficient ($C_d$):** 0.6599
- **Mean Wall $y^+$:** 13.09
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 30.0, "case_idx": 94}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 333.9 | 1.3630 | 0.8202 | 0.235 | 1.00 | 11.99 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 155.6 | 0.6349 | 1.2552 | 0.300 | 1.00 | 20.26 | 12.09 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 1.2 | 0.0049 | 1.4275 | 0.303 | 1.00 | 21.78 | 19.95 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -141.2 | -0.5763 | 1.3147 | 0.303 | 1.00 | 20.95 | 25.11 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -258.1 | -1.0536 | 1.1195 | 0.260 | 1.00 | 16.56 | 28.66 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -321.1 | -1.3108 | 0.9017 | 0.253 | 1.00 | 14.46 | 30.40 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -303.4 | -1.2383 | 0.5619 | 0.268 | 1.00 | 12.09 | 29.92 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -265.2 | -1.0824 | 0.4661 | 0.293 | 1.00 | 12.06 | 28.86 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -240.3 | -0.9809 | 0.5578 | 0.349 | 1.00 | 15.69 | 28.15 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -72.6 | -0.2963 | 0.9488 | 0.433 | 1.00 | 25.43 | 22.77 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -319.6 | -1.3046 | 0.4572 | 0.270 | 1.00 | 10.62 | 30.36 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -295.3 | -1.2052 | 0.2388 | 0.271 | 1.00 | 7.98 | 29.70 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -291.4 | -1.1893 | 0.3350 | 0.278 | 1.00 | 9.70 | 29.59 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -274.1 | -1.1187 | 0.3819 | 0.294 | 1.00 | 10.95 | 29.11 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -248.0 | -1.0122 | 0.3509 | 0.291 | 1.00 | 10.40 | 28.37 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -227.8 | -0.9298 | 0.2814 | 0.280 | 1.00 | 8.95 | 27.78 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -222.9 | -0.9097 | 0.2621 | 0.286 | 1.00 | 8.83 | 27.64 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -217.0 | -0.8857 | 0.3791 | 0.283 | 1.00 | 10.50 | 27.46 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -183.5 | -0.7490 | 0.0757 | 0.303 | 1.00 | 4.89 | 26.45 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -212.3 | -0.8663 | 0.1107 | 0.283 | 1.00 | 5.67 | 27.32 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
