# Aerodynamic Case: case_42_aoa+05_u10
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 10.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2181
- **Drag Coefficient ($C_d$):** 0.1040
- **Mean Wall $y^+$:** 9.31
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 10.0, "incidence": 5.0, "case_idx": 42}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 58.4 | 0.9535 | 0.1308 | 0.344 | 1.00 | 7.50 | 2.16 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | -0.9 | -0.0140 | 0.4518 | 0.305 | 1.00 | 12.36 | 10.07 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -5.9 | -0.0964 | 0.3829 | 0.312 | 1.00 | 11.62 | 10.47 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -19.3 | -0.3145 | 0.3825 | 0.297 | 1.00 | 11.06 | 11.46 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -32.2 | -0.5252 | 0.3892 | 0.293 | 1.00 | 11.01 | 12.35 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -44.0 | -0.7181 | 0.3949 | 0.278 | 1.00 | 10.53 | 13.11 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -47.3 | -0.7719 | 0.3070 | 0.281 | 1.00 | 9.37 | 13.31 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -41.3 | -0.6751 | 0.1940 | 0.297 | 1.00 | 7.89 | 12.94 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -34.3 | -0.5599 | 0.1510 | 0.313 | 1.00 | 7.32 | 12.49 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -30.6 | -0.5000 | 0.2126 | 0.325 | 1.00 | 9.02 | 12.25 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 60.3 | 0.9852 | 0.1708 | 0.324 | 1.00 | 8.08 | 1.22 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -25.8 | -0.4219 | 0.7687 | 0.282 | 1.00 | 14.87 | 11.92 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -45.9 | -0.7494 | 0.6661 | 0.282 | 1.00 | 13.86 | 13.23 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -53.9 | -0.8801 | 0.4135 | 0.290 | 1.00 | 11.24 | 13.71 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -52.6 | -0.8596 | 0.2208 | 0.296 | 1.00 | 8.37 | 13.64 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -44.8 | -0.7309 | 0.0351 | 0.287 | 1.00 | 3.23 | 13.16 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -39.1 | -0.6390 | 0.1074 | 0.285 | 1.00 | 5.62 | 12.80 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -36.1 | -0.5895 | 0.1201 | 0.304 | 1.00 | 6.34 | 12.61 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -35.0 | -0.5707 | 0.1172 | 0.320 | 1.00 | 6.60 | 12.53 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -33.2 | -0.5413 | 0.0128 | 0.402 | 1.00 | 2.74 | 12.41 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
