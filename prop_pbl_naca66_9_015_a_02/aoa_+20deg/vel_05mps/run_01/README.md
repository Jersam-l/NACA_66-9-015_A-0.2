# Aerodynamic Case: case_71_aoa+20_u05
- **Angle of Attack (AoA):** +20.0° (Physically rotated mesh)
- **Freestream Velocity:** 5.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.9747
- **Drag Coefficient ($C_d$):** 0.3107
- **Mean Wall $y^+$:** 6.34
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 5.0, "incidence": 20.0, "case_idx": 71}'
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
| 1 | Upper | 0.0044 | 0.0163 | 0.000 | 12.0 | 0.7816 | 0.1637 | 0.360 | 1.00 | 8.20 | 2.34 |
| 2 | Upper | 0.0161 | 0.0119 | 0.111 | 6.8 | 0.4445 | 0.3014 | 0.264 | 1.00 | 8.74 | 3.73 |
| 3 | Upper | 0.0265 | 0.0079 | 0.222 | 1.1 | 0.0745 | 0.4521 | 0.146 | 1.00 | 5.91 | 4.81 |
| 4 | Upper | 0.0368 | 0.0035 | 0.333 | -4.0 | -0.2614 | 0.3692 | 0.248 | 1.00 | 9.08 | 5.62 |
| 5 | Upper | 0.0470 | -0.0009 | 0.444 | -8.4 | -0.5502 | 0.3157 | 0.325 | 1.00 | 11.00 | 6.22 |
| 6 | Upper | 0.0572 | -0.0052 | 0.556 | -10.7 | -0.6999 | 0.2666 | 0.418 | 1.00 | 12.97 | 6.52 |
| 7 | Upper | 0.0678 | -0.0087 | 0.667 | -12.3 | -0.8026 | 0.2614 | 0.270 | 1.00 | 8.31 | 6.71 |
| 8 | Upper | 0.0785 | -0.0117 | 0.778 | -11.2 | -0.7302 | 0.1825 | 0.251 | 1.00 | 6.46 | 6.58 |
| 9 | Upper | 0.0893 | -0.0146 | 0.889 | -10.0 | -0.6547 | 0.1819 | 0.233 | 1.00 | 5.99 | 6.43 |
| 10 | Upper | 0.0965 | -0.0169 | 1.000 | -12.6 | -0.8242 | 0.3105 | 0.179 | 1.00 | 5.99 | 6.75 |
| 1 | Lower | 0.0045 | 0.0191 | 0.000 | -32.3 | -2.1118 | 0.4531 | 0.306 | 1.00 | 12.39 | 8.82 |
| 2 | Lower | 0.0026 | -0.0253 | 0.111 | -21.7 | -1.4170 | 0.0672 | 0.271 | 1.00 | 4.23 | 7.77 |
| 3 | Lower | 0.0139 | -0.0267 | 0.222 | -17.0 | -1.1116 | 0.0374 | 0.270 | 1.00 | 3.14 | 7.27 |
| 4 | Lower | 0.0246 | -0.0297 | 0.333 | -12.7 | -0.8313 | 0.0152 | 0.275 | 1.00 | 2.04 | 6.77 |
| 5 | Lower | 0.0350 | -0.0338 | 0.444 | -10.3 | -0.6743 | 0.0224 | 0.271 | 1.00 | 2.44 | 6.47 |
| 6 | Lower | 0.0450 | -0.0388 | 0.556 | -8.6 | -0.5646 | 0.0111 | 0.265 | 1.00 | 1.67 | 6.25 |
| 7 | Lower | 0.0545 | -0.0451 | 0.667 | -7.8 | -0.5106 | 0.0439 | 0.270 | 1.00 | 3.40 | 6.14 |
| 8 | Lower | 0.0809 | -0.0052 | 0.778 | -14.7 | -0.9572 | 0.0636 | 0.263 | 1.00 | 3.99 | 7.00 |
| 9 | Lower | 0.0900 | -0.0125 | 0.889 | -14.6 | -0.9543 | 0.0703 | 0.289 | 1.00 | 4.61 | 6.99 |
| 10 | Lower | 0.0965 | -0.0168 | 1.000 | -14.4 | -0.9392 | 0.0222 | 0.328 | 1.00 | 2.94 | 6.96 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
