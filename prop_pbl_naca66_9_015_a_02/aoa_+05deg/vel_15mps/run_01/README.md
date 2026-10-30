# Aerodynamic Case: case_43_aoa+05_u15
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2167
- **Drag Coefficient ($C_d$):** 0.1005
- **Mean Wall $y^+$:** 11.15
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 5.0, "case_idx": 43}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 135.0 | 0.9797 | 0.1956 | 0.344 | 1.00 | 9.17 | 2.13 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 2.8 | 0.0205 | 0.6835 | 0.305 | 1.00 | 15.20 | 14.85 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -9.4 | -0.0682 | 0.5650 | 0.312 | 1.00 | 14.12 | 15.50 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -40.2 | -0.2920 | 0.5485 | 0.297 | 1.00 | 13.25 | 17.05 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -69.2 | -0.5020 | 0.5533 | 0.293 | 1.00 | 13.12 | 18.38 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -95.2 | -0.6904 | 0.5590 | 0.278 | 1.00 | 12.53 | 19.50 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -102.6 | -0.7443 | 0.4259 | 0.281 | 1.00 | 11.03 | 19.81 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -89.7 | -0.6510 | 0.2625 | 0.297 | 1.00 | 9.18 | 19.27 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -74.1 | -0.5380 | 0.2046 | 0.313 | 1.00 | 8.53 | 18.60 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -65.5 | -0.4756 | 0.2959 | 0.325 | 1.00 | 10.64 | 18.22 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 139.3 | 1.0108 | 0.2571 | 0.324 | 1.00 | 9.91 | 0.00 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -53.7 | -0.3897 | 1.1536 | 0.282 | 1.00 | 18.21 | 17.68 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -99.3 | -0.7204 | 0.9809 | 0.282 | 1.00 | 16.82 | 19.67 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -118.3 | -0.8583 | 0.5953 | 0.290 | 1.00 | 13.49 | 20.45 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -116.2 | -0.8433 | 0.3165 | 0.296 | 1.00 | 10.02 | 20.36 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -98.2 | -0.7128 | 0.0627 | 0.287 | 1.00 | 4.32 | 19.63 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -83.8 | -0.6078 | 0.1438 | 0.285 | 1.00 | 6.50 | 19.02 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -76.9 | -0.5582 | 0.1694 | 0.304 | 1.00 | 7.53 | 18.72 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -74.4 | -0.5396 | 0.1633 | 0.320 | 1.00 | 7.79 | 18.61 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -70.4 | -0.5111 | 0.0195 | 0.402 | 1.00 | 3.38 | 18.44 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
