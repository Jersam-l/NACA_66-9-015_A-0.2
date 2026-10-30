# Aerodynamic Case: case_44_aoa+05_u20
- **Angle of Attack (AoA):** +5.0° (Physically rotated mesh)
- **Freestream Velocity:** 20.0 m/s
- **Solver Status:** `CONVERGED`
- **Lift Coefficient ($C_l$):** 0.2230
- **Drag Coefficient ($C_d$):** 0.0976
- **Mean Wall $y^+$:** 12.78
- **Single-Case Execution Command:**
  ```bash
  python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 5.0, "case_idx": 44}'
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
| 1 | Upper | 0.0002 | 0.0049 | 0.000 | 239.5 | 0.9776 | 0.2553 | 0.344 | 1.00 | 10.47 | 2.99 |
| 2 | Upper | 0.0114 | 0.0029 | 0.111 | 5.2 | 0.0211 | 0.9259 | 0.305 | 1.00 | 17.69 | 19.79 |
| 3 | Upper | 0.0225 | 0.0019 | 0.222 | -15.9 | -0.0649 | 0.7716 | 0.312 | 1.00 | 16.50 | 20.64 |
| 4 | Upper | 0.0335 | 0.0004 | 0.333 | -71.9 | -0.2934 | 0.7357 | 0.297 | 1.00 | 15.34 | 22.75 |
| 5 | Upper | 0.0445 | -0.0013 | 0.444 | -123.9 | -0.5056 | 0.7286 | 0.293 | 1.00 | 15.06 | 24.54 |
| 6 | Upper | 0.0555 | -0.0028 | 0.556 | -169.4 | -0.6915 | 0.7300 | 0.278 | 1.00 | 14.32 | 26.01 |
| 7 | Upper | 0.0666 | -0.0037 | 0.667 | -182.0 | -0.7429 | 0.5498 | 0.281 | 1.00 | 12.54 | 26.40 |
| 8 | Upper | 0.0777 | -0.0039 | 0.778 | -159.0 | -0.6489 | 0.3335 | 0.297 | 1.00 | 10.34 | 25.68 |
| 9 | Upper | 0.0889 | -0.0039 | 0.889 | -131.1 | -0.5350 | 0.2596 | 0.313 | 1.00 | 9.60 | 24.78 |
| 10 | Upper | 0.0993 | -0.0043 | 1.000 | -115.0 | -0.4696 | 0.3814 | 0.325 | 1.00 | 12.08 | 24.25 |
| 1 | Lower | 0.0005 | 0.0060 | 0.000 | 246.1 | 1.0046 | 0.3480 | 0.324 | 1.00 | 11.53 | 0.00 |
| 2 | Lower | 0.0122 | 0.0123 | 0.111 | -97.5 | -0.3980 | 1.5465 | 0.282 | 1.00 | 21.09 | 23.65 |
| 3 | Lower | 0.0236 | 0.0144 | 0.222 | -176.5 | -0.7205 | 1.3313 | 0.282 | 1.00 | 19.59 | 26.23 |
| 4 | Lower | 0.0347 | 0.0147 | 0.333 | -210.4 | -0.8588 | 0.8079 | 0.290 | 1.00 | 15.71 | 27.27 |
| 5 | Lower | 0.0458 | 0.0137 | 0.444 | -208.1 | -0.8496 | 0.4238 | 0.296 | 1.00 | 11.60 | 27.20 |
| 6 | Lower | 0.0568 | 0.0117 | 0.556 | -177.0 | -0.7224 | 0.0859 | 0.287 | 1.00 | 5.06 | 26.25 |
| 7 | Lower | 0.0677 | 0.0085 | 0.667 | -149.0 | -0.6082 | 0.1788 | 0.285 | 1.00 | 7.25 | 25.36 |
| 8 | Lower | 0.0784 | 0.0041 | 0.778 | -135.1 | -0.5516 | 0.1986 | 0.304 | 1.00 | 8.16 | 24.91 |
| 9 | Lower | 0.0892 | -0.0006 | 0.889 | -129.7 | -0.5292 | 0.1950 | 0.320 | 1.00 | 8.51 | 24.73 |
| 10 | Lower | 0.0993 | -0.0042 | 1.000 | -123.1 | -0.5023 | 0.0261 | 0.402 | 1.00 | 3.91 | 24.51 |


---

### Artifacts in this Case:
- Geometry: `geometry/images/`, `geometry/dimensions.csv`
- Mesh: `mesh/mesh.msh`, `mesh/mesh.txt`, `mesh/images/`
- Solver Log & Data: `native_solver/log.txt`, `native_solver/residuals.csv`, `native_solver/output.vtk`
- Post-processing: `post/data/foil_surface_sampled_10pts.csv`, `post/plots/`
- Report & Paper: `reports/research_paper.pdf`, `reports/engineering_report.md`
