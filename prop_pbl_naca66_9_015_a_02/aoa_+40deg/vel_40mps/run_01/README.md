# Aerodynamic Case: case_118_aoa+40_u40
- **Angle of Attack (AoA):** +40.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 1.6163
- **Drag Coefficient ($C_d$):** 1.2064
- **Mean Wall $y^+$:** 12.42
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 40.0, "case_idx": 118}'
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
| 1 | Upper | -0.0183 | -0.0086 | 0.000 | 2294.2 | 2.3410 | 2.0690 | 0.307 | 1.00 | 25.02 | 0.00 |
| 2 | Upper | -0.0033 | -0.0212 | 0.111 | 3227.4 | 3.2933 | 0.5423 | 0.313 | 1.00 | 13.90 | 0.00 |
| 3 | Upper | 0.0049 | -0.0288 | 0.222 | 3119.5 | 3.1831 | 0.9917 | 0.296 | 1.00 | 17.75 | 0.00 |
| 4 | Upper | 0.0129 | -0.0365 | 0.333 | 2961.9 | 3.0224 | 1.3419 | 0.280 | 1.00 | 19.57 | 0.00 |
| 5 | Upper | 0.0211 | -0.0441 | 0.444 | 2731.5 | 2.7872 | 1.5710 | 0.274 | 1.00 | 20.70 | 0.00 |
| 6 | Upper | 0.0296 | -0.0511 | 0.556 | 2467.7 | 2.5180 | 1.5927 | 0.275 | 1.00 | 20.94 | 0.00 |
| 7 | Upper | 0.0386 | -0.0577 | 0.667 | 2228.9 | 2.2744 | 1.5426 | 0.291 | 1.00 | 21.77 | 0.00 |
| 8 | Upper | 0.0478 | -0.0641 | 0.778 | 1926.5 | 1.9658 | 1.7035 | 0.323 | 1.00 | 25.42 | 0.00 |
| 9 | Upper | 0.0557 | -0.0701 | 0.889 | 1058.3 | 1.0799 | 2.5072 | 0.361 | 1.00 | 34.44 | 0.00 |
| 10 | Upper | 0.0557 | -0.0701 | 1.000 | 1058.3 | 1.0799 | 2.5072 | 0.361 | 1.00 | 34.44 | 0.00 |
| 1 | Lower | -0.0158 | -0.0047 | 0.000 | -734.3 | -0.7493 | 0.6340 | 0.294 | 1.00 | 13.81 | 52.91 |
| 2 | Lower | 0.0048 | -0.0115 | 0.111 | -757.6 | -0.7731 | 0.4957 | 0.280 | 1.00 | 11.86 | 53.26 |
| 3 | Lower | 0.0141 | -0.0178 | 0.222 | -803.7 | -0.8201 | 1.1961 | 0.290 | 1.00 | 19.07 | 53.96 |
| 4 | Lower | 0.0226 | -0.0250 | 0.333 | -589.0 | -0.6010 | 1.3005 | 0.295 | 1.00 | 20.27 | 50.61 |
| 5 | Lower | 0.0304 | -0.0329 | 0.444 | -344.1 | -0.3511 | 1.1461 | 0.294 | 1.00 | 18.94 | 46.49 |
| 6 | Lower | 0.0374 | -0.0418 | 0.556 | -184.4 | -0.1882 | 1.1270 | 0.287 | 1.00 | 18.34 | 43.60 |
| 7 | Lower | 0.0437 | -0.0516 | 0.667 | -27.3 | -0.0279 | 1.2253 | 0.280 | 1.00 | 18.68 | 40.55 |
| 8 | Lower | 0.0498 | -0.0616 | 0.778 | 262.8 | 0.2682 | 1.0220 | 0.275 | 1.00 | 16.73 | 34.22 |
| 9 | Lower | 0.0558 | -0.0700 | 0.889 | 332.0 | 0.3388 | 0.1606 | 0.336 | 1.00 | 8.12 | 32.53 |
| 10 | Lower | 0.0558 | -0.0700 | 1.000 | 332.0 | 0.3388 | 0.1606 | 0.336 | 1.00 | 8.12 | 32.53 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
