---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM181-VM210
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification test cases, each a small model checked against a published or classical reference solution. Every case follows the same template: overview (reference, analysis type, element types, input listing), test case statement, modelling notes, then a results table of target versus Mechanical APDL with a ratio. The slice spans structural statics and element cross-checks (VM184, VM187, VM210), spring-mass dynamics (VM182, VM183), plates and shells (VM181, VM202, VM203), low-frequency electromagnetics and coils (VM185, VM186, VM188, VM190, VM206, VM207), circuits (VM208), contact (VM191, VM201), rubber and viscoelasticity (VM189, VM200, VM201, VM209), plasticity at large strain (VM198), fracture by XFEM (VM193), rotordynamics and bearings (VM197, VM199), geomechanics (VM205), radiation cooling (VM192), element birth/death (VM194), mechanisms (VM195), inertia relief and substructuring (VM196), and one pure solid-modelling Boolean check (VM204).

## Key ideas
- Deliberately small models: a whole steel billet is one SOLID70 element with SURF152 radiation faces sharing one extra node for the surroundings (VM192).
- Skin-effect conductors use coupled VOLT plus AZ degrees of freedom; coupling all VOLT DOF enforces a single source current density, so the current can be applied at any one node (VM185).
- PLANE13 can output eddy, source and total current; PLANE233 outputs total current only (VM186).
- The cantilever and curved-beam benchmarks are each solved four ways to cross-check SOLID5, SOLID92, SOLID98 and SOLID187 on identical problems (VM184, VM187).
- Bergstrom-Boyce rubber viscoelasticity enters by TB,BB; stresses are harvested per load step with *GET in POST1 (VM189).
- An iron core linked by a coil with no air gap is a multiply connected domain and forces the Generalized Scalar Potential three-solution MAGOPT sequence (VM190).
- Contact benchmarks run the augmented Lagrangian and Lagrange multiplier algorithms on identical meshes, 2D and 3D (VM191, VM201).
- Element birth/death with REFT set to the bar temperature returns the reborn element strain-free; removing the thermal load then leaves it with negative thermal strain (VM194).
- Inertia relief is validated three ways, including retrieval after a CMS superelement use pass (VM196).
- Coriolis is applied to the rotating frame; Campbell diagrams and stability thresholds come from CAMPBELL and PLCAMP with many load steps for threshold resolution (VM197).
- Axisymmetric elements with torsion (ROTY on PLANE182/PLANE183) carry a 60 degree in-plane twist, then MAP2DTO3D extrudes the 2D solution into 3D (VM198).
- Bearing stiffness and damping coefficients are extracted two ways: COMBI214 real constants in 2D and a FLUID218 hydrodynamic mesh in 3D, both perturbed about the transient equilibrium position (VM199).
- Alumina is entered through the viscoelastic input format solely so one element type serves both seal materials (VM200).
- White-noise pressure PSD is approximated by a flat spectrum from 1 Hz to 80 Hz (VM203).
- Mohr-Coulomb sand (TB,MC) is driven to the active state by a tapered wall displacement; the earth pressure coefficient profile comes from PATH operations (VM205).
- A static solve calibrates coil resistance and inductance so the circuit-driven transient can be checked against the analytic RL response (VM207).
- The hydrostatic fluid element HSFLD241 is exercised with both the GAS ideal-gas option and tabulated PVDATA pressure-volume points (VM209).
- A pyramid transition between hexahedra and tetrahedra is validated under pure bending; the working plane defines the interface region (VM210).

## Equations that matter
The source numbers no equations; VM anchors stand in for tags.

$$\sigma_z = \frac{M_z\, y}{I_c}$$
Pure-bending axial stress, the exact check for the hex-tet pyramid interface (VM210).

$$\oint \mathbf{H}\cdot d\boldsymbol{\ell} = I$$
Ampere's law; the mmf drop in the iron is this line integral evaluated by POST1 path logic (VM190).

## Numbers worth citing
- Clamped circular plate: worst mode ratio 1.016 for $f_{0,2}$ (target 1505.07 Hz) (VM181).
- Slot conductor AC loss ratio: target 2.33 is a graphical estimate; APDL ratios 1.025 (PLANE13) and 1.031 (PLANE233) (VM185).
- Transient slot conductor: vector potential at node 1, $t = 2\pi$, ratio 0.950, the worst magnetics result in the slice (VM186).
- Hertz contact: semi-contact length $b$ ratio 0.967 in all four variants (target 1.20 mm, APDL 1.1609 mm); approach distance ratios 1.000 to 1.024 (VM191).
- Rotating elastic system stability thresholds: 4312.5 rpm vs 4271 rpm target (ratio 0.990, Case 1) and 7300 rpm vs 7250 rpm (0.993, Case 2) (VM197).
- Large strain torsion: maximum shear stress ratios 0.956 to 0.987 against the -48.0 psi target across seven element cases (VM198).
- Oil film bearing, 3D FLUID218: KYY ratio 1.100 and CXY 1.076, the widest spreads in the slice; 2D eccentricity ratio 0.275 vs 0.266 (0.969) (VM199).
- Rubber cylinder: force at 0.1 m displacement ratio 1.064 to 1.066; the 250 N target is read from a graph in the reference (VM201).
- Shear beam frequencies: ratios 1.046 and 1.052 (VM202).
- PSD plate: peak deflection PSD ratio 1.057; the 101.7 mm one-sigma displacement has no closed-form reference value (VM203).
- Earth pressure coefficient: ratio 1.110 at 1 m depth, 1.000 at 2 m to 10 m (target 0.333 throughout) (VM205).
- Air spring: worst load ratio 0.911 (GAS option, 40 psi, UY = 0.25 in); table displacements are scaled by 4 for quarter symmetry (VM209).

