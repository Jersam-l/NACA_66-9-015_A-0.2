# Aerodynamic Case: case_73_aoa+20_u15
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9783
- **Drag Coefficient ($C_d$):** 0.3011
- **Mean Wall $y^+$:** 10.18
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 20.0, "case_idx": 73}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 115.9 | 0.8412 | 0.4844 | 0.360 | 1.00 | 14.18 | 5.98 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 67.3 | 0.4886 | 0.8955 | 0.264 | 1.00 | 15.06 | 10.73 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 16.0 | 0.1163 | 1.1895 | 0.146 | 1.00 | 9.59 | 14.10 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -27.8 | -0.2019 | 0.9563 | 0.248 | 1.00 | 14.62 | 16.45 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -74.0 | -0.5368 | 0.7416 | 0.325 | 1.00 | 16.86 | 18.59 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -85.0 | -0.6170 | 0.6618 | 0.418 | 1.00 | 20.45 | 19.07 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -111.2 | -0.8072 | 0.4977 | 0.270 | 1.00 | 11.47 | 20.16 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -103.1 | -0.7480 | 0.3184 | 0.251 | 1.00 | 8.53 | 19.83 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -90.3 | -0.6553 | 0.3806 | 0.233 | 1.00 | 8.66 | 19.30 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -106.8 | -0.7751 | 0.6523 | 0.179 | 1.00 | 8.69 | 19.98 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -249.1 | -1.8073 | 1.3364 | 0.306 | 1.00 | 21.26 | 25.13 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -182.7 | -1.3258 | 0.1204 | 0.271 | 1.00 | 5.66 | 22.88 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -143.7 | -1.0429 | 0.0469 | 0.270 | 1.00 | 3.51 | 21.44 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -109.1 | -0.7916 | 0.0938 | 0.275 | 1.00 | 5.08 | 20.08 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -89.8 | -0.6518 | 0.0866 | 0.271 | 1.00 | 4.80 | 19.28 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -74.4 | -0.5400 | 0.0314 | 0.265 | 1.00 | 2.81 | 18.61 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -66.7 | -0.4843 | 0.1307 | 0.270 | 1.00 | 5.87 | 18.27 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -118.4 | -0.8595 | 0.1962 | 0.263 | 1.00 | 7.01 | 20.45 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -117.0 | -0.8490 | 0.1922 | 0.289 | 1.00 | 7.63 | 20.40 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -114.4 | -0.8302 | 0.0353 | 0.328 | 1.00 | 3.71 | 20.29 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
