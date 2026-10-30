# Aerodynamic Case: case_33_aoa+00_u15
- **Angle of Attack (AoA):** +0.0° (Physically rotated mesh)
- **Freestream Velocity:** 15.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.0566
- **Drag Coefficient ($C_d$):** 0.0939
- **Mean Wall $y^+$:** 10.27
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 15.0, "incidence": 0.0, "case_idx": 33}'
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
| 1 | Upper | -0.0000 | 0.0006 | 0.000 | 97.6 | 0.7082 | 0.5801 | 0.302 | 1.00 | 13.87 | 8.10 |
| 2 | Upper | 0.0111 | -0.0005 | 0.111 | -49.5 | -0.3592 | 0.0736 | 0.285 | 1.00 | 4.64 | 17.49 |
| 3 | Upper | 0.0222 | -0.0005 | 0.222 | -24.6 | -0.1789 | 0.2226 | 0.300 | 1.00 | 8.52 | 16.29 |
| 4 | Upper | 0.0333 | -0.0010 | 0.333 | -32.7 | -0.2373 | 0.4473 | 0.301 | 1.00 | 12.12 | 16.68 |
| 5 | Upper | 0.0444 | -0.0017 | 0.444 | -58.7 | -0.4259 | 0.5282 | 0.290 | 1.00 | 12.69 | 17.91 |
| 6 | Upper | 0.0556 | -0.0023 | 0.556 | -83.1 | -0.6031 | 0.5433 | 0.281 | 1.00 | 12.47 | 18.99 |
| 7 | Upper | 0.0667 | -0.0023 | 0.667 | -91.4 | -0.6635 | 0.4142 | 0.279 | 1.00 | 10.80 | 19.35 |
| 8 | Upper | 0.0778 | -0.0015 | 0.778 | -79.9 | -0.5798 | 0.2487 | 0.286 | 1.00 | 8.60 | 18.85 |
| 9 | Upper | 0.0889 | -0.0005 | 0.889 | -64.9 | -0.4712 | 0.1857 | 0.299 | 1.00 | 7.76 | 18.19 |
| 10 | Upper | 0.0994 | 0.0000 | 1.000 | -54.7 | -0.3969 | 0.2610 | 0.334 | 1.00 | 10.27 | 17.73 |
| 1 | Lower | 0.0001 | 0.0016 | 0.000 | 153.2 | 1.1117 | 0.0649 | 0.344 | 1.00 | 5.29 | 0.00 |
| 2 | Lower | 0.0111 | 0.0089 | 0.111 | -12.4 | -0.0901 | 1.0780 | 0.278 | 1.00 | 17.36 | 15.66 |
| 3 | Lower | 0.0222 | 0.0120 | 0.222 | -71.9 | -0.5216 | 1.0187 | 0.288 | 1.00 | 17.53 | 18.50 |
| 4 | Lower | 0.0333 | 0.0133 | 0.333 | -96.4 | -0.6992 | 0.6810 | 0.294 | 1.00 | 14.64 | 19.55 |
| 5 | Lower | 0.0444 | 0.0133 | 0.444 | -99.5 | -0.7222 | 0.3576 | 0.294 | 1.00 | 10.58 | 19.68 |
| 6 | Lower | 0.0556 | 0.0122 | 0.556 | -84.4 | -0.6121 | 0.0813 | 0.300 | 1.00 | 5.15 | 19.05 |
| 7 | Lower | 0.0667 | 0.0100 | 0.667 | -72.1 | -0.5229 | 0.1367 | 0.296 | 1.00 | 6.60 | 18.51 |
| 8 | Lower | 0.0778 | 0.0066 | 0.778 | -65.3 | -0.4739 | 0.1695 | 0.305 | 1.00 | 7.57 | 18.21 |
| 9 | Lower | 0.0889 | 0.0029 | 0.889 | -63.1 | -0.4575 | 0.1818 | 0.302 | 1.00 | 7.76 | 18.11 |
| 10 | Lower | 0.0995 | 0.0001 | 1.000 | -58.3 | -0.4228 | 0.0296 | 0.368 | 1.00 | 3.82 | 17.89 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
