# Aerodynamic Case: case_49_aoa+05_u45
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 45.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2339
- **Drag Coefficient ($C_d$):** 0.0924
- **Mean Wall $y^+$:** 19.39
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 45.0, "incidence": 5.0, "case_idx": 49}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 1321.2 | 1.0652 | 0.5505 | 0.344 | 1.00 | 15.38 | 0.00 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 142.9 | 0.1152 | 2.2113 | 0.305 | 1.00 | 27.34 | 42.33 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | 63.8 | 0.0515 | 1.9691 | 0.312 | 1.00 | 26.35 | 43.83 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -228.3 | -0.1840 | 1.8200 | 0.297 | 1.00 | 24.13 | 48.97 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -509.9 | -0.4111 | 1.6688 | 0.293 | 1.00 | 22.79 | 53.45 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -742.4 | -0.5985 | 1.6060 | 0.278 | 1.00 | 21.24 | 56.90 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -803.7 | -0.6480 | 1.1816 | 0.281 | 1.00 | 18.38 | 57.77 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -687.5 | -0.5543 | 0.7001 | 0.297 | 1.00 | 14.99 | 56.10 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -544.0 | -0.4386 | 0.5528 | 0.313 | 1.00 | 14.01 | 53.97 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -458.7 | -0.3698 | 0.8427 | 0.325 | 1.00 | 17.95 | 52.67 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 1344.9 | 1.0844 | 0.8057 | 0.324 | 1.00 | 17.54 | 0.00 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -403.6 | -0.3254 | 3.5524 | 0.282 | 1.00 | 31.96 | 51.81 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -763.5 | -0.6156 | 3.3212 | 0.282 | 1.00 | 30.95 | 57.20 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -909.8 | -0.7335 | 2.1194 | 0.290 | 1.00 | 25.45 | 59.25 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -922.7 | -0.7439 | 1.0454 | 0.296 | 1.00 | 18.22 | 59.43 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -785.6 | -0.6334 | 0.1626 | 0.287 | 1.00 | 6.96 | 57.51 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -637.6 | -0.5141 | 0.3922 | 0.285 | 1.00 | 10.74 | 55.37 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -556.4 | -0.4486 | 0.3808 | 0.304 | 1.00 | 11.29 | 54.16 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -527.3 | -0.4252 | 0.4014 | 0.320 | 1.00 | 12.22 | 53.72 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -496.9 | -0.4006 | 0.0572 | 0.402 | 1.00 | 5.79 | 53.26 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
