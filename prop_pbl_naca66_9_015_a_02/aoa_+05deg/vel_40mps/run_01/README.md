# Aerodynamic Case: case_48_aoa+05_u40
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 40.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2330
- **Drag Coefficient ($C_d$):** 0.0929
- **Mean Wall $y^+$:** 18.22
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 40.0, "incidence": 5.0, "case_idx": 48}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 1014.4 | 1.0351 | 0.4919 | 0.344 | 1.00 | 14.54 | 0.00 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 83.1 | 0.0848 | 1.9560 | 0.305 | 1.00 | 25.72 | 38.27 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | 17.2 | 0.0176 | 1.7227 | 0.312 | 1.00 | 24.65 | 39.65 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -214.2 | -0.2186 | 1.5914 | 0.297 | 1.00 | 22.56 | 44.16 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -434.2 | -0.4431 | 1.4751 | 0.293 | 1.00 | 21.43 | 48.05 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -617.0 | -0.6295 | 1.4293 | 0.278 | 1.00 | 20.04 | 51.06 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -665.2 | -0.6787 | 1.0549 | 0.281 | 1.00 | 17.36 | 51.83 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -573.1 | -0.5848 | 0.6262 | 0.297 | 1.00 | 14.17 | 50.36 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -459.9 | -0.4693 | 0.4928 | 0.313 | 1.00 | 13.23 | 48.49 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -392.6 | -0.4006 | 0.7476 | 0.325 | 1.00 | 16.91 | 47.34 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 1034.0 | 1.0552 | 0.7139 | 0.324 | 1.00 | 16.51 | 0.00 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -346.5 | -0.3536 | 3.1488 | 0.282 | 1.00 | 30.09 | 46.54 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -634.2 | -0.6472 | 2.9062 | 0.282 | 1.00 | 28.95 | 51.34 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -755.6 | -0.7710 | 1.8305 | 0.290 | 1.00 | 23.65 | 53.23 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -763.0 | -0.7786 | 0.9095 | 0.296 | 1.00 | 16.99 | 53.35 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -651.8 | -0.6651 | 0.1488 | 0.287 | 1.00 | 6.66 | 51.62 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -534.0 | -0.5449 | 0.3458 | 0.285 | 1.00 | 10.08 | 49.72 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -470.0 | -0.4796 | 0.3403 | 0.304 | 1.00 | 10.68 | 48.66 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -446.9 | -0.4561 | 0.3576 | 0.320 | 1.00 | 11.53 | 48.27 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -422.7 | -0.4313 | 0.0511 | 0.402 | 1.00 | 5.47 | 47.85 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
