---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: NRC piping and miscellaneous benchmarks
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
This slice spans two parts of the manual. Five files form the head of Part IV, NRC Piping Benchmarks: two overview sections explain that every NRC piping benchmark is run twice, once with the archived pipe elements PIPE16 and PIPE18 verified against the NRC benchmark solutions, and once with the current elements PIPE289 and ELBOW290, whose results are deliberately not compared with the NUREG numbers because those came from a 1959-era flexibility factor program rather than analytical solutions. Three demonstration problems then quantify the gap by comparing both pipe element generations against a SHELL281 shell reference model in modal plus single point response spectrum analyses. The remaining twelve files are compact NAFEMS-derived tests from Part III: two linear elastic statics cases (FEBSTA-LE1, LE5), three axisymmetric pressure and thermal statics cases (LSB2-LE8, LE9, LE11), and seven free-vibration frequency checks (P09-T2 to T52) covering beam, shell, plane and solid elements, each ending in a short table of Mechanical APDL results against NAFEMS targets with a ratio per mode or stress point.

## Key ideas
- The NRC piping benchmark set runs in two element generations: archived PIPE16/PIPE18 verified against NRC benchmark solutions, and current PIPE289/ELBOW290 (vm.ch5.pipben.html, vmnmrc_pipbencur.html).
- Current-technology results are not compared with NUREG results: the NUREG program used a flexibility factor method, not analytical calculation (vmnmrc_pipbencur.html).
- The ELBOW command converts straight PIPE289 elements near bends into ELBOW290 to carry ovalization across the joint; meshes keep the subtended angle per ELBOW290 element at or below 45 degrees (vmnmrc_pipbencur.html).
- Three demonstration problems benchmark both pipe generations against a SHELL281 shell model of the same pipework (vmnmrc_pipbencur.html).
- Demonstration Problem 1, a thin cantilevered bend with outer radius to wall thickness ratio 45.36: ELBOW290 frequencies match SHELL281 to within 0.1 percent, PIPE18 is off by more than 50 percent (vnmr_prob1).
- Demonstration Problem 2, straight and bend pipe between fixed anchors: PIPE16/18 lower modes sit within 5 percent, higher modes drift past 30 percent, yet spectrum results stay close because only the lower modes contribute (vnmr_prob2).
- Demonstration Problem 3, a 3.5 inch water line with two anchors and many supports: all three modelling routes agree within a few percent on frequencies, displacement and stress (vnmr_prob3).
- ELBOW290 can constrain end cross-section deformation (warping, ovalization, radial expansion, shell normal rotations) that PIPE289 cannot, which is why the end elements of Demonstration Problem 3 use it (vnmr_prob3).
- CONTA175 and TARGE170 tie the COMBIN14 spring-damper supports to the SHELL281 reference model in Demonstration Problem 3 (vnmr_prob3).
- The NAFEMS statics tests each reduce to one stress component at a named point with a ratio to the NAFEMS target (VMFEBSTA-LE1, VMFEBSTA-LE5, VMLSB2-LE8, VMLSB2-LE9, VMLSB2-LE11).
- In the VMP09 vibration set, low-order elements drift furthest: SHELL181 reaches 16 percent above target on the clamped rhombic plate where SHELL281 stays within 0.5 percent (vmp09t15), and SOLID185 reaches 13 percent above target on the solid square plate (vmp09t52).
- All VMP09 tests share one material: $E = 200\times10^{9}\ \mathrm{N/m^2}$, $\rho = 8000\ \mathrm{kg/m^3}$, $\nu = 0.3$ (vmp09t2 to vmp09t52).

## Equations that matter
The source numbers no equations; the tag carries the benchmark ID instead.

$$\left(\tfrac{x}{2}\right)^2 + y^2 = 1, \qquad \left(\tfrac{x}{3.25}\right)^2 + \left(\tfrac{y}{2.75}\right)^2 = 1 \tag{VMFEBSTA-LE1}$$
Inner curve AD and pressure-loaded outer curve BC of the elliptical membrane, coordinates in metres.

