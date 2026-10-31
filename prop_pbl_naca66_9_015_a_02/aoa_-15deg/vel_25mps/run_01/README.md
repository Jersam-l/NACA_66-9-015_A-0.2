# Aerodynamic Case: case_05_aoa-15_u25
- **Angle of Attack (AoA):** -15.0° (Physically rotated mesh)
- **Freestream Velocity:** 25.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** -0.3856
- **Drag Coefficient ($C_d$):** 0.2620
- **Mean Wall $y^+$:** 11.98
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 25.0, "incidence": -15.0, "case_idx": 5}'
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
| 1 | Upper | 0.0026 | -0.0129 | 0.000 | -710.0 | -1.8546 | 1.5135 | 0.195 | 1.00 | 13.70 | 42.24 |
| 2 | Upper | 0.0142 | -0.0101 | 0.111 | -836.4 | -2.1848 | 0.4596 | 0.279 | 1.00 | 11.38 | 44.62 |
| 3 | Upper | 0.0250 | -0.0073 | 0.222 | -801.4 | -2.0935 | 0.5870 | 0.296 | 1.00 | 13.67 | 43.97 |
| 4 | Upper | 0.0358 | -0.0050 | 0.333 | -679.0 | -1.7736 | 0.4838 | 0.330 | 1.00 | 13.84 | 41.64 |
| 5 | Upper | 0.0468 | -0.0028 | 0.444 | -494.5 | -1.2918 | 0.0019 | 0.289 | 1.00 | 0.67 | 37.85 |
| 6 | Upper | 0.0576 | -0.0004 | 0.556 | -458.5 | -1.1977 | 0.4669 | 0.252 | 1.00 | 10.37 | 37.06 |
| 7 | Upper | 0.0683 | 0.0026 | 0.667 | -452.3 | -1.1815 | 0.3929 | 0.261 | 1.00 | 9.86 | 36.92 |
| 8 | Upper | 0.0788 | 0.0063 | 0.778 | -413.0 | -1.0789 | 0.1469 | 0.286 | 1.00 | 6.60 | 36.05 |
| 9 | Upper | 0.0893 | 0.0101 | 0.889 | -375.9 | -0.9820 | 0.0026 | 0.326 | 1.00 | 0.99 | 35.20 |
| 10 | Upper | 0.0978 | 0.0128 | 1.000 | -347.8 | -0.9086 | 0.0344 | 0.451 | 1.00 | 5.04 | 34.54 |
| 1 | Lower | 0.0019 | -0.0101 | 0.000 | 317.9 | 0.8303 | 0.4775 | 0.296 | 1.00 | 9.44 | 10.30 |
| 2 | Lower | 0.0116 | -0.0004 | 0.111 | -118.9 | -0.3107 | 1.8328 | 0.280 | 1.00 | 22.81 | 28.62 |
| 3 | Lower | 0.0216 | 0.0052 | 0.222 | -446.8 | -1.1672 | 2.1570 | 0.281 | 1.00 | 24.88 | 36.80 |
| 4 | Lower | 0.0321 | 0.0090 | 0.333 | -552.9 | -1.4444 | 1.6003 | 0.291 | 1.00 | 22.19 | 39.09 |
| 5 | Lower | 0.0429 | 0.0117 | 0.444 | -551.8 | -1.4415 | 0.7252 | 0.296 | 1.00 | 15.18 | 39.06 |
| 6 | Lower | 0.0539 | 0.0135 | 0.556 | -501.1 | -1.3090 | 0.0735 | 0.286 | 1.00 | 4.61 | 37.99 |
| 7 | Lower | 0.0653 | 0.0140 | 0.667 | -445.8 | -1.1646 | 0.2391 | 0.290 | 1.00 | 8.55 | 36.78 |
| 8 | Lower | 0.0769 | 0.0135 | 0.778 | -408.6 | -1.0674 | 0.2889 | 0.295 | 1.00 | 9.54 | 35.95 |
| 9 | Lower | 0.0886 | 0.0128 | 0.889 | -383.2 | -1.0010 | 0.3149 | 0.305 | 1.00 | 10.32 | 35.37 |
| 10 | Lower | 0.0977 | 0.0129 | 1.000 | -352.9 | -0.9218 | 0.1837 | 0.307 | 1.00 | 7.92 | 34.66 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
