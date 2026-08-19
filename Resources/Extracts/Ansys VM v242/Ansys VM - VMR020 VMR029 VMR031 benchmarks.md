---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VMR020, VMR029, VMR031 benchmarks
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Twenty-one benchmark description pages from the NAFEMS Benchmarks part of the manual (each page carries the header "Part III: NAFEMS Benchmarks"). Three families: VMR020, thirteen 2-D fracture tests on cracked plates, bars and specimens, each reporting a stress intensity factor and a J integral normalised against the NAFEMS target; VMR029, five geometric non-linearity tests (large deflection cantilevers, lateral torsional buckling, shell limit loads, pinched hemisphere) run across multiple element types; VMR031, three composite tests (laminated strip bending, wrapped cylinder under pressure and heat, sandwich plate under pressure). Every page has the same anatomy: short test description, a properties and loading table, a results table giving the Mechanical APDL value and its ratio to the NAFEMS reference, and links to input listings. Each result names its input file, so the page also serves as a map from benchmark to runnable deck.

## Key ideas
- Centre cracked plate, plane strain, 100 MPa tension, quarter model: SIF 1.333 (ratio 1.006), J 1.335 (1.007) (VMR020-T1A).
- Same plate family under a quadratic thermal distribution, 0 to 100 degrees C, with $\alpha = 1.35\times10^{-5}$ per degree C: SIF 1.010 (1.010), J 1.000 (1.000) (VMR020-T1B).
- Single edge cracked plate, 100 MPa tension: SIF 2.966 (0.989), J 2.965 (0.988) (VMR020-T2A).
- Single edge cracked plate driven by a 0.01 mm uniform normal displacement instead of stress: SIF 1.027 (0.988), J 1.029 (0.989) (VMR020-T2B).
- Embedded angle crack at 22.5 degrees to the vertical, full geometry, mixed mode: $K_I$ 0.186 (0.979), $K_{II}$ 0.405 (1.000) (VMR020-T3A).
- Same crack at 67.5 degrees: $K_I$ 1.057 (1.026), $K_{II}$ 0.375 (1.013) (VMR020-T3B).
- Same crack at 90 degrees, which reduces to a pure mode I case: SIF 1.214 (1.011), J 1.213 (1.011) (VMR020-T3C).
- Crack at a hole, plane stress: SIF 1.087 (1.035), J 1.083 (1.031) (VMR020-T4A).
- Identical geometry in plane strain gives near-identical numbers: SIF 1.087 (1.036), J 1.083 (1.032) (VMR020-T4B).
- Circumferentially cracked round bar, axisymmetric elements: SIF 0.521 (1.096); J with plane stress formulation 0.463 (0.975); J with plane strain formulation 0.486 (1.022) (VMR020-T5).
- Compact tension specimen, 1000 N point load, half model: SIF 9.666 (1.001), J 9.637 (0.998) (VMR020-T6).
- V-notch cracked plate, 100 MPa normal stress: SIF 2.798 (1.021), J 2.809 (1.025) (VMR020-T8A).
- V-notch plate driven by 0.1 mm normal displacement: SIF 3.193 (0.990), J 3.224 (0.999) (VMR020-T8B).
- Z-shaped cantilever, elastic large deflection under end load 4000: tip deflection 142.62 to 144.14 across SHELL181, SOLID185, BEAM188, BEAM189, SOLSH190 and SHELL281, ratios 0.99 to 1.00 (VMR029-T1).
- Lateral torsional buckling of a thin cantilever, conservative and follower loads via arc-length: PCR 0.01888 to 0.02002 across the same six element types, ratios 0.9979 to 1.0583 (VMR029-T4).
- Curved 45 degree cantilever, radius 100, transverse end load 3000: BEAM188 tip displacements UX 24.9916, UY 47.6258, UZ 68.4150, ratios 1.0009 to 1.0067; SOLID185, BEAM189 and SOLSH190 also run (VMR029-T5).
- Hinged spherical shell panel under uniform pressure, mid-surface $Z = 2.0285\times10^{-4}\,[X(1570-X)+Y(1570-Y)]$: two limit loads per element, LIMIT1 0.05277 to 0.05985 and LIMIT2 0.02868 to 0.03423, ratios 0.81 to 1.11 (VMR029-T7).
- Pinched hemispherical shell, R 10, t 0.04, loads 100 inward and outward on symmetry planes: node A displacement -5.66 to -5.90, node B 3.31 to 3.41, ratios 0.959 to 1.000 (VMR029-T9).
- Seven-layer laminated strip [0/90/0/90/0/90/0], central ply four times the others, three-point bending with a 10 N/mm line load: deflection -1.117 mm (1.054), bending stress 690.361 MPa (1.009) (VMR031-T1).
- Isotropic cylinder with orthotropic hoop windings, 200 MPa internal pressure alone (Case 1) and with a 130 degree C uniform rise (Case 2): eight hoop stress checks, ratios 0.978 to 1.036 (VMR031-T2).
- Square sandwich plate, 10 inch side, 100 psi pressure, quarter model, run in both SHELL281 and SHELL181: deflection -0.122 (0.993 both), stresses within 0.954 to 0.985 of target (VMR031-T3).

