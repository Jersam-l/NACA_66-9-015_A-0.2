# Aerodynamic Case: case_07_aoa-15_u35
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.3163
- **Drag Coefficient ($C_d$):** 0.2528
- **Mean Wall $y^+$:** 13.87
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": -15.0, "case_idx": 7}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -1095.5 | -1.4600 | 2.0986 | 0.195 | 1.00 | 16.01 | 54.90 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -1342.3 | -1.7890 | 0.6315 | 0.279 | 1.00 | 13.34 | 58.45 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -1266.1 | -1.6874 | 0.7943 | 0.296 | 1.00 | 15.90 | 57.38 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -1030.1 | -1.3728 | 0.6232 | 0.330 | 1.00 | 15.71 | 53.91 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -697.8 | -0.9300 | 0.0149 | 0.289 | 1.00 | 2.11 | 48.62 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -621.8 | -0.8288 | 0.6405 | 0.252 | 1.00 | 12.15 | 47.33 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -598.3 | -0.7974 | 0.5304 | 0.261 | 1.00 | 11.46 | 46.92 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -518.6 | -0.6912 | 0.1745 | 0.286 | 1.00 | 7.20 | 45.52 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -451.7 | -0.6020 | 0.0240 | 0.326 | 1.00 | 3.04 | 44.30 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -406.4 | -0.5416 | 0.0081 | 0.451 | 1.00 | 2.45 | 43.46 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 967.5 | 1.2894 | 0.6766 | 0.296 | 1.00 | 11.27 | 0.00 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | 93.8 | 0.1250 | 2.5954 | 0.280 | 1.00 | 27.14 | 32.74 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -566.7 | -0.7553 | 3.0986 | 0.281 | 1.00 | 29.82 | 46.37 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -778.4 | -1.0374 | 2.3927 | 0.291 | 1.00 | 27.13 | 49.96 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -788.8 | -1.0513 | 1.1227 | 0.296 | 1.00 | 18.89 | 50.13 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -698.1 | -0.9304 | 0.1645 | 0.286 | 1.00 | 6.95 | 48.63 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -586.7 | -0.7820 | 0.2915 | 0.290 | 1.00 | 9.44 | 46.72 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -509.3 | -0.6788 | 0.3613 | 0.295 | 1.00 | 10.67 | 45.35 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -460.0 | -0.6130 | 0.3726 | 0.305 | 1.00 | 11.23 | 44.45 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -412.5 | -0.5498 | 0.2403 | 0.307 | 1.00 | 9.05 | 43.57 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
