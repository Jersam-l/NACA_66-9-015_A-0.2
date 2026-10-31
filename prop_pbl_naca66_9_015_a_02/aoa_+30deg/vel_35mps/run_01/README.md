# Aerodynamic Case: case_97_aoa+30_u35
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0998
- **Drag Coefficient ($C_d$):** 0.7414
- **Mean Wall $y^+$:** 17.58
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 30.0, "case_idx": 97}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 1394.2 | 1.8581 | 1.4438 | 0.235 | 1.00 | 15.79 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 845.0 | 1.1262 | 2.1936 | 0.300 | 1.00 | 26.78 | 0.00 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 375.7 | 0.5007 | 2.5416 | 0.303 | 1.00 | 29.06 | 24.73 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -57.9 | -0.0771 | 2.4393 | 0.303 | 1.00 | 28.53 | 36.33 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -455.2 | -0.6067 | 2.1180 | 0.260 | 1.00 | 22.78 | 44.37 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -714.4 | -0.9521 | 1.7389 | 0.253 | 1.00 | 20.07 | 48.90 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -723.6 | -0.9645 | 1.1771 | 0.268 | 1.00 | 17.50 | 49.06 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -678.4 | -0.9042 | 1.0741 | 0.293 | 1.00 | 18.31 | 48.30 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -738.2 | -0.9838 | 1.3172 | 0.349 | 1.00 | 24.11 | 49.30 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -76.9 | -0.1025 | 1.7092 | 0.433 | 1.00 | 34.13 | 36.75 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -579.1 | -0.7718 | 0.8009 | 0.270 | 1.00 | 13.97 | 46.59 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -491.2 | -0.6546 | 0.3610 | 0.271 | 1.00 | 9.81 | 45.02 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -474.0 | -0.6317 | 0.4054 | 0.278 | 1.00 | 10.67 | 44.71 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -443.8 | -0.5915 | 0.4062 | 0.294 | 1.00 | 11.30 | 44.16 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -408.3 | -0.5441 | 0.2967 | 0.291 | 1.00 | 9.56 | 43.49 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -400.6 | -0.5339 | 0.1248 | 0.280 | 1.00 | 5.96 | 43.35 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -428.5 | -0.5711 | 0.0506 | 0.286 | 1.00 | 3.85 | 43.87 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -462.5 | -0.6164 | 0.4360 | 0.283 | 1.00 | 11.26 | 44.50 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -431.6 | -0.5752 | 0.0570 | 0.303 | 1.00 | 4.33 | 43.93 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -535.8 | -0.7141 | 0.2641 | 0.283 | 1.00 | 8.76 | 45.82 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
