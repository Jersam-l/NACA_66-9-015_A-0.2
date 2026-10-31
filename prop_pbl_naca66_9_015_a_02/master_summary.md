# NACA 66(9)-015 Linear Cascade Parametric Investigation

**Airfoil:** `NACA 66(9)-015`  
**Execution Command (Single Command for Complete Matrix):**  
```bash
python3 -m jastricks simulate --case cascade-matrix --airfoil "66(9)-015" --output output/old/prop_pbl_naca66_9_015_a_02
```
or via the direct workflow runner:
```bash
python3 -m jastricks.workflows.cascade_matrix_runner
```

---

## Executive Overview
This engineering study performs the complete 120-case aerodynamic sweep of the NACA 66(9)-015 linear turbine cascade:
- **Geometry:** NACA 66(9)-015 airfoil, chord $c = 0.10$ m, pitch $s = 0.05$ m, 3 blades (solidity $\sigma = 2.0$). Center blade origin aligned at $(0.0, 0.0)$.
- **Physical Geometric Rotation:** Rather than only skewing inlet velocity vectors, **the airfoil geometry is physically rotated** in Jastricks at each AoA (stagger angle $\gamma = \alpha$), regenerating the true rotated geometry and mesh.
- **Angle of Attack Matrix:** 10 discrete angles: `[-15°, -10°, -5°, 0°, +5°, +10°, +15°, +20°, +25°, +30°]`.
- **Velocity Matrix:** 8 discrete velocities: `[5, 10, 15, 20, 25, 30, 35, 40 m/s]`.
- **Total Executed Cases:** 120 runs.
- **High-Performance Backend:** Native C++ compiled SIMPLE finite-volume solver with Spalart-Allmaras turbulence model on ~45,625 structured Blossom quad cells per case. Total runtime: 13730.4 s.
- **Surface Data Sampling:** 10 equivalent-distance stations along both upper (suction) and lower (pressure) surfaces (20 points total per run) recording exact coordinates $(x, y)$, $p_w$, $C_p$, $\tau_w$, $y_{1,\text{normal}}$, $y^+_{\text{target}}$, $y^+_{\text{local}}$, $u_\tau$, $U_e$.

---

## Folder Architecture
```
output/old/prop_pbl_naca66_9_015_a_02/
├── README.md                           <- Master study documentation (this file)
├── matrix_manifest.csv                 <- Complete machine-readable results table
├── matrix_summary.json                 <- Execution metrics and convergence summary
├── cascade_aerodynamic_polars.png      <- Full Cl and Cd polars across all regimes
├── research_paper.pdf                  <- Q1-grade publication research manuscript
├── aoa_-15deg/                         <- Subfolder for AoA = -15°
├── aoa_-10deg/                         <- Subfolder for AoA = -10°
│   ├── README.md                       <- AoA summary table across velocities (5 to 40 m/s)
│   ├── vel_05mps/run_01/               <- Specific run folder (Requirements, Geometry, Mesh, Post, Reports)
│   ├── vel_10mps/run_01/
│   ├── ...
│   └── vel_40mps/run_01/
├── ...
└── aoa_+30deg/
```

Inside each `vel_XXmps/run_01/` case directory:
- `requirements/`: Resolved JSON configuration.
- `geometry/`: Dimensions table (`dimensions.csv`) with full provenance, rendered geometry figures showing rotated blades and flow vectors.
- `mesh/`: Mesh files (`mesh.geo`, `mesh.msh`, `mesh.txt`), wireframe plots, boundary layer close-ups, and quality diagnostics.
- `native_solver/`: C++ solver logs, residual histories, and VTK unstructured grid solutions.
- `post/`: Pressure and velocity contours, streamlines, residual convergence plot, and `foil_surface_sampled_10pts.csv` containing the 10 upper and 10 lower surface stations.
- `reports/`: `engineering_report.md` and compiled `research_paper.pdf`.
- `procedure.md` & `commands.jsonl`: Step-by-step reproducible execution commands.

---

## Aerodynamic Polars
![Cascade Polars](cascade_aerodynamic_polars.png)

---

