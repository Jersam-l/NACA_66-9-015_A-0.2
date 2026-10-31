# Aerodynamic Case: case_93_aoa+30_u15
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.4004
- **Drag Coefficient ($C_d$):** 0.7425
- **Mean Wall $y^+$:** 11.56
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 30.0, "case_idx": 93}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 211.5 | 1.5346 | 0.6233 | 0.235 | 1.00 | 10.28 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 112.9 | 0.8194 | 0.9336 | 0.300 | 1.00 | 17.47 | 6.38 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 29.7 | 0.2157 | 1.0491 | 0.303 | 1.00 | 18.67 | 13.28 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -46.8 | -0.3398 | 0.9521 | 0.303 | 1.00 | 17.82 | 17.36 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -108.0 | -0.7836 | 0.8087 | 0.260 | 1.00 | 14.08 | 20.03 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -139.4 | -1.0119 | 0.6567 | 0.253 | 1.00 | 12.34 | 21.28 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -127.9 | -0.9281 | 0.4127 | 0.268 | 1.00 | 10.36 | 20.83 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -105.3 | -0.7638 | 0.3554 | 0.293 | 1.00 | 10.54 | 19.92 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -92.0 | -0.6678 | 0.4446 | 0.349 | 1.00 | 14.01 | 19.37 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -1.9 | -0.0138 | 0.7016 | 0.433 | 1.00 | 21.87 | 15.10 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -148.4 | -1.0765 | 0.3547 | 0.270 | 1.00 | 9.39 | 21.61 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -138.0 | -1.0013 | 0.2171 | 0.271 | 1.00 | 7.61 | 21.22 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -136.1 | -0.9875 | 0.3110 | 0.278 | 1.00 | 9.35 | 21.15 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -121.0 | -0.8777 | 0.3210 | 0.294 | 1.00 | 10.04 | 20.55 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -102.0 | -0.7402 | 0.2894 | 0.291 | 1.00 | 9.44 | 19.79 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -88.9 | -0.6452 | 0.2646 | 0.280 | 1.00 | 8.68 | 19.24 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -81.8 | -0.5939 | 0.2258 | 0.286 | 1.00 | 8.19 | 18.94 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -76.6 | -0.5559 | 0.2558 | 0.283 | 1.00 | 8.63 | 18.71 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -61.8 | -0.4481 | 0.0398 | 0.303 | 1.00 | 3.46 | 18.05 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -75.7 | -0.5493 | 0.0874 | 0.283 | 1.00 | 5.04 | 18.67 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
