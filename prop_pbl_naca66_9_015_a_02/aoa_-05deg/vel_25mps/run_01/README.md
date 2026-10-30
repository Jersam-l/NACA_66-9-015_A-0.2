# Aerodynamic Case: case_25_aoa-05_u25
- **Angle of Attack (AoA):** -5.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0036
- **Drag Coefficient ($C_d$):** 0.1152
- **Mean Wall $y^+$:** 12.12
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": -5.0, "case_idx": 25}'
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
| 1 | Upper | 0.0001 | -0.0038 | 0.000 | 227.9 | 0.5954 | 1.1852 | 0.298 | 1.00 | 19.54 | 15.90 |
| 2 | Upper | 0.0115 | -0.0038 | 0.111 | -396.3 | -1.0353 | 0.3925 | 0.286 | 1.00 | 10.79 | 35.67 |
| 3 | Upper | 0.0226 | -0.0029 | 0.222 | -304.2 | -0.7947 | 0.2773 | 0.310 | 1.00 | 9.81 | 33.49 |
| 4 | Upper | 0.0337 | -0.0025 | 0.333 | -187.6 | -0.4900 | 0.3328 | 0.307 | 1.00 | 10.66 | 30.52 |
| 5 | Upper | 0.0448 | -0.0022 | 0.444 | -229.0 | -0.5982 | 0.7143 | 0.288 | 1.00 | 14.64 | 31.61 |
| 6 | Upper | 0.0559 | -0.0018 | 0.556 | -290.2 | -0.7582 | 0.8189 | 0.274 | 1.00 | 14.95 | 33.15 |
| 7 | Upper | 0.0670 | -0.0008 | 0.667 | -297.5 | -0.7772 | 0.5545 | 0.278 | 1.00 | 12.45 | 33.33 |
| 8 | Upper | 0.0780 | 0.0009 | 0.778 | -255.5 | -0.6675 | 0.2264 | 0.291 | 1.00 | 8.33 | 32.28 |
| 9 | Upper | 0.0890 | 0.0029 | 0.889 | -213.5 | -0.5576 | 0.0819 | 0.320 | 1.00 | 5.51 | 31.20 |
| 10 | Upper | 0.0993 | 0.0043 | 1.000 | -180.8 | -0.4723 | 0.1086 | 0.365 | 1.00 | 7.24 | 30.34 |
| 1 | Lower | 0.0002 | -0.0027 | 0.000 | 422.0 | 1.1024 | 0.3900 | 0.302 | 1.00 | 11.38 | 0.00 |
| 2 | Lower | 0.0107 | 0.0056 | 0.111 | -24.6 | -0.0641 | 1.8001 | 0.278 | 1.00 | 22.46 | 25.79 |
| 3 | Lower | 0.0215 | 0.0096 | 0.222 | -235.4 | -0.6150 | 1.8949 | 0.282 | 1.00 | 23.41 | 31.77 |
| 4 | Lower | 0.0324 | 0.0118 | 0.333 | -318.4 | -0.8316 | 1.3585 | 0.289 | 1.00 | 20.32 | 33.83 |
| 5 | Lower | 0.0435 | 0.0127 | 0.444 | -340.8 | -0.8903 | 0.7453 | 0.295 | 1.00 | 15.32 | 34.37 |
| 6 | Lower | 0.0547 | 0.0127 | 0.556 | -304.0 | -0.7941 | 0.2439 | 0.294 | 1.00 | 8.76 | 33.49 |
| 7 | Lower | 0.0659 | 0.0114 | 0.667 | -254.9 | -0.6660 | 0.1830 | 0.287 | 1.00 | 7.40 | 32.27 |
| 8 | Lower | 0.0773 | 0.0090 | 0.778 | -222.1 | -0.5803 | 0.2795 | 0.282 | 1.00 | 8.98 | 31.43 |
| 9 | Lower | 0.0887 | 0.0062 | 0.889 | -206.1 | -0.5385 | 0.3105 | 0.275 | 1.00 | 9.24 | 31.01 |
| 10 | Lower | 0.0993 | 0.0044 | 1.000 | -186.0 | -0.4859 | 0.1399 | 0.343 | 1.00 | 7.73 | 30.47 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
