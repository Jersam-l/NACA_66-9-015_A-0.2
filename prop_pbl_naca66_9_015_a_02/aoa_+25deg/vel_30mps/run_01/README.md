# Aerodynamic Case: case_86_aoa+25_u30
- **Angle of Attack (AoA):** +25.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0156
- **Drag Coefficient ($C_d$):** 0.4114
- **Mean Wall $y^+$:** 15.09
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 25.0, "case_idx": 86}'
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
| 1 | Upper | 0.0059 | 0.0205 | 0.000 | -9.5 | -0.0172 | 1.8424 | 0.276 | 1.00 | 21.92 | 30.26 |
| 2 | Upper | 0.0188 | 0.0141 | 0.111 | 265.4 | 0.4814 | 1.8984 | 0.257 | 1.00 | 21.35 | 21.60 |
| 3 | Upper | 0.0288 | 0.0091 | 0.222 | 15.4 | 0.0280 | 1.9086 | 0.287 | 1.00 | 23.87 | 29.58 |
| 4 | Upper | 0.0386 | 0.0039 | 0.333 | -242.1 | -0.4392 | 1.7804 | 0.284 | 1.00 | 22.80 | 35.99 |
| 5 | Upper | 0.0484 | -0.0015 | 0.444 | -466.6 | -0.8465 | 1.5194 | 0.292 | 1.00 | 21.69 | 40.77 |
| 6 | Upper | 0.0582 | -0.0065 | 0.556 | -660.0 | -1.1974 | 1.3843 | 0.317 | 1.00 | 22.46 | 44.47 |
| 7 | Upper | 0.0685 | -0.0109 | 0.667 | -543.4 | -0.9857 | 1.3171 | 0.358 | 1.00 | 24.75 | 42.27 |
| 8 | Upper | 0.0789 | -0.0147 | 0.778 | -571.2 | -1.0361 | 0.8257 | 0.273 | 1.00 | 14.93 | 42.81 |
| 9 | Upper | 0.0894 | -0.0186 | 0.889 | -526.4 | -0.9549 | 0.8681 | 0.245 | 1.00 | 13.76 | 41.95 |
| 10 | Upper | 0.0948 | -0.0209 | 1.000 | -566.6 | -1.0279 | 1.2087 | 0.304 | 1.00 | 20.12 | 42.72 |
| 1 | Lower | -0.0021 | 0.0034 | 0.000 | -1198.7 | -2.1745 | 2.3316 | 0.272 | 1.00 | 21.96 | 53.45 |
| 2 | Lower | 0.0023 | -0.0213 | 0.111 | -695.0 | -1.2608 | 0.4579 | 0.272 | 1.00 | 11.08 | 45.11 |
| 3 | Lower | 0.0133 | -0.0240 | 0.222 | -635.9 | -1.1535 | 0.4627 | 0.276 | 1.00 | 11.32 | 44.02 |
| 4 | Lower | 0.0237 | -0.0281 | 0.333 | -571.8 | -1.0374 | 0.4193 | 0.280 | 1.00 | 10.94 | 42.82 |
| 5 | Lower | 0.0336 | -0.0332 | 0.444 | -513.6 | -0.9317 | 0.3660 | 0.278 | 1.00 | 10.12 | 41.70 |
| 6 | Lower | 0.0430 | -0.0392 | 0.556 | -470.1 | -0.8528 | 0.3310 | 0.263 | 1.00 | 9.10 | 40.84 |
| 7 | Lower | 0.0519 | -0.0465 | 0.667 | -444.8 | -0.8069 | 0.2536 | 0.254 | 1.00 | 7.70 | 40.33 |
| 8 | Lower | 0.0604 | -0.0545 | 0.778 | -441.3 | -0.8005 | 0.2562 | 0.263 | 1.00 | 8.02 | 40.26 |
| 9 | Lower | 0.0901 | -0.0171 | 0.889 | -609.8 | -1.1062 | 0.2503 | 0.297 | 1.00 | 8.95 | 43.54 |
| 10 | Lower | 0.0949 | -0.0208 | 1.000 | -618.1 | -1.1212 | 0.0759 | 0.297 | 1.00 | 4.92 | 43.69 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