$$T = \left(x^2 + y^2\right)^{1/2} + z \tag{VMLSB2-LE11}$$
Imposed temperature field in degrees Celsius: a linear gradient in radius and height that drives the thermal stress check.

## Numbers worth citing
Results tables state no units for frequencies or stresses; values below are as printed.
- Demo 1 pipe: outer diameter 10.932 in, wall 0.1205 in, bend radius 36.30 in; $E = 24\times10^{6}$ psi, $\rho = 1.25\times10^{-4}\ \mathrm{lb\,s^2/in^4}$, $\nu = 0.3$ (vnmr_prob1).
- Demo 1 mode 1: SHELL281 145.554 vs PIPE18 90.588 (ratio 1.606); ELBOW290 145.641 (Table 1.1, vnmr_prob1).
- Demo 1 spectrum maxima: equivalent stress 33.144 (SHELL281), 41.915 (PIPE18), 27.633 (ELBOW290); displacement vector sum $4.99\times10^{-4}$ vs $1.23\times10^{-3}$ (PIPE18) (Table 1.2, vnmr_prob1).
- Demo 2 pipe: wall 0.241 in, otherwise Demo 1 material and diameters; mode 1 45.457 (SHELL281) vs 44.673 (PIPE16/18); spectrum stress 147.522 / 147.736 / 160.106 for A/B/C (Tables 1.3, 1.4, vnmr_prob2).
- Demo 3 material: $E = 0.258\times10^{8}$ psi, $G = 0.992\times10^{7}$ psi; support spring stiffness $0.2\times10^{8}$ lb/in (set 1, UX/UY/UZ) and $0.2\times10^{5}$ lb/in (set 2, UX/UY); pipe 3.5 in outer diameter, wall 0.216 in, bend radius 48.003 in (vnmr_prob3).
- Demo 3 results: mode 1 5.989 (SHELL281); spectrum stress 2400.901 / 2250.316 / 2446.53; displacement 0.134 / 0.131 / 0.135 for A/B/C (Tables 1.5, 1.6, vnmr_prob3).
- NAFEMS statics common material: $E = 210\times10^{3}$ MPa, $\nu = 0.3$ (VMFEBSTA-LE1 to VMLSB2-LE11).
- VMFEBSTA-LE1: SYY at C = 93.026 (SHELL181, ratio 1.004) under 10 MPa outward pressure on BC, thickness 0.1 m.
- VMFEBSTA-LE5: SXX at A = -111.204 (SHELL181, ratio 1.030) and -116.124 (SHELL281, ratio 1.075) under 1.2 MN m end torque as two 0.6 MN edge shears.
- VMLSB2-LE8: SZ at D = 91.348 (SHELL208, ratio 0.966), 90.548 (SHELL209, ratio 0.958), internal pressure 1 MPa, thickness 0.01 m.
- VMLSB2-LE9: SYY at C = -304.509 (SHELL208, ratio 0.952), -304.151 (SHELL209, ratio 0.951), 1 MPa over edge BCD.
- VMLSB2-LE11: SZZ at A = -102.082 (SOLID185, ratio 0.972), -103.268 (SOLID186, ratio 0.984), thermal expansion coefficient $2.3\times10^{-4}$ per degree C.
- VMP09-T2: mode 1 = 11.3308, ratio 0.9995, identical for BEAM188 and BEAM189.
- VMP09-T4: point masses 10000 kg and 1000 kg; mode 1 = 1.7198 (BEAM188, ratio 0.9982).
- VMP09-T5: modes 1,2 = 42.730 (BEAM188, ratio 1.0019); 42.634 (BEAM189, ratio 0.9996), beam length 10 m.
- VMP09-T12: mode 4 = 1.632 (SHELL181, ratio 1.0060), 1.620 (SHELL281, ratio 0.9988); results reported for modes 4 to 10.
- VMP09-T15: mode 5 ratio 1.1643 for SHELL181 against 1.0041 for SHELL281 on the same plate.
- VMP09-T33: modes 4,5 = 137.164 (PLANE182, ratio 1.061), 125.834 (PLANE183, ratio 0.974), annulus radii 1.8 m and 6 m.
- VMP09-T52: mode 4 spans 43.837 (SOLID186) to 48.925 (SOLID185) across five element types.