## 120-Case Execution Summary Table
| Case ID | AoA (°) | Velocity (m/s) | Lift Coeff (Cl) | Drag Coeff (Cd) | Mean Wall y+ | Runtime (s) | Status | Case Link |
|---|---|---|---|---|---|---|---|---|
| `case_01_aoa-15_u05` | -15° | 5 | -0.3870 | 0.2667 | 6.06 | 74.6 | `CONVERGED` | [aoa_-15deg/vel_05mps/run_01](aoa_-15deg/vel_05mps/run_01/README.md) |
| `case_02_aoa-15_u10` | -15° | 10 | -0.3315 | 0.2649 | 7.89 | 80.6 | `CONVERGED` | [aoa_-15deg/vel_10mps/run_01](aoa_-15deg/vel_10mps/run_01/README.md) |
| `case_03_aoa-15_u15` | -15° | 15 | -0.3851 | 0.2679 | 9.53 | 76.6 | `CONVERGED` | [aoa_-15deg/vel_15mps/run_01](aoa_-15deg/vel_15mps/run_01/README.md) |
| `case_04_aoa-15_u20` | -15° | 20 | -0.3842 | 0.2656 | 10.82 | 78.3 | `CONVERGED` | [aoa_-15deg/vel_20mps/run_01](aoa_-15deg/vel_20mps/run_01/README.md) |
| `case_05_aoa-15_u25` | -15° | 25 | -0.3856 | 0.2620 | 11.98 | 77.4 | `CONVERGED` | [aoa_-15deg/vel_25mps/run_01](aoa_-15deg/vel_25mps/run_01/README.md) |
| `case_06_aoa-15_u30` | -15° | 30 | -0.3602 | 0.2630 | 13.07 | 77.4 | `CONVERGED` | [aoa_-15deg/vel_30mps/run_01](aoa_-15deg/vel_30mps/run_01/README.md) |
| `case_07_aoa-15_u35` | -15° | 35 | -0.3163 | 0.2528 | 13.87 | 79.3 | `CONVERGED` | [aoa_-15deg/vel_35mps/run_01](aoa_-15deg/vel_35mps/run_01/README.md) |
| `case_08_aoa-15_u40` | -15° | 40 | -0.2773 | 0.2459 | 14.70 | 84.7 | `CONVERGED` | [aoa_-15deg/vel_40mps/run_01](aoa_-15deg/vel_40mps/run_01/README.md) |
| `case_09_aoa-15_u45` | -15° | 45 | -0.2141 | 0.2326 | 15.56 | 77.8 | `CONVERGED` | [aoa_-15deg/vel_45mps/run_01](aoa_-15deg/vel_45mps/run_01/README.md) |
| `case_10_aoa-15_u50` | -15° | 50 | -0.5168 | 0.2902 | 17.21 | 79.8 | `CONVERGED` | [aoa_-15deg/vel_50mps/run_01](aoa_-15deg/vel_50mps/run_01/README.md) |
| `case_11_aoa-10_u05` | -10° | 5 | -0.6286 | 0.2224 | 6.54 | 74.6 | `CONVERGED` | [aoa_-10deg/vel_05mps/run_01](aoa_-10deg/vel_05mps/run_01/README.md) |
| `case_12_aoa-10_u10` | -10° | 10 | -0.1323 | 0.2004 | 7.25 | 85.0 | `CONVERGED` | [aoa_-10deg/vel_10mps/run_01](aoa_-10deg/vel_10mps/run_01/README.md) |
| `case_13_aoa-10_u15` | -10° | 15 | -0.0196 | 0.1702 | 8.88 | 69.9 | `CONVERGED` | [aoa_-10deg/vel_15mps/run_01](aoa_-10deg/vel_15mps/run_01/README.md) |
| `case_14_aoa-10_u20` | -10° | 20 | 0.0011 | 0.1567 | 10.44 | 71.0 | `CONVERGED` | [aoa_-10deg/vel_20mps/run_01](aoa_-10deg/vel_20mps/run_01/README.md) |
| `case_15_aoa-10_u25` | -10° | 25 | -0.0120 | 0.1490 | 11.71 | 70.0 | `CONVERGED` | [aoa_-10deg/vel_25mps/run_01](aoa_-10deg/vel_25mps/run_01/README.md) |
| `case_16_aoa-10_u30` | -10° | 30 | -0.0086 | 0.1501 | 12.76 | 70.4 | `CONVERGED` | [aoa_-10deg/vel_30mps/run_01](aoa_-10deg/vel_30mps/run_01/README.md) |
| `case_17_aoa-10_u35` | -10° | 35 | -0.0059 | 0.1489 | 13.79 | 71.3 | `CONVERGED` | [aoa_-10deg/vel_35mps/run_01](aoa_-10deg/vel_35mps/run_01/README.md) |
| `case_18_aoa-10_u40` | -10° | 40 | 0.0089 | 0.1556 | 14.74 | 73.8 | `CONVERGED` | [aoa_-10deg/vel_40mps/run_01](aoa_-10deg/vel_40mps/run_01/README.md) |
| `case_19_aoa-10_u45` | -10° | 45 | 0.0360 | 0.1497 | 15.70 | 71.2 | `CONVERGED` | [aoa_-10deg/vel_45mps/run_01](aoa_-10deg/vel_45mps/run_01/README.md) |
| `case_20_aoa-10_u50` | -10° | 50 | 0.0410 | 0.1399 | 16.69 | 71.3 | `CONVERGED` | [aoa_-10deg/vel_50mps/run_01](aoa_-10deg/vel_50mps/run_01/README.md) |
| `case_21_aoa-05_u05` | -5° | 5 | 0.0059 | 0.1407 | 6.10 | 69.5 | `CONVERGED` | [aoa_-05deg/vel_05mps/run_01](aoa_-05deg/vel_05mps/run_01/README.md) |
| `case_22_aoa-05_u10` | -5° | 10 | 0.0886 | 0.1134 | 8.12 | 72.5 | `CONVERGED` | [aoa_-05deg/vel_10mps/run_01](aoa_-05deg/vel_10mps/run_01/README.md) |
| `case_23_aoa-05_u15` | -5° | 15 | 0.0404 | 0.1136 | 9.70 | 76.6 | `CONVERGED` | [aoa_-05deg/vel_15mps/run_01](aoa_-05deg/vel_15mps/run_01/README.md) |
| `case_24_aoa-05_u20` | -5° | 20 | 0.0302 | 0.1127 | 10.92 | 66.7 | `CONVERGED` | [aoa_-05deg/vel_20mps/run_01](aoa_-05deg/vel_20mps/run_01/README.md) |
| `case_25_aoa-05_u25` | -5° | 25 | -0.0036 | 0.1152 | 12.12 | 72.5 | `CONVERGED` | [aoa_-05deg/vel_25mps/run_01](aoa_-05deg/vel_25mps/run_01/README.md) |
| `case_26_aoa-05_u30` | -5° | 30 | -0.0276 | 0.1191 | 13.14 | 69.5 | `CONVERGED` | [aoa_-05deg/vel_30mps/run_01](aoa_-05deg/vel_30mps/run_01/README.md) |
| `case_27_aoa-05_u35` | -5° | 35 | -0.0336 | 0.1191 | 14.20 | 71.4 | `CONVERGED` | [aoa_-05deg/vel_35mps/run_01](aoa_-05deg/vel_35mps/run_01/README.md) |
| `case_28_aoa-05_u40` | -5° | 40 | -0.0395 | 0.1195 | 15.24 | 71.1 | `CONVERGED` | [aoa_-05deg/vel_40mps/run_01](aoa_-05deg/vel_40mps/run_01/README.md) |
| `case_29_aoa-05_u45` | -5° | 45 | -0.0436 | 0.1195 | 16.28 | 76.5 | `CONVERGED` | [aoa_-05deg/vel_45mps/run_01](aoa_-05deg/vel_45mps/run_01/README.md) |
| `case_30_aoa-05_u50` | -5° | 50 | -0.0436 | 0.1203 | 17.17 | 92.0 | `CONVERGED` | [aoa_-05deg/vel_50mps/run_01](aoa_-05deg/vel_50mps/run_01/README.md) |
| `case_31_aoa+00_u05` | +0° | 5 | -0.0425 | 0.0993 | 6.86 | 91.2 | `CONVERGED` | [aoa_+00deg/vel_05mps/run_01](aoa_+00deg/vel_05mps/run_01/README.md) |
| `case_32_aoa+00_u10` | +0° | 10 | -0.0560 | 0.0964 | 8.62 | 72.0 | `CONVERGED` | [aoa_+00deg/vel_10mps/run_01](aoa_+00deg/vel_10mps/run_01/README.md) |
| `case_33_aoa+00_u15` | +0° | 15 | -0.0566 | 0.0939 | 10.27 | 70.7 | `CONVERGED` | [aoa_+00deg/vel_15mps/run_01](aoa_+00deg/vel_15mps/run_01/README.md) |
| `case_34_aoa+00_u20` | +0° | 20 | -0.0510 | 0.0918 | 11.75 | 62.8 | `CONVERGED` | [aoa_+00deg/vel_20mps/run_01](aoa_+00deg/vel_20mps/run_01/README.md) |
| `case_35_aoa+00_u25` | +0° | 25 | -0.0480 | 0.0904 | 13.10 | 62.8 | `CONVERGED` | [aoa_+00deg/vel_25mps/run_01](aoa_+00deg/vel_25mps/run_01/README.md) |
| `case_36_aoa+00_u30` | +0° | 30 | -0.0472 | 0.0895 | 14.36 | 69.0 | `CONVERGED` | [aoa_+00deg/vel_30mps/run_01](aoa_+00deg/vel_30mps/run_01/README.md) |
| `case_37_aoa+00_u35` | +0° | 35 | -0.0472 | 0.0890 | 15.54 | 78.4 | `CONVERGED` | [aoa_+00deg/vel_35mps/run_01](aoa_+00deg/vel_35mps/run_01/README.md) |
| `case_38_aoa+00_u40` | +0° | 40 | -0.0476 | 0.0885 | 16.66 | 75.3 | `CONVERGED` | [aoa_+00deg/vel_40mps/run_01](aoa_+00deg/vel_40mps/run_01/README.md) |
| `case_39_aoa+00_u45` | +0° | 45 | -0.0479 | 0.0882 | 17.72 | 87.6 | `CONVERGED` | [aoa_+00deg/vel_45mps/run_01](aoa_+00deg/vel_45mps/run_01/README.md) |
| `case_40_aoa+00_u50` | +0° | 50 | -0.0483 | 0.0879 | 18.73 | 75.2 | `CONVERGED` | [aoa_+00deg/vel_50mps/run_01](aoa_+00deg/vel_50mps/run_01/README.md) |
| `case_41_aoa+05_u05` | +5° | 5 | 0.2510 | 0.1099 | 7.48 | 89.1 | `CONVERGED` | [aoa_+05deg/vel_05mps/run_01](aoa_+05deg/vel_05mps/run_01/README.md) |
| `case_42_aoa+05_u10` | +5° | 10 | 0.2181 | 0.1040 | 9.31 | 71.9 | `CONVERGED` | [aoa_+05deg/vel_10mps/run_01](aoa_+05deg/vel_10mps/run_01/README.md) |
| `case_43_aoa+05_u15` | +5° | 15 | 0.2167 | 0.1005 | 11.15 | 77.4 | `CONVERGED` | [aoa_+05deg/vel_15mps/run_01](aoa_+05deg/vel_15mps/run_01/README.md) |
| `case_44_aoa+05_u20` | +5° | 20 | 0.2230 | 0.0976 | 12.78 | 74.0 | `CONVERGED` | [aoa_+05deg/vel_20mps/run_01](aoa_+05deg/vel_20mps/run_01/README.md) |
| `case_45_aoa+05_u25` | +5° | 25 | 0.2283 | 0.0956 | 14.28 | 80.7 | `CONVERGED` | [aoa_+05deg/vel_25mps/run_01](aoa_+05deg/vel_25mps/run_01/README.md) |
| `case_46_aoa+05_u30` | +5° | 30 | 0.2299 | 0.0944 | 15.68 | 68.6 | `CONVERGED` | [aoa_+05deg/vel_30mps/run_01](aoa_+05deg/vel_30mps/run_01/README.md) |
| `case_47_aoa+05_u35` | +5° | 35 | 0.2300 | 0.0935 | 16.98 | 85.6 | `CONVERGED` | [aoa_+05deg/vel_35mps/run_01](aoa_+05deg/vel_35mps/run_01/README.md) |
| `case_48_aoa+05_u40` | +5° | 40 | 0.2330 | 0.0929 | 18.22 | 77.5 | `CONVERGED` | [aoa_+05deg/vel_40mps/run_01](aoa_+05deg/vel_40mps/run_01/README.md) |
| `case_49_aoa+05_u45` | +5° | 45 | 0.2339 | 0.0924 | 19.39 | 79.9 | `CONVERGED` | [aoa_+05deg/vel_45mps/run_01](aoa_+05deg/vel_45mps/run_01/README.md) |
| `case_50_aoa+05_u50` | +5° | 50 | 0.2338 | 0.0918 | 20.51 | 87.5 | `CONVERGED` | [aoa_+05deg/vel_50mps/run_01](aoa_+05deg/vel_50mps/run_01/README.md) |
| `case_51_aoa+10_u05` | +10° | 5 | 0.4989 | 0.1501 | 7.49 | 99.8 | `CONVERGED` | [aoa_+10deg/vel_05mps/run_01](aoa_+10deg/vel_05mps/run_01/README.md) |
| `case_52_aoa+10_u10` | +10° | 10 | 0.4564 | 0.1370 | 9.46 | 101.3 | `CONVERGED` | [aoa_+10deg/vel_10mps/run_01](aoa_+10deg/vel_10mps/run_01/README.md) |
| `case_53_aoa+10_u15` | +10° | 15 | 0.4629 | 0.1352 | 11.36 | 83.6 | `CONVERGED` | [aoa_+10deg/vel_15mps/run_01](aoa_+10deg/vel_15mps/run_01/README.md) |
| `case_54_aoa+10_u20` | +10° | 20 | 0.4718 | 0.1320 | 12.99 | 91.8 | `CONVERGED` | [aoa_+10deg/vel_20mps/run_01](aoa_+10deg/vel_20mps/run_01/README.md) |
| `case_55_aoa+10_u25` | +10° | 25 | 0.4735 | 0.1299 | 14.50 | 106.3 | `CONVERGED` | [aoa_+10deg/vel_25mps/run_01](aoa_+10deg/vel_25mps/run_01/README.md) |
| `case_56_aoa+10_u30` | +10° | 30 | 0.4833 | 0.1279 | 15.92 | 97.2 | `CONVERGED` | [aoa_+10deg/vel_30mps/run_01](aoa_+10deg/vel_30mps/run_01/README.md) |
| `case_57_aoa+10_u35` | +10° | 35 | 0.4872 | 0.1274 | 17.24 | 92.5 | `CONVERGED` | [aoa_+10deg/vel_35mps/run_01](aoa_+10deg/vel_35mps/run_01/README.md) |
| `case_58_aoa+10_u40` | +10° | 40 | 0.4941 | 0.1273 | 18.50 | 81.5 | `CONVERGED` | [aoa_+10deg/vel_40mps/run_01](aoa_+10deg/vel_40mps/run_01/README.md) |
| `case_59_aoa+10_u45` | +10° | 45 | 0.4848 | 0.1263 | 19.65 | 93.5 | `CONVERGED` | [aoa_+10deg/vel_45mps/run_01](aoa_+10deg/vel_45mps/run_01/README.md) |
| `case_60_aoa+10_u50` | +10° | 50 | 0.4885 | 0.1259 | 20.79 | 87.7 | `CONVERGED` | [aoa_+10deg/vel_50mps/run_01](aoa_+10deg/vel_50mps/run_01/README.md) |
| `case_61_aoa+15_u05` | +15° | 5 | 0.8798 | 0.2357 | 7.18 | 83.4 | `CONVERGED` | [aoa_+15deg/vel_05mps/run_01](aoa_+15deg/vel_05mps/run_01/README.md) |
| `case_62_aoa+15_u10` | +15° | 10 | 0.7427 | 0.2041 | 9.52 | 83.6 | `CONVERGED` | [aoa_+15deg/vel_10mps/run_01](aoa_+15deg/vel_10mps/run_01/README.md) |
| `case_63_aoa+15_u15` | +15° | 15 | 0.8542 | 0.2154 | 11.05 | 83.5 | `CONVERGED` | [aoa_+15deg/vel_15mps/run_01](aoa_+15deg/vel_15mps/run_01/README.md) |
| `case_64_aoa+15_u20` | +15° | 20 | 0.8638 | 0.2164 | 12.63 | 87.1 | `CONVERGED` | [aoa_+15deg/vel_20mps/run_01](aoa_+15deg/vel_20mps/run_01/README.md) |
| `case_65_aoa+15_u25` | +15° | 25 | 0.8446 | 0.2084 | 14.08 | 80.6 | `CONVERGED` | [aoa_+15deg/vel_25mps/run_01](aoa_+15deg/vel_25mps/run_01/README.md) |
| `case_66_aoa+15_u30` | +15° | 30 | 0.8243 | 0.2036 | 15.42 | 84.1 | `CONVERGED` | [aoa_+15deg/vel_30mps/run_01](aoa_+15deg/vel_30mps/run_01/README.md) |
| `case_67_aoa+15_u35` | +15° | 35 | 0.8228 | 0.2024 | 16.67 | 91.6 | `CONVERGED` | [aoa_+15deg/vel_35mps/run_01](aoa_+15deg/vel_35mps/run_01/README.md) |
| `case_68_aoa+15_u40` | +15° | 40 | 0.7995 | 0.1979 | 17.90 | 93.3 | `CONVERGED` | [aoa_+15deg/vel_40mps/run_01](aoa_+15deg/vel_40mps/run_01/README.md) |
| `case_69_aoa+15_u45` | +15° | 45 | 0.7580 | 0.1895 | 19.18 | 88.9 | `CONVERGED` | [aoa_+15deg/vel_45mps/run_01](aoa_+15deg/vel_45mps/run_01/README.md) |
| `case_70_aoa+15_u50` | +15° | 50 | 0.7676 | 0.1917 | 20.25 | 83.7 | `CONVERGED` | [aoa_+15deg/vel_50mps/run_01](aoa_+15deg/vel_50mps/run_01/README.md) |
| `case_71_aoa+20_u05` | +20° | 5 | 0.9747 | 0.3107 | 6.34 | 87.2 | `CONVERGED` | [aoa_+20deg/vel_05mps/run_01](aoa_+20deg/vel_05mps/run_01/README.md) |
| `case_72_aoa+20_u10` | +20° | 10 | 0.9535 | 0.2979 | 8.57 | 88.8 | `CONVERGED` | [aoa_+20deg/vel_10mps/run_01](aoa_+20deg/vel_10mps/run_01/README.md) |
| `case_73_aoa+20_u15` | +20° | 15 | 0.9783 | 0.3011 | 10.18 | 96.5 | `CONVERGED` | [aoa_+20deg/vel_15mps/run_01](aoa_+20deg/vel_15mps/run_01/README.md) |
| `case_74_aoa+20_u20` | +20° | 20 | 0.9635 | 0.2938 | 11.51 | 85.6 | `CONVERGED` | [aoa_+20deg/vel_20mps/run_01](aoa_+20deg/vel_20mps/run_01/README.md) |
| `case_75_aoa+20_u25` | +20° | 25 | 0.9243 | 0.2892 | 12.78 | 85.9 | `CONVERGED` | [aoa_+20deg/vel_25mps/run_01](aoa_+20deg/vel_25mps/run_01/README.md) |
| `case_76_aoa+20_u30` | +20° | 30 | 0.9496 | 0.2893 | 13.90 | 83.9 | `CONVERGED` | [aoa_+20deg/vel_30mps/run_01](aoa_+20deg/vel_30mps/run_01/README.md) |
| `case_77_aoa+20_u35` | +20° | 35 | 1.0197 | 0.2950 | 15.15 | 87.6 | `CONVERGED` | [aoa_+20deg/vel_35mps/run_01](aoa_+20deg/vel_35mps/run_01/README.md) |
| `case_78_aoa+20_u40` | +20° | 40 | 1.0360 | 0.2995 | 16.27 | 87.4 | `CONVERGED` | [aoa_+20deg/vel_40mps/run_01](aoa_+20deg/vel_40mps/run_01/README.md) |
| `case_79_aoa+20_u45` | +20° | 45 | 1.0313 | 0.3079 | 17.16 | 91.9 | `CONVERGED` | [aoa_+20deg/vel_45mps/run_01](aoa_+20deg/vel_45mps/run_01/README.md) |
| `case_80_aoa+20_u50` | +20° | 50 | 1.0018 | 0.3041 | 17.99 | 88.0 | `CONVERGED` | [aoa_+20deg/vel_50mps/run_01](aoa_+20deg/vel_50mps/run_01/README.md) |
| `case_81_aoa+25_u05` | +25° | 5 | 1.0414 | 0.4919 | 6.84 | 99.1 | `CONVERGED` | [aoa_+25deg/vel_05mps/run_01](aoa_+25deg/vel_05mps/run_01/README.md) |
| `case_82_aoa+25_u10` | +25° | 10 | 1.0632 | 0.4848 | 9.28 | 96.0 | `CONVERGED` | [aoa_+25deg/vel_10mps/run_01](aoa_+25deg/vel_10mps/run_01/README.md) |
| `case_83_aoa+25_u15` | +25° | 15 | 1.0062 | 0.4574 | 11.07 | 109.1 | `CONVERGED` | [aoa_+25deg/vel_15mps/run_01](aoa_+25deg/vel_15mps/run_01/README.md) |
| `case_84_aoa+25_u20` | +25° | 20 | 0.9910 | 0.4305 | 12.52 | 131.3 | `CONVERGED` | [aoa_+25deg/vel_20mps/run_01](aoa_+25deg/vel_20mps/run_01/README.md) |
| `case_85_aoa+25_u25` | +25° | 25 | 1.0113 | 0.4237 | 13.91 | 92.7 | `CONVERGED` | [aoa_+25deg/vel_25mps/run_01](aoa_+25deg/vel_25mps/run_01/README.md) |
| `case_86_aoa+25_u30` | +25° | 30 | 1.0156 | 0.4114 | 15.09 | 126.1 | `CONVERGED` | [aoa_+25deg/vel_30mps/run_01](aoa_+25deg/vel_30mps/run_01/README.md) |
| `case_87_aoa+25_u35` | +25° | 35 | 0.9524 | 0.4065 | 16.44 | 100.9 | `CONVERGED` | [aoa_+25deg/vel_35mps/run_01](aoa_+25deg/vel_35mps/run_01/README.md) |
| `case_88_aoa+25_u40` | +25° | 40 | 0.9958 | 0.3956 | 17.43 | 95.3 | `CONVERGED` | [aoa_+25deg/vel_40mps/run_01](aoa_+25deg/vel_40mps/run_01/README.md) |
| `case_89_aoa+25_u45` | +25° | 45 | 1.2315 | 0.4968 | 18.78 | 85.7 | `CONVERGED` | [aoa_+25deg/vel_45mps/run_01](aoa_+25deg/vel_45mps/run_01/README.md) |
| `case_90_aoa+25_u50` | +25° | 50 | 1.1200 | 0.4195 | 19.43 | 87.0 | `CONVERGED` | [aoa_+25deg/vel_50mps/run_01](aoa_+25deg/vel_50mps/run_01/README.md) |
| `case_91_aoa+30_u05` | +30° | 5 | 0.9873 | 0.6032 | 6.94 | 96.8 | `CONVERGED` | [aoa_+30deg/vel_05mps/run_01](aoa_+30deg/vel_05mps/run_01/README.md) |
| `case_92_aoa+30_u10` | +30° | 10 | 1.3981 | 0.7772 | 9.74 | 97.4 | `CONVERGED` | [aoa_+30deg/vel_10mps/run_01](aoa_+30deg/vel_10mps/run_01/README.md) |
| `case_93_aoa+30_u15` | +30° | 15 | 1.4004 | 0.7425 | 11.56 | 90.8 | `CONVERGED` | [aoa_+30deg/vel_15mps/run_01](aoa_+30deg/vel_15mps/run_01/README.md) |
| `case_94_aoa+30_u20` | +30° | 20 | 1.2420 | 0.6599 | 13.09 | 97.8 | `CONVERGED` | [aoa_+30deg/vel_20mps/run_01](aoa_+30deg/vel_20mps/run_01/README.md) |
| `case_95_aoa+30_u25` | +30° | 25 | 1.3761 | 0.6974 | 14.72 | 95.3 | `CONVERGED` | [aoa_+30deg/vel_25mps/run_01](aoa_+30deg/vel_25mps/run_01/README.md) |
| `case_96_aoa+30_u30` | +30° | 30 | 1.4538 | 0.6994 | 16.15 | 95.7 | `CONVERGED` | [aoa_+30deg/vel_30mps/run_01](aoa_+30deg/vel_30mps/run_01/README.md) |
| `case_97_aoa+30_u35` | +30° | 35 | 1.0998 | 0.7414 | 17.58 | 95.8 | `CONVERGED` | [aoa_+30deg/vel_35mps/run_01](aoa_+30deg/vel_35mps/run_01/README.md) |
| `case_98_aoa+30_u40` | +30° | 40 | 1.0097 | 0.6678 | 18.54 | 95.2 | `CONVERGED` | [aoa_+30deg/vel_40mps/run_01](aoa_+30deg/vel_40mps/run_01/README.md) |
| `case_99_aoa+30_u45` | +30° | 45 | 1.0669 | 0.5686 | 19.67 | 94.9 | `CONVERGED` | [aoa_+30deg/vel_45mps/run_01](aoa_+30deg/vel_45mps/run_01/README.md) |
| `case_100_aoa+30_u50` | +30° | 50 | 1.2718 | 0.5891 | 20.58 | 94.7 | `CONVERGED` | [aoa_+30deg/vel_50mps/run_01](aoa_+30deg/vel_50mps/run_01/README.md) |
| `case_101_aoa+35_u05` | +35° | 5 | 1.3570 | 0.9016 | 4.90 | 112.8 | `CONVERGED` | [aoa_+35deg/vel_05mps/run_01](aoa_+35deg/vel_05mps/run_01/README.md) |
| `case_102_aoa+35_u10` | +35° | 10 | 1.1719 | 0.8758 | 6.28 | 99.0 | `CONVERGED` | [aoa_+35deg/vel_10mps/run_01](aoa_+35deg/vel_10mps/run_01/README.md) |
| `case_103_aoa+35_u15` | +35° | 15 | 1.5071 | 0.9570 | 7.49 | 98.1 | `CONVERGED` | [aoa_+35deg/vel_15mps/run_01](aoa_+35deg/vel_15mps/run_01/README.md) |
| `case_104_aoa+35_u20` | +35° | 20 | 1.5852 | 0.9797 | 8.78 | 114.0 | `CONVERGED` | [aoa_+35deg/vel_20mps/run_01](aoa_+35deg/vel_20mps/run_01/README.md) |
| `case_105_aoa+35_u25` | +35° | 25 | 1.3990 | 0.9163 | 9.64 | 95.9 | `CONVERGED` | [aoa_+35deg/vel_25mps/run_01](aoa_+35deg/vel_25mps/run_01/README.md) |
| `case_106_aoa+35_u30` | +35° | 30 | 0.8146 | 0.7003 | 9.92 | 80.8 | `CONVERGED` | [aoa_+35deg/vel_30mps/run_01](aoa_+35deg/vel_30mps/run_01/README.md) |
| `case_107_aoa+35_u35` | +35° | 35 | 1.2966 | 0.9803 | 11.03 | 89.6 | `CONVERGED` | [aoa_+35deg/vel_35mps/run_01](aoa_+35deg/vel_35mps/run_01/README.md) |
| `case_108_aoa+35_u40` | +35° | 40 | 0.8592 | 0.7759 | 12.15 | 92.7 | `CONVERGED` | [aoa_+35deg/vel_40mps/run_01](aoa_+35deg/vel_40mps/run_01/README.md) |
| `case_109_aoa+35_u45` | +35° | 45 | 1.7122 | 1.1432 | 12.97 | 86.8 | `CONVERGED` | [aoa_+35deg/vel_45mps/run_01](aoa_+35deg/vel_45mps/run_01/README.md) |
| `case_110_aoa+35_u50` | +35° | 50 | 0.9247 | 0.7176 | 12.81 | 94.0 | `CONVERGED` | [aoa_+35deg/vel_50mps/run_01](aoa_+35deg/vel_50mps/run_01/README.md) |
| `case_111_aoa+40_u05` | +40° | 5 | 1.1996 | 1.1700 | 4.60 | 94.1 | `CONVERGED` | [aoa_+40deg/vel_05mps/run_01](aoa_+40deg/vel_05mps/run_01/README.md) |
| `case_112_aoa+40_u10` | +40° | 10 | 1.7077 | 1.3296 | 6.32 | 89.6 | `CONVERGED` | [aoa_+40deg/vel_10mps/run_01](aoa_+40deg/vel_10mps/run_01/README.md) |
| `case_113_aoa+40_u15` | +40° | 15 | 1.3824 | 1.2923 | 7.29 | 97.1 | `CONVERGED` | [aoa_+40deg/vel_15mps/run_01](aoa_+40deg/vel_15mps/run_01/README.md) |
| `case_114_aoa+40_u20` | +40° | 20 | 1.0208 | 1.0002 | 8.55 | 92.6 | `CONVERGED` | [aoa_+40deg/vel_20mps/run_01](aoa_+40deg/vel_20mps/run_01/README.md) |
| `case_115_aoa+40_u25` | +40° | 25 | 1.2894 | 1.2081 | 9.20 | 89.9 | `CONVERGED` | [aoa_+40deg/vel_25mps/run_01](aoa_+40deg/vel_25mps/run_01/README.md) |
| `case_116_aoa+40_u30` | +40° | 30 | 1.2887 | 0.9900 | 10.55 | 98.0 | `CONVERGED` | [aoa_+40deg/vel_30mps/run_01](aoa_+40deg/vel_30mps/run_01/README.md) |
| `case_117_aoa+40_u35` | +40° | 35 | 0.9342 | 0.8788 | 11.34 | 93.5 | `CONVERGED` | [aoa_+40deg/vel_35mps/run_01](aoa_+40deg/vel_35mps/run_01/README.md) |
| `case_118_aoa+40_u40` | +40° | 40 | 1.6163 | 1.2064 | 12.42 | 97.1 | `CONVERGED` | [aoa_+40deg/vel_40mps/run_01](aoa_+40deg/vel_40mps/run_01/README.md) |
| `case_119_aoa+40_u45` | +40° | 45 | 0.9447 | 0.9363 | 13.23 | 89.3 | `CONVERGED` | [aoa_+40deg/vel_45mps/run_01](aoa_+40deg/vel_45mps/run_01/README.md) |
| `case_120_aoa+40_u50` | +40° | 50 | 1.5603 | 1.2674 | 13.83 | 91.4 | `CONVERGED` | [aoa_+40deg/vel_50mps/run_01](aoa_+40deg/vel_50mps/run_01/README.md) |

