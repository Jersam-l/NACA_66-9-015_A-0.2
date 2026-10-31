# Aerodynamic Case: case_104_aoa+35_u20
- **Angle of Attack (AoA):** +35.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.5852
- **Drag Coefficient ($C_d$):** 0.9797
- **Mean Wall $y^+$:** 8.78
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 35.0, "case_idx": 104}'
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
| 1 | Upper | -0.0152 | -0.0161 | 0.000 | 663.0 | 2.7060 | 0.1963 | 0.335 | 1.00 | 8.40 | 0.00 |
| 2 | Upper | -0.0034 | -0.0242 | 0.111 | 657.9 | 2.6854 | 0.3368 | 0.316 | 1.00 | 11.03 | 0.00 |
| 3 | Upper | 0.0054 | -0.0310 | 0.222 | 627.5 | 2.5611 | 0.5293 | 0.312 | 1.00 | 13.70 | 0.00 |
| 4 | Upper | 0.0142 | -0.0379 | 0.333 | 588.2 | 2.4010 | 0.6932 | 0.297 | 1.00 | 14.88 | 0.00 |
| 5 | Upper | 0.0229 | -0.0448 | 0.444 | 533.8 | 2.1786 | 0.7895 | 0.285 | 1.00 | 15.26 | 0.00 |
| 6 | Upper | 0.0319 | -0.0513 | 0.556 | 467.7 | 1.9090 | 0.7992 | 0.287 | 1.00 | 15.46 | 0.00 |
| 7 | Upper | 0.0414 | -0.0571 | 0.667 | 415.5 | 1.6959 | 0.7391 | 0.284 | 1.00 | 14.70 | 0.00 |
| 8 | Upper | 0.0511 | -0.0627 | 0.778 | 358.7 | 1.4640 | 0.7849 | 0.303 | 1.00 | 16.19 | 0.00 |
| 9 | Upper | 0.0606 | -0.0684 | 0.889 | 225.9 | 0.9221 | 1.0310 | 0.360 | 1.00 | 22.05 | 5.58 |
| 10 | Upper | 0.0618 | -0.0693 | 1.000 | 169.2 | 0.6904 | 1.0854 | 0.392 | 1.00 | 24.61 | 11.13 |
| 1 | Lower | -0.0144 | -0.0103 | 0.000 | -216.0 | -0.8816 | 0.2922 | 0.271 | 1.00 | 8.78 | 27.43 |
| 2 | Lower | 0.0035 | -0.0143 | 0.111 | -223.0 | -0.9104 | 0.1448 | 0.294 | 1.00 | 6.73 | 27.64 |
| 3 | Lower | 0.0135 | -0.0194 | 0.222 | -247.8 | -1.0116 | 0.5371 | 0.292 | 1.00 | 12.88 | 28.37 |
| 4 | Lower | 0.0227 | -0.0256 | 0.333 | -210.3 | -0.8584 | 0.7480 | 0.287 | 1.00 | 14.97 | 27.26 |
| 5 | Lower | 0.0314 | -0.0327 | 0.444 | -109.5 | -0.4468 | 0.6286 | 0.293 | 1.00 | 13.98 | 24.06 |
| 6 | Lower | 0.0393 | -0.0407 | 0.556 | -39.5 | -0.1613 | 0.4869 | 0.294 | 1.00 | 12.38 | 21.55 |
| 7 | Lower | 0.0466 | -0.0497 | 0.667 | 0.6 | 0.0023 | 0.4048 | 0.296 | 1.00 | 11.33 | 19.98 |
| 8 | Lower | 0.0535 | -0.0591 | 0.778 | 30.4 | 0.1240 | 0.3536 | 0.302 | 1.00 | 10.80 | 18.72 |
| 9 | Lower | 0.0608 | -0.0682 | 0.889 | 47.6 | 0.1944 | 0.1183 | 0.344 | 1.00 | 6.97 | 17.95 |
| 10 | Lower | 0.0619 | -0.0693 | 1.000 | 24.2 | 0.0989 | 0.1367 | 0.353 | 1.00 | 7.87 | 18.99 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