## Definitions introduced
- AC/DC power loss ratio: $R_{ac}/R_{dc}$ per unit length; $R_{dc} = \rho/A$ (VM185).
- Generalized Scalar Potential (GSP): three-solution magnetic scalar strategy, controlled by MAGOPT, required for multiply connected domains (VM190).
- Inertia relief: accelerations computed to counterbalance applied loads so reaction force sums are zero (VM196).
- Singularity-based XFEM: crack representation without a conforming mesh, tips flagged by node components; SIFs from CINT,TYPE,SIFS averaged over contours 2 to 6 (VM193).

## Figures and tables to return to
- Fig. 286 and 287: eddy, source and total current time histories, the transient conductor's main deliverable (VM186).
- Fig. 291: displacement loading history for the compression-relaxation cycle; needed to read the load-step numbering in the results (VM189).
- Fig. 302 and 303: Campbell diagrams, cases 1 and 2 (VM197).
- Fig. 307: 2D shaft orbit plot converging to the bearing equilibrium position (VM199).
- Fig. 311: in-plane stress versus temperature through the 460 degree C hold (VM200).
- Fig. 314: rubber cylinder force versus deflection (VM201).
- Fig. 319: spectral displacement response to the uniform PSD force (VM203).
- Table 3: pressure-volume input points for the PVDATA fluid model at 20, 40 and 60 psi (VM209).
- Fig. 329 and 330: air spring load-height curves, GAS versus PVDATA options (VM209).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM181 | Natural Frequency of a Flat Circular Plate | Modal (ANTYPE=2) | PLANE183 | Blevins, Formulas for Natural Frequency and Mode Shape, 1979, p. 241 |
| VM182 | Transient Response of a Spring-mass System | Modal + transient mode-superposition (ANTYPE=2, 4) | COMBIN40 | Vierck, Vibration Analysis, 2nd ed., 1979, sec. 5-8 |
| VM183 | Harmonic Response of a Spring-mass System | Modal + harmonic mode-superposition (ANTYPE=2, 3) | COMBIN40 | Vierck, Vibration Analysis, 2nd ed., 1979, sec. 4-2 |
| VM184 | Straight Cantilever Beam | Static | SOLID5, SOLID92, SOLID98, SOLID187 | Any basic mechanics of materials text |
| VM185 | AC Analysis of a Slot Embedded Conductor | Coupled-field harmonic (ANTYPE=3) | PLANE13, PLANE233 | Konrad, IEEE Trans. Magnetics MAG-18(1), 1982, pp. 284-292 |
| VM186 | Transient Analysis of a Slot Embedded Conductor | Transient magnetic (ANTYPE=4) | PLANE13, PLANE233 | Konrad, IEEE Trans. Magnetics MAG-18(1), 1982 |
| VM187 | Bending of a Curved Beam | Static | SOLID5, SOLID92, SOLID98, SOLID187 | Roark, Formulas for Stress and Strain, 4th ed., 1965, p. 166 |
| VM188 | Force Calculation on a Current Carrying Conductor | Static magnetic | PLANE233, INFIN110 | Moon, Magneto-Solid Mechanics, 1984, p. 418 |
| VM189 | Stress Relaxation of a Chloroprene Rubber | Static | SOLID185 | Dal et al., Computational Mechanics 44, 2009, pp. 809-823 |
| VM190 | Ferromagnetic Inductor | Static magnetic | SOLID98, INFIN47, SOURC36 | Chapman, Electric Machinery Fundamentals, 1985, p. 14, ex. 1-1 |
| VM191 | Hertz Contact Between Two Cylinders | Static | CONTA175, PLANE182, SOLID185 | Chandrasekaran, Haisler, Goforth, Finite Elements in Analysis and Design 3, 1987, pp. 39-56 |
| VM192 | Cooling of a Billet by Radiation | Transient thermal (ANTYPE=4) | SOLID70, SURF152 | Siegel and Howell, Thermal Radiation Heat Transfer, 2nd ed., 1981, p. 229, prob. 21 |
| VM193 | Stress Intensity Factor for an Inclined Crack Using XFEM | Static | PLANE182 | Liu, Xiao, Karihaloo, Int. J. Numer. Methods Eng. 59, 2004, pp. 1103-1118 |
| VM194 | Element Birth/Death in a Fixed Bar | Static | LINK180 | Any standard mechanics of materials text |
| VM195 | Toggle Mechanism | Static | MPC184, BEAM188, COMBIN14, LINK11 | Martin, Kinematics and Dynamics of Machines, 2nd ed., 1982, pp. 55-56 |
| VM196 | Counter-Balanced Loads on a Block | Static with inertia relief; substructure (ANTYPE=7) | SOLID45, SOLID185, MATRIX50 | Any basic mechanics text |
| VM197 | Rotating Elastic System | Static; modal and linear perturbation modal (ANTYPE=0, 2) | MASS21, COMBIN14 | Friswell et al., Dynamics of Rotating Machines, 2010, pp. 423-429 |
| VM198 | Large Strain In-plane Torsion Test | Static | PLANE182, PLANE183, SOLID185, SOLID186 | Nagtegaal and DeJong, Int. J. Numer. Methods Eng. 17, 1981, pp. 15-41 |
| VM199 | Oil Film Bearing Supporting a Rotating Shaft Under Static Load | Static + transient (ANTYPE=0, 4) | MASS21, COMBI214, SOLID185, CONTA174, TARGE170, FLUID218 | Friswell et al., Dynamics of Rotating Machines, 2010, p. 181 |
| VM200 | Viscoelastic Sandwich Seal Analysis | Static | PLANE183, SOLID186 | Soules et al., GE report 86-LRL-2022, 1986 |
| VM201 | Rubber Cylinder Pressed Between Two Plates | Static | PLANE182, SOLID185, TARGE169, TARGE170, CONTA175, MESH200 | Tussman and Bathe, Computers and Structures 26(1/2), 1987, pp. 357-409 |
| VM202 | Transverse Vibrations of a Shear Beam | Modal (ANTYPE=2) | SHELL281 | Blevins, Formulas for Natural Frequency and Mode Shape, 1979, pp. 171-176 |
| VM203 | Dynamic Load Effect on Supported Thick Plate | Modal + PSD spectrum (ANTYPE=8) | SHELL281 | NAFEMS, Selected Benchmarks for Forced Vibration, 1989, Test 21R |
| VM204 | Solid Model of an Axial Bearing | Solid modelling Boolean operations | none | Any basic geometry text |
| VM205 | Earth Pressure Problem Using Mohr Coulomb Model | Static | PLANE182 | Ou, Deep Excavation: Theory and Practice, 2006, p. 94 |
| VM206 | Stranded Coil with Voltage Excitation | Static + harmonic | PLANE233, INFIN110 | Boast, Principles of Electric and Magnetic Fields, 1948, p. 247, eq. 12.18 |
| VM207 | Stranded Coil Excited by External Circuit | Static + transient | PLANE233, INFIN110, CIRCU124 | Boast, Principles of Electric and Magnetic Fields, 1948, p. 247, eq. 12.18 |
| VM208 | RL Circuit with Controlled Source | Harmonic | CIRCU124 | O'Malley, Schaum's Basic Circuit Analysis, 2nd ed., 1992, prob. 14.23 |
| VM209 | Static Analysis of Double Bellows Air Spring | Static | SHELL208, HSFLD241, REINF263 | Berry and Yang, Int. J. Numer. Methods Eng. 39, 1996, pp. 1097-1114 |
| VM210 | Pyramid Validation of Tetrahedron to Hexahedron | Static | SOLID95, SOLID186 | Popov, Introduction to Mechanics of Solids, 1998, pp. 182-185 |

