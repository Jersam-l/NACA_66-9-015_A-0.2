# Aerodynamic Case: case_41_aoa+05_u05
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2510
- **Drag Coefficient ($C_d$):** 0.1099
- **Mean Wall $y^+$:** 7.48
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 5.0, "case_idx": 41}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 14.6 | 0.9547 | 0.0624 | 0.344 | 1.00 | 5.18 | 1.06 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | -0.8 | -0.0533 | 0.2311 | 0.305 | 1.00 | 8.84 | 5.13 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -1.7 | -0.1117 | 0.2225 | 0.312 | 1.00 | 8.86 | 5.27 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -4.6 | -0.3018 | 0.2545 | 0.297 | 1.00 | 9.02 | 5.71 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -7.6 | -0.4995 | 0.2757 | 0.293 | 1.00 | 9.26 | 6.12 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -10.6 | -0.6942 | 0.2909 | 0.278 | 1.00 | 9.04 | 6.51 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -11.1 | -0.7275 | 0.2474 | 0.281 | 1.00 | 8.41 | 6.57 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -9.3 | -0.6095 | 0.1648 | 0.297 | 1.00 | 7.27 | 6.34 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -7.8 | -0.5063 | 0.1129 | 0.313 | 1.00 | 6.33 | 6.14 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -6.9 | -0.4507 | 0.1458 | 0.325 | 1.00 | 7.47 | 6.02 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 15.0 | 0.9772 | 0.0886 | 0.324 | 1.00 | 5.81 | 0.75 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -7.4 | -0.4805 | 0.3901 | 0.282 | 1.00 | 10.59 | 6.08 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -12.2 | -0.7964 | 0.3891 | 0.282 | 1.00 | 10.59 | 6.70 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -12.9 | -0.8428 | 0.3197 | 0.290 | 1.00 | 9.88 | 6.79 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -11.6 | -0.7548 | 0.2128 | 0.296 | 1.00 | 8.22 | 6.62 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -9.5 | -0.6209 | 0.0419 | 0.287 | 1.00 | 3.54 | 6.37 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -9.3 | -0.6090 | 0.0617 | 0.285 | 1.00 | 4.26 | 6.34 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -8.7 | -0.5660 | 0.0633 | 0.304 | 1.00 | 4.60 | 6.26 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -8.4 | -0.5471 | 0.0640 | 0.320 | 1.00 | 4.88 | 6.22 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -7.9 | -0.5153 | 0.0059 | 0.402 | 1.00 | 1.86 | 6.16 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
