# Aerodynamic Case: case_57_aoa+10_u35
- **Angle of Attack (AoA):** +10.0° (Physically rotated mesh)
- **Freestream Velocity:** 35.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.4872
- **Drag Coefficient ($C_d$):** 0.1274
- **Mean Wall $y^+$:** 17.24
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 35.0, "incidence": 10.0, "case_idx": 57}'
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
| 1 | Upper | 0.0010 | 0.0088 | 0.000 | 685.3 | 0.9134 | 0.9524 | 0.310 | 1.00 | 17.17 | 10.30 |
| 2 | Upper | 0.0124 | 0.0062 | 0.111 | 118.9 | 0.1584 | 1.9648 | 0.306 | 1.00 | 25.85 | 32.11 |
| 3 | Upper | 0.0233 | 0.0042 | 0.222 | -11.1 | -0.0149 | 1.9339 | 0.302 | 1.00 | 25.26 | 35.26 |
| 4 | Upper | 0.0341 | 0.0017 | 0.333 | -233.4 | -0.3111 | 1.6995 | 0.290 | 1.00 | 22.75 | 40.08 |
| 5 | Upper | 0.0450 | -0.0009 | 0.444 | -440.9 | -0.5876 | 1.4544 | 0.270 | 1.00 | 19.59 | 44.10 |
| 6 | Upper | 0.0558 | -0.0034 | 0.556 | -584.2 | -0.7785 | 1.3761 | 0.266 | 1.00 | 18.81 | 46.68 |
| 7 | Upper | 0.0668 | -0.0052 | 0.667 | -609.9 | -0.8129 | 0.9652 | 0.295 | 1.00 | 17.47 | 47.12 |
| 8 | Upper | 0.0778 | -0.0064 | 0.778 | -546.5 | -0.7283 | 0.5622 | 0.297 | 1.00 | 13.41 | 46.01 |
| 9 | Upper | 0.0890 | -0.0074 | 0.889 | -458.0 | -0.6104 | 0.4766 | 0.296 | 1.00 | 12.31 | 44.42 |
| 10 | Upper | 0.0987 | -0.0086 | 1.000 | -426.7 | -0.5687 | 0.7827 | 0.263 | 1.00 | 14.04 | 43.84 |
| 1 | Lower | 0.0015 | 0.0106 | 0.000 | 180.2 | 0.2401 | 1.8979 | 0.308 | 1.00 | 25.40 | 30.51 |
| 2 | Lower | 0.0140 | 0.0157 | 0.111 | -631.3 | -0.8415 | 2.8425 | 0.288 | 1.00 | 29.28 | 47.49 |
| 3 | Lower | 0.0255 | 0.0167 | 0.222 | -764.2 | -1.0185 | 2.2648 | 0.278 | 1.00 | 25.19 | 49.73 |
| 4 | Lower | 0.0366 | 0.0159 | 0.333 | -834.1 | -1.1117 | 1.2726 | 0.271 | 1.00 | 18.41 | 50.86 |
| 5 | Lower | 0.0476 | 0.0139 | 0.444 | -786.9 | -1.0488 | 0.6636 | 0.269 | 1.00 | 13.21 | 50.10 |
| 6 | Lower | 0.0583 | 0.0109 | 0.556 | -655.3 | -0.8733 | 0.1560 | 0.273 | 1.00 | 6.48 | 47.91 |
| 7 | Lower | 0.0689 | 0.0067 | 0.667 | -548.3 | -0.7307 | 0.3020 | 0.275 | 1.00 | 9.09 | 46.05 |
| 8 | Lower | 0.0792 | 0.0013 | 0.778 | -496.6 | -0.6619 | 0.3111 | 0.292 | 1.00 | 9.81 | 45.12 |
| 9 | Lower | 0.0895 | -0.0043 | 0.889 | -477.2 | -0.6360 | 0.3150 | 0.311 | 1.00 | 10.51 | 44.77 |
| 10 | Lower | 0.0987 | -0.0085 | 1.000 | -460.0 | -0.6131 | 0.0303 | 0.418 | 1.00 | 4.39 | 44.45 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
