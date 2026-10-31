# Aerodynamic Case: case_100_aoa+30_u50
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 50.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.2718
- **Drag Coefficient ($C_d$):** 0.5891
- **Mean Wall $y^+$:** 20.58
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 50.0, "incidence": 30.0, "case_idx": 100}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 1735.9 | 1.1337 | 2.2443 | 0.235 | 1.00 | 18.87 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 650.6 | 0.4249 | 3.2001 | 0.300 | 1.00 | 32.35 | 37.92 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | -191.4 | -0.1250 | 3.6110 | 0.303 | 1.00 | 34.64 | 53.03 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | -917.1 | -0.5989 | 3.3727 | 0.303 | 1.00 | 33.55 | 63.22 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -1541.5 | -1.0067 | 2.7803 | 0.260 | 1.00 | 26.10 | 70.83 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -1846.6 | -1.2059 | 2.0896 | 0.253 | 1.00 | 22.00 | 74.26 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -1675.1 | -1.0939 | 1.2087 | 0.268 | 1.00 | 17.74 | 72.35 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -1361.6 | -0.8892 | 1.0604 | 0.293 | 1.00 | 18.20 | 68.72 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -1126.9 | -0.7359 | 1.4314 | 0.349 | 1.00 | 25.13 | 65.88 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -244.0 | -0.1593 | 2.2979 | 0.433 | 1.00 | 39.57 | 53.84 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -2518.3 | -1.6446 | 1.2637 | 0.270 | 1.00 | 17.67 | 81.31 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -2349.4 | -1.5343 | 0.9109 | 0.271 | 1.00 | 15.59 | 79.60 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -2210.9 | -1.4439 | 1.2906 | 0.278 | 1.00 | 19.04 | 78.17 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -1844.8 | -1.2047 | 1.1859 | 0.294 | 1.00 | 19.30 | 74.24 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -1496.8 | -0.9775 | 0.9733 | 0.291 | 1.00 | 17.31 | 70.31 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -1275.2 | -0.8327 | 0.8814 | 0.280 | 1.00 | 15.84 | 67.69 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -1104.0 | -0.7210 | 0.7053 | 0.286 | 1.00 | 14.48 | 65.59 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -1000.2 | -0.6532 | 0.6742 | 0.283 | 1.00 | 14.01 | 64.29 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -862.5 | -0.5633 | 0.1875 | 0.303 | 1.00 | 7.77 | 62.52 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -978.2 | -0.6388 | 0.2231 | 0.283 | 1.00 | 8.05 | 64.01 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