## Definitions introduced
- Archived elements - legacy pipe elements PIPE16 and PIPE18, retained for the first benchmark set (vm.ch5.pipben.html).
- Current technology elements - PIPE289 for straight runs and ELBOW290 for bends (vmnmrc_pipbencur.html).
- PIPE289 - extended Timoshenko beam theory with pipe wall expansion degrees of freedom; supports plane stress (thin pipe) and 3D stress (thick pipe) states (vmnmrc_pipbencur.html).
- ELBOW290 - 3D finite-strain shell theory with Fourier-series cross-section deformation: non-uniform radial expansion, ovalization, warping (vmnmrc_pipbencur.html).
- Flexibility factor method - the 1959-published bend correction behind PIPE18 and the NUREG reference program (vmnmrc_pipbencur.html).
- ELBOW command - automatic conversion of straight PIPE289 elements near bends into ELBOW290 (vmnmrc_pipbencur.html).

## Figures and tables to return to
- Tables 1.1, 1.3, 1.5 - fifteen-mode frequency comparisons, SHELL281 vs PIPE16/18 vs ELBOW290, one per demonstration problem (vnmr_prob1, vnmr_prob2, vnmr_prob3).
- Tables 1.2, 1.4, 1.6 - spectrum displacement and equivalent stress comparisons for the same three models (vnmr_prob1, vnmr_prob2, vnmr_prob3).
- Figures 1.1 to 1.9 - nodal equivalent stress plots, three per demonstration problem, one per element technology (vnmr_prob1, vnmr_prob2, vnmr_prob3).
- Figures 607, 608, 609 - problem sketches for VMLSB2-LE8, LE9 and LE11; the geometry for these tests lives only in the sketch, the text says "refer to figure" (vmlsb2le8, vmlsb2le9, vmlsb2le11).

## Where to find what
| Benchmark | Title | Analysis type | Elements | Reference |
| --- | --- | --- | --- | --- |
| Ch 1.1 (vm.ch5.pipben.html) | Piping Benchmarks Using Archived Elements | overview, no test | PIPE16, PIPE18 | NRC benchmark solutions (citation not stated) |
| Ch 1.2 (vmnmrc_pipbencur.html) | Piping Benchmarks using Current Technology Elements | overview, no test | PIPE289, ELBOW290 | NUREG (deliberately not compared) |
| Demo 1 (vnmr_prob1.html) | Cantilevered bend pipe, radius to thickness 45.36 | modal + single point response spectrum | PIPE18; ELBOW290; SHELL281 | not stated (element cross-comparison) |
| Demo 2 (vnmr_prob2.html) | Straight and bend pipe between two fixed anchors | modal + single point response spectrum | PIPE16, PIPE18; ELBOW290; SHELL281 | similar to NRC1677 Vol 1 Problem 1 |
| Demo 3 (vnmr_prob3.html) | 3.5 in water line, two anchors, intermediate supports | modal + single point response spectrum | PIPE16, PIPE18; PIPE289, ELBOW290; SHELL281; COMBIN14; CONTA175; TARGE170 | NRC 1677 Vol 2 Problem 1 |
| VMFEBSTA-LE1 | Linear Elastic Analysis on an Elliptical Membrane | linear elastic static | SHELL181 | NAFEMS manual (edition not stated) |
| VMFEBSTA-LE5 | Linear Elastic Analysis on a Z-Section Cantilevered Plate | linear elastic static | SHELL181, SHELL281 | NAFEMS manual |
| VMLSB2-LE8 | Linear Elastic Axisymmetric Shell with Pressure Loading | linear elastic static | SHELL208, SHELL209 | NAFEMS manual |
| VMLSB2-LE9 | Linear Elastic Axisymmetric Branched Shell with Pressure Loading | linear elastic static | SHELL208, SHELL209 | NAFEMS manual |
| VMLSB2-LE11 | titled as LE8; body is an axisymmetric solid under thermal load | linear elastic static, thermal | SOLID185, SOLID186 | NAFEMS manual |
| VMP09-T2 | Pin-Ended Double Cross: In-Plane Vibration | frequency (modal) | BEAM188, BEAM189 | NAFEMS manual |
| VMP09-T4 | Cantilever with Off-Center Point Masses | frequency (modal) | BEAM188, BEAM189 | NAFEMS manual |
| VMP09-T5 | Deep Simply-Supported Beam | frequency (modal) | BEAM188, BEAM189 | NAFEMS manual |
| VMP09-T12 | Free Thin Square Plate | frequency (modal) | SHELL181, SHELL281 | NAFEMS manual |
| VMP09-T15 | Clamped Thin Rhombic Plate | frequency (modal) | SHELL181, SHELL281 | NAFEMS manual |
| VMP09-T33 | Free Annular Membrane | frequency (modal) | PLANE182, PLANE183 | NAFEMS manual |
| VMP09-T52 | Simply-Supported 'Solid' Square Plate | frequency (modal) | SHELL181, SOLID185, SOLID186, SOLID187, SHELL281 | NAFEMS manual |