## Numbers worth citing
- VMR020 common material: E = 207000 MPa, $\nu$ = 0.3; applied stress 100 MPa where stress loaded (VMR020-T1A and throughout the family).
- VMR020-T1B adds $\alpha = 1.35\times10^{-5}$ per degree C for the thermal case (VMR020-T1B).
- VMR020 SIF and J values are printed without units, "tabulated and displayed as in the NAFEMS manual" (VMR020-T1A).
- VMR029 uses a consistent unit-free set: T1 E = $2.0\times10^{5}$, $\nu$ = 0.3, load 4000; T4 E = $1.0\times10^{4}$, G = $0.5\times10^{4}$; T5 E = $1.0\times10^{7}$, G = $0.5\times10^{7}$, load 3000; T7 E = 69, $\nu$ = 0.3, pressure 0.1; T9 E = $6.825\times10^{7}$, $\nu$ = 0.3, load 100 (VMR029-T1, VMR029-T4, VMR029-T5, VMR029-T7, VMR029-T9).
- VMR031-T1 laminate: $E_1$ = $1.0\times10^{5}$ MPa, $E_2$ = $5\times10^{3}$ MPa, $\nu_{12}$ = 0.4, $G_{12}$ = $3\times10^{3}$ MPa, $\nu_{23}$ = 0.3, $G_{13} = G_{23}$ = $2\times10^{3}$ MPa; strip 50 mm by 10 mm by 1 mm, supports at x = 10 mm and 45 mm (VMR031-T1).
- VMR031-T2 inner cylinder (isotropic): E = $2.1\times10^{5}$ MPa, $\nu$ = 0.3, $\alpha$ = $2\times10^{-5}$ per degree C, radii 23 to 25 mm; outer windings (orthotropic): $E_1$ = $1.3\times10^{5}$ MPa, $E_2$ = $5.0\times10^{3}$ MPa, $\nu_{12}$ = 0.25, $G_{12}$ = $1.0\times10^{4}$ MPa, $G_{33}$ = $5.0\times10^{3}$ MPa, $\alpha_1$ = $3\times10^{-6}$, $\alpha_2$ = $2\times10^{-5}$ per degree C, radii 25 to 27 mm (VMR031-T2).
- VMR031-T2 Case 1 hoop stresses: 1531.227 and 1437.434 (inner cylinder at r = 23 and 25 mm), 861.226 and 781.121 (outer at 25 and 27 mm); Case 2: 1372.696, 1258.668, 1045.695, 969.466 (VMR031-T2).
- VMR031-T3 sandwich: faces $E_x$ = $10.0\times10^{6}$ psi, $E_y$ = $4.0\times10^{6}$ psi, $\nu_{xy}$ = 0.3, $G_{xy}$ = $1.875\times10^{6}$ psi; core $E_x$ = 0, $G_{xz}$ = $3.0\times10^{4}$ psi, $G_{yz}$ = $1.2\times10^{4}$ psi; SHELL281 results $\sigma_{xx}$ 33752.207, $\sigma_{yy}$ 13143.214, $\tau_{xy}$ -4982.367 at 100 psi pressure (VMR031-T3).

## Definitions introduced
- b - plate width; a - crack length; h - plate height, given as ratios a/b and h/b per test (VMR020-T1A).
- $\beta$ - angle of the inclined crack measured from the vertical axis (VMR020-T3A).
- R - radius of the hole (VMR020-T4A); radius of the bar, with b redefined as the bar ligament width (VMR020-T5).
- W - specimen width; d - depth of the v-notch, with a/d, d/W and h/W ratios (VMR020-T8A).

## Figures and tables to return to
- Table 26 - VMR031-T3 SHELL281 results: deflection and all three stress components with ratios (VMR031-T3).
- Table 27 - VMR031-T3 SHELL181 results, the direct lower-order comparison to Table 26 (VMR031-T3).
- Unnumbered results tables on every other page pair each Mechanical APDL value with its ratio and input file name; the properties and loading table on each page is the complete model specification (VMR020-T1A).

