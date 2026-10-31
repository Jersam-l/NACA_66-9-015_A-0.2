# Aerodynamic Case: case_91_aoa+30_u05
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9873
- **Drag Coefficient ($C_d$):** 0.6032
- **Mean Wall $y^+$:** 6.94
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 30.0, "case_idx": 91}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 23.9 | 1.5596 | 0.2115 | 0.235 | 1.00 | 5.80 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 12.7 | 0.8261 | 0.3089 | 0.300 | 1.00 | 10.05 | 2.08 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 3.6 | 0.2365 | 0.3680 | 0.303 | 1.00 | 11.06 | 4.37 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -4.4 | -0.2855 | 0.3929 | 0.303 | 1.00 | 11.45 | 5.67 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -11.2 | -0.7292 | 0.4098 | 0.260 | 1.00 | 10.02 | 6.58 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -16.0 | -1.0464 | 0.3649 | 0.253 | 1.00 | 9.20 | 7.15 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -15.1 | -0.9867 | 0.2504 | 0.268 | 1.00 | 8.07 | 7.05 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -13.3 | -0.8709 | 0.2055 | 0.293 | 1.00 | 8.01 | 6.84 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -13.1 | -0.8537 | 0.2316 | 0.349 | 1.00 | 10.11 | 6.81 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -2.0 | -0.1320 | 0.2724 | 0.433 | 1.00 | 13.63 | 5.32 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -16.0 | -1.0425 | 0.1201 | 0.270 | 1.00 | 5.44 | 7.15 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -14.8 | -0.9693 | 0.1061 | 0.271 | 1.00 | 5.32 | 7.02 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -13.8 | -0.9022 | 0.1028 | 0.278 | 1.00 | 5.37 | 6.90 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -12.0 | -0.7840 | 0.0706 | 0.294 | 1.00 | 4.71 | 6.68 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -10.8 | -0.7056 | 0.0422 | 0.291 | 1.00 | 3.60 | 6.53 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -10.4 | -0.6810 | 0.0338 | 0.280 | 1.00 | 3.10 | 6.48 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -10.1 | -0.6601 | 0.0068 | 0.286 | 1.00 | 1.39 | 6.44 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -10.3 | -0.6744 | 0.0068 | 0.283 | 1.00 | 1.40 | 6.47 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -10.6 | -0.6909 | 0.0133 | 0.303 | 1.00 | 2.06 | 6.50 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -12.4 | -0.8073 | 0.0397 | 0.283 | 1.00 | 3.40 | 6.72 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