## Links
[[Ansys Mechanical APDL]], [[Finite element verification]], [[Modal analysis]], [[Response spectrum analysis]], [[Piping vibration]], [[Pipe elements]], [[Shell elements]], [[NAFEMS benchmarks]]

## Flags
- Input listings ending txt.html exist but were not read (per instruction). They belong to: Demo 1 (demonstration-problem1-290/-281/-18), Demo 2 (demonstration-problem2-290/-281/-16-18), Demo 3 (demonstration-problem3-281/-16-18, demonstration_problem3-289-290), VMFEBSTA-LE1 (181 plus a .cdb), VMFEBSTA-LE5 (181, 281), VMLSB2-LE8 and LE9 (208, 209), VMLSB2-LE11 (185, 186), VMP09-T2/T4/T5 (188, 189), VMP09-T12/T15 (181, 281), VMP09-T33 (182, 183), VMP09-T52 (181, 185, 186, 187, 281). The vm-nr1677 series listings in the same folder belong to the neighbouring NRC series slice.
- Suspected erratum: Demo 2 Table 1.4 prints displacement ratio A/B as 1.106, but the tabulated values $5.65\times10^{-3}$ and $5.72\times10^{-3}$ give 0.988 (vnmr_prob2).
- VMLSB2-LE11 carries the same title as LE8 ("Axisymmetric Shell with Pressure Loading") while the body describes an axisymmetric solid under thermal load with no pressure; suspected title slip.
- VMP09-T4: the text says the beam is constrained in all DOF at the left end, but the boundary condition table applies the six constraints at the right beam endpoint; the two statements conflict.
- VMP09-T52: the text gives length and width 10 m with height 1 m, the table gives L = H = 10 m with W = 1 m; the labels conflict.
- VMFEBSTA-LE1 requires a supplemental .cdb file from the VM2024R2_MAPDL.zip download, with geometry and mesh regenerated, before the case runs.
- Results tables state no units anywhere in the slice; frequencies and stresses are bare numbers.
- Cross-references into neighbouring slices: the two overview sections index VM-NR1677-01-1 to -7, VM-NR1677-02-1 to -4 and VM-NR6645-01-1 (current) plus the same IDs with -a suffix (archived), all handled in the NRC series slice; VMFEBSTA-LE1 follows the NAFEMS overview (Hlp_V_CH4_1.html) and VMP09-T52 precedes VMR020-t1a, both in neighbouring slices.
- Slice straddles two parts of the manual: the five NRC files sit in Part IV Chapter 1; the twelve VMFEBSTA/VMLSB2/VMP09 files sit in Part III, NAFEMS Benchmarks.
