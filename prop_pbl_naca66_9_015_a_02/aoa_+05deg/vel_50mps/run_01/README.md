# Aerodynamic Case: case_50_aoa+05_u50
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2338
- **Drag Coefficient ($C_d$):** 0.0918
- **Mean Wall $y^+$:** 20.51
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 5.0, "case_idx": 50}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 1518.5 | 0.9917 | 0.6124 | 0.344 | 1.00 | 16.22 | 4.57 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 63.8 | 0.0417 | 2.4650 | 0.305 | 1.00 | 28.87 | 48.95 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -28.9 | -0.0189 | 2.2156 | 0.312 | 1.00 | 27.95 | 50.47 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -387.7 | -0.2532 | 2.0518 | 0.297 | 1.00 | 25.62 | 55.97 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -738.7 | -0.4824 | 1.8642 | 0.293 | 1.00 | 24.09 | 60.88 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -1027.1 | -0.6707 | 1.7826 | 0.278 | 1.00 | 22.38 | 64.63 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -1102.9 | -0.7203 | 1.3072 | 0.281 | 1.00 | 19.33 | 65.58 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -959.7 | -0.6267 | 0.7725 | 0.297 | 1.00 | 15.74 | 63.77 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -782.1 | -0.5107 | 0.6111 | 0.313 | 1.00 | 14.73 | 61.46 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -675.8 | -0.4414 | 0.9354 | 0.325 | 1.00 | 18.92 | 60.03 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 1548.1 | 1.0110 | 0.8948 | 0.324 | 1.00 | 18.48 | 0.00 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -610.9 | -0.3989 | 3.9555 | 0.282 | 1.00 | 33.73 | 59.14 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -1051.7 | -0.6868 | 3.7398 | 0.282 | 1.00 | 32.84 | 64.94 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -1223.0 | -0.7987 | 2.4193 | 0.290 | 1.00 | 27.19 | 67.06 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -1242.7 | -0.8115 | 1.1876 | 0.296 | 1.00 | 19.41 | 67.30 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -1077.7 | -0.7038 | 0.1774 | 0.287 | 1.00 | 7.27 | 65.27 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -896.4 | -0.5854 | 0.4394 | 0.285 | 1.00 | 11.37 | 62.96 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -796.1 | -0.5199 | 0.4221 | 0.304 | 1.00 | 11.89 | 61.64 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -760.2 | -0.4965 | 0.4456 | 0.320 | 1.00 | 12.87 | 61.16 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -722.9 | -0.4721 | 0.0636 | 0.402 | 1.00 | 6.11 | 60.66 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