## Where to find what
| Test | Title | Analysis type | Elements | Reference |
|---|---|---|---|---|
| VMR020-T1A | Center Cracked Plate in Tension | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T1B | Center Cracked Plate with Quadratic Thermal Distribution | 2-D thermal fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T2A | Single Edge Cracked Plate Subjected to Uniform Tensile Stress | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T2B | Single Edge Cracked Plate Subjected to Uniform Normal Displacement | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T3A | An Angle Crack Embedded in a Plate Subjected to Uniaxial Tension (22.5 deg) | 2-D mixed-mode fracture, $K_I$ and $K_{II}$ | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T3B | An Angle Crack Embedded in a Plate Subjected to Uniaxial Tension (67.5 deg) | 2-D mixed-mode fracture, $K_I$ and $K_{II}$ | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T3C | An Angle Crack Embedded in a Plate Subjected to Uniaxial Tension (90 deg) | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T4A | Crack at a Hole in a Plate Subjected to Uniaxial Tension | 2-D fracture, SIF and J | Plane stress (-183 input) | NAFEMS manual |
| VMR020-T4B | Crack at a Hole in a Plate Subjected to Uniaxial Tension | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T5 | Axisymmetric Crack in a Bar | Axisymmetric fracture, SIF and J | Axisymmetric (-183 input) | NAFEMS manual |
| VMR020-T6 | Compact Tension Specimen | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T8A | V-Notch Cracked Plate Subjected to Uniform Tensile Stress | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR020-T8B | V-Notch Cracked Plate Subjected to Uniform Normal Displacement | 2-D fracture, SIF and J | Plane strain (-183 input) | NAFEMS manual |
| VMR029-T1 | Elastic Large Deflection Response of a Z-Shaped Cantilever, Upper End Load | Elastic large deflection | SHELL181, SOLID185, BEAM188, BEAM189, SOLSH190, SHELL281 | NAFEMS manual |
| VMR029-T4 | Lateral Torsional Buckling of an Elastic Cantilever, Transverse End Load | Buckling, arc-length, conservative and follower loads | SHELL181, SOLID185, BEAM188, BEAM189, SOLSH190, SHELL281 | NAFEMS manual |
| VMR029-T5 | Large Deflection of a Curved Elastic Cantilever under Transverse End Load | Elastic large deflection | SOLID185, BEAM188, BEAM189, SOLSH190 | NAFEMS manual |
| VMR029-T7 | Large Displacement of a Hinged Spherical Shell under Uniform Pressure Loading | Elastic large deflection, limit loads | SHELL181, SOLID185, SOLSH190, SHELL281 | NAFEMS manual |
| VMR029-T9 | Large Elastic Deflection of a Pinched Hemispherical Shell | Elastic large deflection | SHELL181, SOLID185, SOLSH190, SHELL281 | NAFEMS manual |
| VMR031-T1 | Laminated Strip under Three-Point Bending | Laminate static bending | -281 input | NAFEMS manual |
| VMR031-T2 | Wrapped Thick Cylinder under Pressure and Thermal Loading | Composite static, pressure and thermal, two cases | -281 input | NAFEMS manual |
| VMR031-T3 | Three-Layer Sandwich Shell under Normal Pressure Loading | Sandwich plate static bending | SHELL281, SHELL181 | NAFEMS manual |

## Links
[[Fracture mechanics]], [[Stress intensity factor]], [[J integral]], [[Plane strain]], [[Large deflection]], [[Buckling]], [[Arc-length method]], [[Shell elements]], [[Composite laminates]], [[Sandwich panels]], [[NAFEMS benchmarks]], [[Ansys Mechanical APDL]], [[Finite element verification]]

## Flags
- Input listing pages (files ending txt.html) exist for every test in this slice; per instruction they were not read.
- File and label swap in the T3 pair: the file VMR020t3b.html holds the benchmark titled VMR020-T3C (crack at 90 degrees) and VMR020t3c.html holds VMR020-T3B (67.5 degrees). Inside each, the results-table test name and the input-file link are crossed: the T3C page tabulates against "vmr020-t3b-183" while linking input vmr020-t3c-183, and vice versa (VMR020-T3B, VMR020-T3C).
- Suspected erratum: E printed as 207000000 MPa in both V-notch tests where the rest of the family uses 207000 MPa (VMR020-T8A, VMR020-T8B).
- Suspected erratum: SOLID185 UX ratio printed as 1.9810 against value 24.4964, while the neighbouring elements give about 25.0 at ratio near 1.00 (VMR029-T5).
- Suspected erratum: the Case 2 results list "Outer cylinder at r = 23 mm" for both outer rows; Case 1 uses 25 mm and 27 mm for those positions (VMR031-T2).
- Supplemental .cdb files are required and must be downloaded from the 2024 R2 test case archive: vmr020-t1a-183-1.cdb and -2.cdb (VMR020-T1A); vmr029-t4-190.cdb and vmr029-t4-281.cdb (VMR029-T4).
- No VMR020-T7 page exists in this build; the sequence jumps from T6 to T8A (VMR020-T6).
- VMR029 and the VMR020 normalised results carry no units; VMR031-T2 hoop stresses and VMR031-T3 stresses are printed without units, with loading given in MPa and psi respectively (VMR029-T1, VMR031-T2, VMR031-T3).
- Recurring source typos: column heading "Geometic Properties" throughout, "Loaading" (VMR031-T2), and a garbled symmetry sentence "Symmetry is approximately =25mm and y=5mm" (VMR031-T1).
- Cross-references into neighbouring slices: page navigation runs VMP09-T52 into VMR020-T1A (NAFEMS slice), VMR020-T8B into VMR027-3A, VMR027-12C into VMR029-T1, and VMR031-T3 into VMR049-CR1 (VMR027 and VMR049 handled by other agents); all pages sit under the Part III NAFEMS Benchmarks landing page vm_nafems.html.
