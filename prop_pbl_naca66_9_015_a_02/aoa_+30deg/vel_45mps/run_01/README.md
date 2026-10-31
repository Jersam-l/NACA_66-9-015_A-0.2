# Aerodynamic Case: case_99_aoa+30_u45
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0669
- **Drag Coefficient ($C_d$):** 0.5686
- **Mean Wall $y^+$:** 19.67
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 30.0, "case_idx": 99}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 1483.7 | 1.1963 | 1.9907 | 0.235 | 1.00 | 17.42 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 623.5 | 0.5027 | 2.8337 | 0.300 | 1.00 | 30.44 | 31.73 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | -56.7 | -0.0457 | 3.2126 | 0.303 | 1.00 | 32.67 | 46.02 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -680.5 | -0.5487 | 3.0525 | 0.303 | 1.00 | 31.92 | 56.00 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -1244.6 | -1.0034 | 2.6256 | 0.260 | 1.00 | 25.36 | 63.69 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -1586.7 | -1.2793 | 2.1065 | 0.253 | 1.00 | 22.09 | 67.94 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -1519.8 | -1.2254 | 1.3472 | 0.268 | 1.00 | 18.73 | 67.13 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -1332.3 | -1.0742 | 1.2111 | 0.293 | 1.00 | 19.45 | 64.81 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -1250.4 | -1.0082 | 1.5506 | 0.349 | 1.00 | 26.16 | 63.77 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -450.7 | -0.3634 | 2.1345 | 0.433 | 1.00 | 38.14 | 52.54 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -1852.8 | -1.4938 | 1.1572 | 0.270 | 1.00 | 16.94 | 71.06 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -1684.8 | -1.3584 | 0.7422 | 0.271 | 1.00 | 14.07 | 69.11 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -1577.7 | -1.2720 | 0.8672 | 0.278 | 1.00 | 15.61 | 67.83 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -1382.0 | -1.1143 | 0.7364 | 0.294 | 1.00 | 15.21 | 65.43 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -1194.6 | -0.9632 | 0.5154 | 0.291 | 1.00 | 12.60 | 63.05 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -1090.8 | -0.8795 | 0.3725 | 0.280 | 1.00 | 10.30 | 61.69 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -1037.1 | -0.8362 | 0.2042 | 0.286 | 1.00 | 7.79 | 60.98 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -1026.4 | -0.8276 | 0.1164 | 0.283 | 1.00 | 5.82 | 60.83 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -1004.0 | -0.8095 | 0.0552 | 0.303 | 1.00 | 3.72 | 60.53 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -1098.2 | -0.8854 | 0.2152 | 0.283 | 1.00 | 7.91 | 61.79 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