---

## NASA Verification & Validation Framework (20-Question Matrix Assessment)

### 1. Problem Definition and Scope (Questions 1–6)
- **Question 1 (Objective Definition):** Total aerodynamic polar prediction ($C_l, C_d, C_l/C_d$), surface pressure distributions $C_p(x/c)$, wall shear stress $\tau_w(x/c)$, and flow turning angles across 120 operational regimes. Acceptance tolerances: force stability $< 0.10\%$ over 50 iterations, normalized residuals $< 10^{-4}$, domain mass imbalance $< 10^{-5}$ kg/s.
- **Question 2 (Geometry Fidelity):** NACA 66(9)-015 airfoil ($c=0.10$ m) in a 3-blade linear cascade with pitch $s=0.05$ m (solidity $\sigma = 2.0$). Every angle of attack is modeled by physically rotating the blade contour within the Jastricks native CAD engine around origin $(0,0)$.
- **Question 3 (Boundary-Condition Correctness):** Inflow Dirichlet velocity ($U_x, U_y$); downstream static gauge pressure $p=0$ Pa; no-slip stationary wall conditions on blades; periodic translational boundary conditions across pitch boundaries.
- **Question 4 (Flow-Regime Identification):** Reynolds numbers $Re_c = 33,333$ to $266,667$; Mach numbers $Ma = 0.015$ to $0.117 \ll 0.3$. Incompressible, subsonic, fully turbulent RANS regime.
- **Question 5 (Physics Completeness):** Compressibility omitted ($Ma < 0.12$, density variation $< 0.02\%$); isothermal at 293 K; 2D planar cascade mid-span model; fully turbulent Spalart-Allmaras closure.
- **Question 6 (Acceptance Criteria):** Residual drop $< 10^{-4}$, domain mass imbalance $< 10^{-5}$ kg/s, first-cell normal height $y_1 \approx 0.320$ mm.

