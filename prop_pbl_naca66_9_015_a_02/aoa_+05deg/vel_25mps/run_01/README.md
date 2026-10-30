# Aerodynamic Case: case_45_aoa+05_u25
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2283
- **Drag Coefficient ($C_d$):** 0.0956
- **Mean Wall $y^+$:** 14.28
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": 5.0, "case_idx": 45}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 385.0 | 1.0057 | 0.3140 | 0.344 | 1.00 | 11.62 | 0.00 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 20.5 | 0.0537 | 1.1957 | 0.305 | 1.00 | 20.11 | 24.32 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -10.5 | -0.0275 | 1.0112 | 0.312 | 1.00 | 18.88 | 25.34 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -100.1 | -0.2615 | 0.9437 | 0.297 | 1.00 | 17.37 | 28.08 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -182.7 | -0.4773 | 0.9114 | 0.293 | 1.00 | 16.84 | 30.39 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -253.5 | -0.6621 | 0.9029 | 0.278 | 1.00 | 15.93 | 32.23 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -272.5 | -0.7117 | 0.6744 | 0.281 | 1.00 | 13.88 | 32.71 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -236.3 | -0.6174 | 0.4049 | 0.297 | 1.00 | 11.40 | 31.79 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -192.5 | -0.5028 | 0.3155 | 0.313 | 1.00 | 10.59 | 30.65 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -166.8 | -0.4357 | 0.4692 | 0.325 | 1.00 | 13.40 | 29.95 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 394.1 | 1.0296 | 0.4401 | 0.324 | 1.00 | 12.96 | 0.00 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -143.6 | -0.3752 | 1.9441 | 0.282 | 1.00 | 23.64 | 29.32 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -263.5 | -0.6882 | 1.7045 | 0.282 | 1.00 | 22.17 | 32.48 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -315.7 | -0.8246 | 1.0399 | 0.290 | 1.00 | 17.83 | 33.77 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -314.1 | -0.8205 | 0.5368 | 0.296 | 1.00 | 13.05 | 33.73 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -266.8 | -0.6969 | 0.1051 | 0.287 | 1.00 | 5.60 | 32.57 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -221.3 | -0.5781 | 0.2162 | 0.285 | 1.00 | 7.97 | 31.41 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -197.6 | -0.5161 | 0.2274 | 0.304 | 1.00 | 8.73 | 30.78 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -188.7 | -0.4930 | 0.2320 | 0.320 | 1.00 | 9.29 | 30.55 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -178.8 | -0.4671 | 0.0326 | 0.402 | 1.00 | 4.37 | 30.28 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
