---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: "Part II overview, VMC1-VMC8, VMD1-VMD3"
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Part II is the benchmark study section of the Verification Manual. Where Part I verifies answers, Part II probes how element choice, mesh pattern, and mesh density change the answer, deliberately including improper modelling so the reader learns what bad discretisation looks like. An overview chapter sets out the study design, the test case format, how to run the inputs, the energy error norm, and a coverage index. Eleven benchmarks follow: VMC1 to VMC8 study convergence under mesh refinement or alternative element types; VMD1 to VMD3 study single-element performance under distorted shapes. Three analysis types appear: static, mode-frequency, transient. This slice also holds the part title pages for Parts I, III, and IV, plus the overview chapters for the NAFEMS benchmarks and the NRC piping benchmarks, whose test cases sit in neighbouring slices.

## Key ideas
- Some benchmark results look wrong on purpose: they are the expected solutions for the chosen element, mesh, and loading, given as guidance on analysis options (Hlp_V_CH2_1).
- VMD series tests individual element performance under distorted, irregular shapes; VMC series tests accuracy and convergence under increasing refinement or alternate element types (Hlp_V_CH2_2).
- Only three analysis types are used: static (ANTYPE,0), mode-frequency (ANTYPE,2), transient (ANTYPE,4) (Hlp_V_CH2_2).
- Fixed test case format: Overview, Test Case, Representative Mesh Options, Target Solution, Results Comparison (ratios of Mechanical APDL result over target), optional Graphical Results, then modelling comments (Hlp_V_CH2_3).
- Comparison locations are marked with a bull's-eye target point symbol, labelled TP-XX (Hlp_V_CH2_3).
- Each input runs either the single documented case (quick) or all cases for the problem; running all cases can consume long run times, disk, and memory (Hlp_V_CH2_4).
- The energy error norm is an a posteriori estimate of mesh discretisation error; its correlation to displacement or stress error is problem dependent, so it is a relative measure only (Hlp_V_CH2_5).
- Under uniform refinement the percent error in energy norm follows a log-log linear relation with model DOF (VMC2).
- The error norm can stay high at built-in edges where point-wise inaccuracy is expected, even when target-point displacement and stress are good (VMC1).
- Many elements through the plate thickness are needed to catch bending stress at a built-in edge with solid elements (VMC1).
- Trapezoidal distortion locks linear elements: in-plane shear tip displacement ratio falls to 0.052 (PLANE182) and 0.047 (SOLID185) at 45 degrees, while quadratic elements stay near 1 (VMD1).
- Distorted linear elements stiffen and overpredict the first bending frequency, up to ratio 2.254 for SOLID185 at 45 degree trapezoids; quadratics stay within about 5 percent (VMD3).
- Linear triangles from degenerated SHELL181 are too stiff under membrane plus bending; constant-strain membrane behaviour underpredicts displacement and stress, and their use is not recommended (VMC3).
- Repeated eigenvalues and rigid body modes are the specific test targets of the modal benchmarks (VMC4, VMC5).
- Lower order PLANE55 converges to the thermal solution from above; higher order PLANE35 and PLANE77 converge from below and give identical results in triangular form (VMC6).
- Benchmarks are drawn from NAFEMS specifications, literature proposals, and textbooks; conforming cases are identified (Hlp_V_CH2_2).

## Equations that matter
$$e_i = \frac{1}{2}\int_V \{\Delta\sigma\}^{T}[D]^{-1}\{\Delta\sigma\}\, dV$$
Error energy in element i: the nodal stress error (averaged minus unaveraged nodal stresses) weighted by the compliance matrix. Summed over elements, normalised against total energy (u + e), it gives the percent error in energy norm E. Unnumbered in the source (Hlp_V_CH2_5).

