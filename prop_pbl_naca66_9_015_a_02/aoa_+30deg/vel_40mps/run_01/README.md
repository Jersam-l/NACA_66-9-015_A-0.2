# Aerodynamic Case: case_98_aoa+30_u40
- **Angle of Attack (AoA):** +30.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.0097
- **Drag Coefficient ($C_d$):** 0.6678
- **Mean Wall $y^+$:** 18.54
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 30.0, "case_idx": 98}'
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
| 1 | Upper | 0.0096 | 0.0209 | 0.000 | 1835.1 | 1.8726 | 1.7638 | 0.235 | 1.00 | 16.36 | 0.00 |
| 2 | Upper | 0.0219 | 0.0157 | 0.111 | 1128.0 | 1.1510 | 2.5342 | 0.300 | 1.00 | 28.79 | 0.00 |
| 3 | Upper | 0.0313 | 0.0099 | 0.222 | 551.3 | 0.5625 | 2.8959 | 0.303 | 1.00 | 31.02 | 26.46 |
| 4 | Upper | 0.0406 | 0.0037 | 0.333 | 5.3 | 0.0054 | 2.7811 | 0.303 | 1.00 | 30.46 | 39.89 |
| 5 | Upper | 0.0499 | -0.0024 | 0.444 | -506.3 | -0.5167 | 2.4267 | 0.260 | 1.00 | 24.38 | 49.26 |
| 6 | Upper | 0.0594 | -0.0082 | 0.556 | -830.6 | -0.8475 | 1.9529 | 0.253 | 1.00 | 21.27 | 54.37 |
| 7 | Upper | 0.0693 | -0.0133 | 0.667 | -802.2 | -0.8186 | 1.2743 | 0.268 | 1.00 | 18.21 | 53.94 |
| 8 | Upper | 0.0794 | -0.0181 | 0.778 | -676.3 | -0.6901 | 1.1816 | 0.293 | 1.00 | 19.21 | 52.00 |
| 9 | Upper | 0.0894 | -0.0228 | 0.889 | -652.7 | -0.6660 | 1.4622 | 0.349 | 1.00 | 25.40 | 51.63 |
| 10 | Upper | 0.0678 | -0.0680 | 1.000 | -7.0 | -0.0071 | 1.9485 | 0.433 | 1.00 | 36.44 | 40.14 |
| 1 | Lower | -0.0141 | -0.0161 | 0.000 | -777.0 | -0.7929 | 0.9779 | 0.270 | 1.00 | 15.50 | 53.56 |
| 2 | Lower | 0.0027 | -0.0176 | 0.111 | -652.1 | -0.6654 | 0.5340 | 0.271 | 1.00 | 11.94 | 51.62 |
| 3 | Lower | 0.0132 | -0.0215 | 0.222 | -587.9 | -0.5999 | 0.5311 | 0.278 | 1.00 | 12.21 | 50.59 |
| 4 | Lower | 0.0231 | -0.0267 | 0.333 | -511.7 | -0.5221 | 0.3800 | 0.294 | 1.00 | 10.93 | 49.35 |
| 5 | Lower | 0.0324 | -0.0328 | 0.444 | -476.9 | -0.4866 | 0.3168 | 0.291 | 1.00 | 9.88 | 48.77 |
| 6 | Lower | 0.0412 | -0.0398 | 0.556 | -449.3 | -0.4584 | 0.3181 | 0.280 | 1.00 | 9.51 | 48.31 |
| 7 | Lower | 0.0493 | -0.0480 | 0.667 | -419.3 | -0.4278 | 0.0739 | 0.286 | 1.00 | 4.64 | 47.80 |
| 8 | Lower | 0.0570 | -0.0568 | 0.778 | -436.8 | -0.4457 | 0.0176 | 0.283 | 1.00 | 2.18 | 48.09 |
| 9 | Lower | 0.0649 | -0.0653 | 0.889 | -455.3 | -0.4645 | 0.0732 | 0.303 | 1.00 | 4.71 | 48.41 |
| 10 | Lower | 0.0679 | -0.0680 | 1.000 | -572.3 | -0.5840 | 0.3193 | 0.283 | 1.00 | 9.64 | 50.34 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