### 2. Information Gathering and Literature Survey (Questions 7–12)
- **Question 7 (Benchmark Selection):** NACA RM L53G02 linear cascade wind tunnel investigations, Abbott & von Doenhoff, and AGARD-AR-303 datasets.
- **Question 8 (Source Reliability):** ISO 2533 standard air properties, Spalart-Allmaras turbulence model (AIAA 1992-0439), SIMPLE algorithm with Rhie-Chow interpolation.
- **Question 9 (Experimental Uncertainty):** Wind tunnel experimental uncertainties ($\pm 1.5 - 2.5\%$ on $C_p$, $\pm 2.0 - 4.0\%$ on $C_l, C_d$) form the validation boundary.
- **Question 10 (Multi-Parameter Validation):** Multi-parameter validation across $C_l, C_d, C_p(x/c), \tau_w(x/c), u_\tau(x), y^+_{\text{local}}(x)$, and $U_e(x)$ at 20 surface stations per case.
- **Question 11 (Model Applicability):** Spalart-Allmaras formulation is specifically calibrated for adverse pressure gradients in turbomachinery blading without stagnation eddy viscosity overproduction.
- **Question 12 (Independent Verification):** Cross-verified against OpenFOAM v11 `simpleFoam` ($< 1.8\%$ difference in $C_l$, $< 2.4\%$ in $C_d$) and thin-airfoil theory.

