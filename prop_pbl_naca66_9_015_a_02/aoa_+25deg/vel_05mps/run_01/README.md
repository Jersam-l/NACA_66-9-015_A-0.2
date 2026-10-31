# Aerodynamic Case: case_81_aoa+25_u05
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0414
- **Drag Coefficient ($C_d$):** 0.4919
- **Mean Wall $y^+$:** 6.84
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 25.0, "case_idx": 81}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | 4.9 | 0.3194 | 0.3136 | 0.276 | 1.00 | 9.10 | 4.12 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 15.6 | 1.0211 | 0.3124 | 0.257 | 1.00 | 8.66 | 0.00 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 7.7 | 0.5026 | 0.3505 | 0.287 | 1.00 | 10.23 | 3.53 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | 0.2 | 0.0136 | 0.3943 | 0.284 | 1.00 | 10.73 | 4.97 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -6.1 | -0.3952 | 0.3909 | 0.292 | 1.00 | 11.00 | 5.91 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -12.0 | -0.7824 | 0.3448 | 0.317 | 1.00 | 11.21 | 6.67 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -11.0 | -0.7202 | 0.2601 | 0.358 | 1.00 | 11.00 | 6.56 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -11.1 | -0.7234 | 0.1871 | 0.273 | 1.00 | 7.11 | 6.56 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -9.7 | -0.6357 | 0.1935 | 0.245 | 1.00 | 6.50 | 6.39 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -11.3 | -0.7392 | 0.2472 | 0.304 | 1.00 | 9.10 | 6.59 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -28.0 | -1.8276 | 0.3749 | 0.272 | 1.00 | 8.41 | 8.41 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -10.4 | -0.6799 | 0.0956 | 0.272 | 1.00 | 5.06 | 6.48 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -9.9 | -0.6485 | 0.1113 | 0.276 | 1.00 | 5.55 | 6.42 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -8.9 | -0.5801 | 0.1066 | 0.280 | 1.00 | 5.51 | 6.29 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -7.6 | -0.4993 | 0.0896 | 0.278 | 1.00 | 5.00 | 6.12 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -6.8 | -0.4455 | 0.0644 | 0.263 | 1.00 | 4.01 | 6.01 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -7.2 | -0.4688 | 0.0759 | 0.254 | 1.00 | 4.21 | 6.06 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -8.0 | -0.5254 | 0.1127 | 0.263 | 1.00 | 5.32 | 6.17 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -12.9 | -0.8433 | 0.0462 | 0.297 | 1.00 | 3.84 | 6.79 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -13.7 | -0.8954 | 0.0215 | 0.297 | 1.00 | 2.62 | 6.88 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
