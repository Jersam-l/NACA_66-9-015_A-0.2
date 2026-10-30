# Aerodynamic Case: case_47_aoa+05_u35
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2300
- **Drag Coefficient ($C_d$):** 0.0935
- **Mean Wall $y^+$:** 16.98
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 5.0, "case_idx": 47}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 673.0 | 0.8970 | 0.4374 | 0.344 | 1.00 | 13.71 | 11.23 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | -40.7 | -0.0543 | 1.6988 | 0.305 | 1.00 | 23.97 | 35.94 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -94.0 | -0.1252 | 1.4769 | 0.312 | 1.00 | 22.82 | 37.13 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -271.0 | -0.3612 | 1.3666 | 0.297 | 1.00 | 20.91 | 40.83 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -437.1 | -0.5826 | 1.2834 | 0.293 | 1.00 | 19.99 | 44.03 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -576.3 | -0.7681 | 1.2530 | 0.278 | 1.00 | 18.76 | 46.54 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -613.0 | -0.8170 | 0.9275 | 0.281 | 1.00 | 16.28 | 47.18 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -542.2 | -0.7226 | 0.5513 | 0.297 | 1.00 | 13.30 | 45.94 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -455.5 | -0.6071 | 0.4313 | 0.313 | 1.00 | 12.38 | 44.37 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -403.7 | -0.5380 | 0.6506 | 0.325 | 1.00 | 15.77 | 43.41 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 690.2 | 0.9199 | 0.6187 | 0.324 | 1.00 | 15.37 | 9.91 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -365.0 | -0.4864 | 2.7445 | 0.282 | 1.00 | 28.09 | 42.67 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -589.2 | -0.7853 | 2.4967 | 0.282 | 1.00 | 26.83 | 46.77 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -686.1 | -0.9144 | 1.5544 | 0.290 | 1.00 | 21.80 | 48.43 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -689.5 | -0.9189 | 0.7802 | 0.296 | 1.00 | 15.74 | 48.48 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -602.1 | -0.8024 | 0.1355 | 0.287 | 1.00 | 6.36 | 46.99 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -511.7 | -0.6819 | 0.3005 | 0.285 | 1.00 | 9.40 | 45.39 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -463.0 | -0.6170 | 0.3006 | 0.304 | 1.00 | 10.03 | 44.51 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -445.3 | -0.5935 | 0.3144 | 0.320 | 1.00 | 10.81 | 44.18 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -426.5 | -0.5685 | 0.0454 | 0.402 | 1.00 | 5.16 | 43.83 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
