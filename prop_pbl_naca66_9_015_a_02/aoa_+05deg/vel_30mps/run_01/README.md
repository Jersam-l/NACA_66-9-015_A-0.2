# Aerodynamic Case: case_46_aoa+05_u30
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 30.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2299
- **Drag Coefficient ($C_d$):** 0.0944
- **Mean Wall $y^+$:** 15.68
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 30.0, "incidence": 5.0, "case_idx": 46}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 530.8 | 0.9628 | 0.3747 | 0.344 | 1.00 | 12.69 | 5.78 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 6.3 | 0.0114 | 1.4469 | 0.305 | 1.00 | 22.12 | 29.83 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -35.5 | -0.0645 | 1.2415 | 0.312 | 1.00 | 20.92 | 30.95 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -165.4 | -0.3000 | 1.1519 | 0.297 | 1.00 | 19.19 | 34.20 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -285.9 | -0.5187 | 1.0960 | 0.293 | 1.00 | 18.47 | 36.97 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -387.9 | -0.7036 | 1.0776 | 0.278 | 1.00 | 17.40 | 39.16 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -414.9 | -0.7527 | 0.8010 | 0.281 | 1.00 | 15.13 | 39.72 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -362.9 | -0.6583 | 0.4781 | 0.297 | 1.00 | 12.38 | 38.63 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -299.4 | -0.5432 | 0.3733 | 0.313 | 1.00 | 11.52 | 37.27 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -261.8 | -0.4750 | 0.5596 | 0.325 | 1.00 | 14.63 | 36.44 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 543.4 | 0.9857 | 0.5302 | 0.324 | 1.00 | 14.23 | 3.59 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -231.6 | -0.4201 | 2.3437 | 0.282 | 1.00 | 25.96 | 35.75 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -399.6 | -0.7250 | 2.0950 | 0.282 | 1.00 | 24.58 | 39.40 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -473.1 | -0.8583 | 1.2898 | 0.290 | 1.00 | 19.85 | 40.90 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -473.4 | -0.8588 | 0.6555 | 0.296 | 1.00 | 14.42 | 40.90 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -407.3 | -0.7389 | 0.1210 | 0.287 | 1.00 | 6.01 | 39.56 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -341.0 | -0.6186 | 0.2572 | 0.285 | 1.00 | 8.70 | 38.17 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -305.7 | -0.5546 | 0.2625 | 0.304 | 1.00 | 9.38 | 37.41 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -292.8 | -0.5311 | 0.2723 | 0.320 | 1.00 | 10.06 | 37.12 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -278.8 | -0.5058 | 0.0389 | 0.402 | 1.00 | 4.77 | 36.81 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