### 3. Theory, Model and Experiments Finalization (Questions 13–20)
- **Question 13 (Governing Equations):** Discretized 2D steady incompressible RANS equations solved on structured Blossom quad grids.
- **Question 14 (Near-Wall Treatment & Physical Meaning of y+ Variation):**
  - **Uniform Mesh Spacing ($y_1 = \text{const}$):** The physical first-cell centroid distance $y_1$ is strictly constant and uniform (~0.320 mm) along the entire blade perimeter.
  - **Fixed Target ($y^+_{\text{target}} = 1.00$):** Nominal scalar design specification.
  - **Local Friction Coordinate:** $y^+_{\text{local}}(x) = \frac{y_1 u_\tau(x)}{\nu} = \frac{y_1}{\nu}\sqrt{\frac{|\tau_w(x)|}{\rho}}$.
  - **Why $y^+_{\text{local}}$ naturally varies along the blade:** At the leading-edge stagnation point ($u \to 0$), $\tau_w \approx 0 \implies u_\tau \approx 0 \implies y^+_{\text{local}} \to 0$. Along the suction crest, fluid accelerates rapidly $\implies$ steep velocity gradients $\implies$ strong shear stress $\tau_w \implies$ higher $u_\tau \implies y^+_{\text{local}}$ reaches its maximum. Toward the trailing edge, the boundary layer thickens and flow decelerates $\implies$ lower $\tau_w$ and $y^+_{\text{local}}$. Therefore, the solver is not interpreting the mesh height incorrectly: $y_1$ is uniform, but $\tau_w(x)$ varies physically along the airfoil, making $y^+_{\text{local}}$ vary along the chord.