## Numbers worth citing
- VMC1 built-in plate (a = 10 in, t = 1 in, E = 1 x 10^7 psi, nu = 0.3, pressure 1000 psi): target UZ(1) = -0.0172 in, SX(2) = -32.124 ksi, SX(3) = 14.465 ksi from a 45708 DOF fine mesh at 10 percent error norm; approximate analytical solution neglecting shear deflection gives -0.0138 in, -30.780 ksi, 13.860 ksi (VMC1).
- VMC2 elliptic membrane (E = 210 x 10^3 MPa, nu = 0.3, t = 0.1 m, outward edge pressure 10 MPa): target tangential edge stress SY = 92.7 MPa at TP1 (VMC2).
- VMC3 barrel vault roof (E = 4.32 x 10^8 N/m^2, rho = 36.7347 kg/m^3, L = 50 m, R = 25 m, t = 0.25 m, theta = 40 deg, g = 9.8 m/s^2): target from Cook's 8-node shell, N = 8, 2310 DOF (VMC3); the same physical case in VMD2 states target UY = -0.3016, axial stress 358.42 kPa, hoop stress -213.40 kPa at the target points (VMD2).
- VMC4 annular plate (E = 200 x 10^9 N/m^2, rho = 8000 kg/m^3, a = 1.8 m, b = 6.0 m, t = 0.06 m): target frequencies modes 1 to 9 run 1.880 Hz to 18.942 Hz, with close pairs at 5.187/5.195 Hz and 9.784/9.791 Hz (VMC4).
- VMC5 solid square plate (10 m x 10 m x 1 m, same steel properties): modes 1 to 3 are rigid body at zero frequency; mode 4 = 45.897 Hz, modes 9 and 10 coincident at 206.19 Hz (VMC5).
- VMC6 2D conduction with convection (k = 52 W/m degC, h = 750 W/m^2 degC, T1 = 100 degC, T0 = 0 degC): converged temperature at TP1 reads 18.3 degC at temperature ratio 1.00 (VMC6).
- VMC7 semi-infinite solid (k = 54 W/m degC, rho = 7833 kg/m^3, c = 0.465 J/kg degC as printed, h = 50 W/m^2 degC, T1 = 1000 degC): target surface temperature 157.25 at 2 s (VMC7).
- VMC8 aluminium bar impact (E = 70 x 10^9 N/m^2, ET = 100 x 10^6 N/m^2, yield 420 x 10^6 N/m^2, rho = 2700 kg/m^3 as printed, bar 2.347 cm x 0.762 cm dia, V0 = 478 m/s): experimental target deformed length 0.01319 m; FE results 0.014 m, ratios 1.067 to 1.078; transient span 4.5 x 10^-5 s (VMC8).
- VMD1 cantilever (L = 6 in, d = 0.1 in, t = 0.2 in, E = 10 x 10^6 psi): unit tip loads; worst distorted linear result 0.030 out-of-plane shear ratio for SOLID185 trapezoid at 45 degrees (VMD1).
- VMD3 free-free beam (L = 12 m, 0.1 m x 0.2 m section, steel): targets 208.333 Hz axial, 7.138 Hz bending (VMD3).

## Definitions introduced
- Percent error in energy norm E - global error energy e normalised against total energy (u + e), u the strain energy; a relative measure of mesh accuracy (Hlp_V_CH2_5).
- Nodal stress error vector {Delta sigma} - averaged nodal stresses minus unaveraged nodal stresses (Hlp_V_CH2_5).
- Target point (TP-XX) - bull's-eye marked location where the Mechanical APDL and target solutions are compared (Hlp_V_CH2_3).
- VMCxx - benchmark series for solution accuracy and convergence under mesh refinement or alternate element types (Hlp_V_CH2_2).
- VMDxx - benchmark series for individual element performance under distorted, irregular shapes (Hlp_V_CH2_2).

## Figures and tables to return to
- Tables 1.1 to 1.4 - coverage index mapping each benchmark to plane, solid, shell, and thermal elements (Hlp_V_CH2Ind).
- Table 1.5 - analysis type per benchmark: static C1, C2, C3, C6, D1, D2; modal C4, C5, D3; transient C7, C8 (Hlp_V_CH2Ind).
- Table 24 - VMC1 convergence of SOLID185/186/187 against DOF and error norm (VMC1).
- Fig 588 - VMC1 representative mesh refinement sequence for the plate (VMC1).
- Fig 594 - VMC4 quadrilateral and triangle meshes at both densities (VMC4).
- Fig 597 - VMC5 mode shapes including the rigid body modes (VMC5).
- Figs 602, 603 - VMC8 deformed bar shape and time histories of tip displacement and plastic strain (VMC8).
- Results table vmd1.tab.3 - VMD1 full matrix of shape (rectangle, trapezoid, parallelogram) versus load and element, the reference table for distortion sensitivity (VMD1).
- VMD3 results table - first-frequency ratios for the same shape matrix under axial and bending modes (VMD3).