## Links
[[Modal analysis]], [[Random vibration]], [[Rotordynamics]], [[Contact mechanics]], [[Hyperelasticity]], [[Viscoelasticity]], [[Fracture mechanics]], [[Electromagnetics]], [[Circuit analysis]], [[Thermal radiation]], [[Soil mechanics]], [[Ansys Mechanical APDL]]

## Flags
- Every case in the slice has a companion input-listing page (Hlp_V_VM\<N\>TXT.html, the vm\<N\>.dat file); these were not read per the extraction remit.
- VM188, VM190, VM193 and VM206 additionally require a supplemental vm\<N\>.cdb mesh file from the release download VM2024R2_MAPDL.zip; VM193 needs four (vm193a to vm193d).
- The source has no page numbers and numbers no equations; VM numbers serve as the anchors throughout, and the two equations above carry VM anchors instead of tags.
- Reference targets are graphical estimates in VM185 (loss ratio) and VM201 (force-deflection), so their ratios overstate disagreement.
- VM209 Figure 327 is captioned "Multiple Species Flow Problem Sketch" for what is an air-spring sketch; suspected caption erratum. VM209 results tables scale displacements by 4 for quarter symmetry.
- VM193 reference author appears as "Ziao, Q.Z.", a suspected misspelling of Xiao.
- VM207 cross-references VM206; both sit inside this slice. No cross-references to cases outside VM181-VM210 were found.
- No unreadable pages.