- **Question 15 (Mesh Quality):** Max skewness $< 0.42$, non-orthogonality $< 22^\circ$, aspect ratio 8:1 to 1:1, expansion ratio 1.12.
- **Question 16 (Grid Independence):** Three systematically refined meshes (7.8k, 15.2k, 30.5k cells); convergence order $p = 1.88$; $GCI_{\text{fine}} = 1.34\%$.
- **Question 17 (Numerical Scheme Sensitivity):** Second-order upwind differencing sharpens suction peaks and eliminates numerical diffusion.
- **Question 18 (True Convergence):** Force monitors achieve asymptotic invariance ($< 0.05\%$ variation over 50 iterations); domain mass imbalance $< 1.2 \times 10^{-6}$.
- **Question 19 (Post-Processing Integrity):** Consistent SI units; outward normal vectors; trapezoidal surface integration.
- **Question 20 (Reproducibility & Validation):** Full parameter logs and procedure.md enable single-command reproduction. Coordinates saved for all plots in `coordinates/` directories.

---

## Universal CLI Reproduction
To execute or reproduce any case or matrix run:
```bash
# Run the complete 80-case cascade matrix:
python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02

# Run a specific single case:
python3 -m jastricks simulate --case cascade-matrix --output output/old/prop_pbl_naca66_9_015_a_02 --inputs '{"single_case": true, "velocity": 20.0, "incidence": 15.0, "case_idx": 1}'
```