## Where to find what
| Item | What it is | Analysis type | Elements |
|---|---|---|---|
| Hlp_V_BENTOC.html | Part II title page, no content | n/a | n/a |
| Hlp_V_CH2_1.html | Benchmark overview: purpose, deliberate improper-use cases | n/a | n/a |
| Hlp_V_CH2_2.html | Study description: VMC/VMD split, analysis types, sources | n/a | lists PLANE35, PLANE55, PLANE77, PLANE182, PLANE183, SHELL63, SHELL181, SHELL281, SOLID70, SOLID186, SOLID187 |
| Hlp_V_CH2_3.html | Test case format and nomenclature, target point symbol | n/a | n/a |
| Hlp_V_CH2_4.html | Running the inputs: single case vs all cases | n/a | n/a |
| Hlp_V_CH2_5.html | Energy norm theory | n/a | n/a |
| Hlp_V_CH2Ind.html | Coverage index, Tables 1.1 to 1.5 | n/a | n/a |
| vm.testcases.html | Part I title page (verification test cases) | n/a | n/a |
| vm_nafems.html | Part III title page (NAFEMS benchmarks) | n/a | n/a |
| Hlp_V_CH4_1.html | NAFEMS overview: publications FEBSTA, LSB2, P09, R0027, R0029, R0038, R0049, R0031, R0020; NAFEMS contact | n/a | n/a |
| vm_nrcbench.html | Part IV title page (NRC piping benchmarks) | n/a | n/a |
| Hlp_V_ch5_1.html | NRC piping overview: NUREG/CR-1677 Vols 1 and 2, NUREG/CR-6645, EPIPE/SAP IV reference solutions, seismic response spectrum method | n/a | n/a |
| VMC1 | Built-in plate under uniform pressure, refinement and error norm (Timoshenko) | Static | SOLID185, SOLID186, SOLID187 |
| VMC2 | Elliptic membrane under outward pressure, quad vs triangle refinement (NAFEMS LE1 modified) | Static | PLANE182, PLANE183 |
| VMC3 | Barrel vault roof under self weight, refinement (Cook) | Static | SHELL181, SHELL281 |
| VMC4 | Thin annular plate, first nine frequencies, repeated eigenvalues (NAFEMS Test 14 modified); needs vmc4-1.cdb to vmc4-6.cdb | Modal, Block Lanczos | SHELL181, SHELL281 |
| VMC5 | Solid square plate, 10 modes with 3 rigid body (NAFEMS FV52 modified) | Modal, Block Lanczos | SOLID185, SOLID187 |
| VMC6 | 2D steady conduction with convection edges (NAFEMS T4 modified) | Thermal static | PLANE35, PLANE55, PLANE77 |
| VMC7 | 1D transient conduction, semi-infinite solid, time step optimisation (Holman) | Thermal transient | PLANE35, PLANE55, PLANE77 |
| VMC8 | Aluminium bar impact on rigid wall, axisymmetric plasticity (Wilkins and Guinan) | Nonlinear transient dynamic | PLANE182, PLANE183 |
| VMD1 | Straight cantilever under unit loads, distorted element shapes (MacNeal and Harder) | Static | PLANE182, PLANE183, SOLID185, SOLID186, SOLID187 |
| VMD2 | Barrel vault roof with skewed meshes, companion to VMC3 (Cook) | Static | SHELL181, SHELL281 |
| VMD3 | Free-free beam, axial and bending frequencies vs element distortion (Blevins) | Modal, Block Lanczos | PLANE182, PLANE183, SOLID185, SOLID186, SOLID187 |

## Links
[[Finite element method]], [[Mesh convergence]], [[Energy error norm]], [[Element distortion]], [[Shell elements]], [[Plate bending]], [[Modal analysis]], [[Transient heat conduction]], [[NAFEMS benchmarks]], [[NRC piping benchmarks]], [[Ansys Mechanical APDL]]

## Flags
- Input listing files exist but were excluded from this slice by instruction: vm.nafems.input.html, vm.nrcbenchmarks.input.html, and all files ending txt.html (per-benchmark data input listings such as vmc1.dat pages).
- Legacy element type numbers persist in results tables while the prose uses current names: ETYP 95 and 35 in the VMC1 target and shell tables against SOLID186/SHELL281 in the text (VMC1); ETYP 2 in the VMC8 results table (VMC8); PLANE82 named in a VMC2 solution comment (VMC2).
- Suspected unit inconsistency: the VMC3 target table prints UY(1) 3016 under a header labelled metres with stresses 358,420 and -213,400 unlabelled, while VMD2 prints the same case as UY -0.3016 with stresses 358.42 and -213.40 kPa, under a header "UY (1), in" for a metric model (VMC3, VMD2).
- VMC3 states nu = 0.3 but companion VMD2 states nu = 0.0 for the same roof (VMC3, VMD2).
- VMC6 has no explicitly stated target value; the converged value 18.3 degC is inferred only from ratio 1.00 rows, and the results table heading says "Triangle Mesh" while containing quadrilateral, triangle, and uniform triangle sections (VMC6).
- Suspected errata: VMC7 specific heat printed as 0.465 J/kg degC (VMC7); VMC8 density printed as "2700 Kq/m3" (VMC8).
- The defining expression for percent error in energy norm E is announced with a colon in the text but no equation renders in this HTML build; inline equation graphics in VMC8 (bar length symbol, elastic wave speed) are external SVGs not captured here (Hlp_V_CH2_5, VMC8).
- SHELL63 and SOLID70 are named in the overview element list but no Part II benchmark exercises them per the coverage index (Hlp_V_CH2_2, Hlp_V_CH2Ind).
- VMD1 lists PLANE183 twice in its element table, as 8-node and as 6-node triangular form (VMD1).
- Continuations in neighbouring slices: Hlp_V_CH4_1 leads into the NAFEMS test cases (VMFEBSTA-LE1 onward); Hlp_V_ch5_1 leads into the NRC piping benchmark chapter (vm.ch5.pipben.html); the VMR083 series sits between Parts III and IV per the navigation links (Hlp_V_CH4_1, Hlp_V_ch5_1, vm_nrcbench.html).
