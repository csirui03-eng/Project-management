---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM1-VM30
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
The first thirty verification cases of the manual, each a small problem with a classical or readily obtainable reference solution, solved in Mechanical APDL and reported as a target versus computed table with a ratio column. Every case follows the same layout: reference, analysis type with ANTYPE code, element types, a link to the input listing (vm*n*.dat), problem sketch, material, geometry and loading tables, modelling notes, then results. The slice is dominated by linear statics from Timoshenko and from Crandall and Dahl (trusses, beams, plates, shells, cylinders), but it already spans plasticity (VM7, VM11, VM24), large deflection and snap-through (VM14, VM17, VM26), stress stiffening (VM21), random vibration (VM19), transient heat conduction (VM28), thermal-structural and frictional contact (VM23, VM27, VM29), and two non-physics utility tests: parametric macro arithmetic (VM8) and solid-model Boolean accuracy (VM30). Its job in the book is to exercise the basic element library (LINK180, BEAM188, PLANE182/183, SHELL181/208/281, PIPE288/289, SOLID185, contact elements) on problems where the answer is known in closed form.

## Key ideas
- Standard case layout: reference, analysis type, elements, input listing, then target versus Mechanical APDL results with a ratio column (VM1).
- Reactions of an axially loaded bar with both ends built in; ratios exactly 1.000 (VM1).
- 30 inch WF beam loaded on overhangs; bending stress and midspan deflection with a BEAM188 I-section (VM2).
- Copper and steel wires under load plus a 10 degF rise; the rigid lower beam is modelled by nodal coupling (VM3).
- Two-bar hinged structure; stress and deflection under a 5000 lb load (VM4).
- Cantilever tapering from depth d to 3d; plane stress with thickness, $\nu = 0$ chosen to agree with beam theory (VM5).
- Pinched thin-walled cylinder on one-eighth symmetry; the classic shell discretisation benchmark (VM6).
- Coaxial steel and aluminium tubes compressed into the plastic range; one problem solved three ways, PIPE288, SOLID185 and SHELL181 (VM7).
- User macro built with *CREATE computing node and keypoint distances; a scripting test, no elements (VM8).
- Two-spring large-deflection problem solved by the slow dynamics technique with COMBIN40 dampers near critical (VM9).
- Unsymmetric T-section in pure bending, section input via SECDATA (VM10).
- Three-rod frame loaded until fully plastic then unloaded; residual stress recovered in the central rod (VM11).
- Vertical bar under an offset horizontal force; maximum principal and shear stress with PIPE16 and PIPE288 (VM12).
- Closed pressure vessel as an axisymmetric shell; hoop target taken from thick-shell theory because SHELL208 uses thick-shell logic through the thickness (VM13).
- Eccentrically compressed channel strut, half model with fixed-free boundary; large deflection required (VM14).
- Circular plate in three cases, clamped-uniform, clamped-point, simply supported-uniform; stiffness matrix reused across load steps until constraints change (VM15).
- Solid beam bending with PLANE42 and PLANE182; the end moment applied as an equal and opposite force pair (VM16).
- Hinged cylindrical shell snap-through under a centre point load; arc length solution, results tracked in POST26 (VM17).
- Quarter circular ring loaded out of plane; a solid bar modelled with pipe elements by setting wall thickness to half the diameter (VM18).
- NAFEMS Test 5R random vibration of a deep beam; peak displacement and stress PSD found at 42.63 Hz (VM19).
- Membrane cylinder as a one-element 10 degree sector; closed end simulated by a 15,000 psi edge traction (VM20).
- Tie rod with tension and lateral load; stress stiffening roughly halves midspan deflection and moment (VM21).
- Belleville spring element as a conical axisymmetric shell; load applied per full circumference (VM22).
- Thermal-structural contact between two bodies; interface temperature and heat flow through CONTA175 and TARGE169 with 100 W/degC conductance per contact element (VM23).
- Elastic-perfectly-plastic rectangular beam forming a plastic hinge; moment ramped from $M_{yp}$ to $1.5\,M_{yp}$ in four increments (VM24).
- Thick-walled cylinder under internal pressure, then spun at 1000 rad/s; radial and tangential stresses through the wall, linearised stresses shown in POST1 (VM25).
- Cantilevered plate rolled up by an end moment; large deflection with shells, and a demonstration of the restart option ANTYPE,,REST mid-load (VM26).
- Heated bar closing a 0.002 in gap against a rigid wall; LINK180 with CONTA178, gap stiffness set high to mimic the wall (VM27).
- Semi-infinite slab suddenly exposed to convection; graded mesh toward the surface and automatic time stepping from a 10 s initial step (VM28).
- Friction block on a 20 degree incline; the sticking to sliding transition bracketed by two load steps either side of the theoretical force (VM29).
- Fillet Boolean accuracy judged by the out-of-plane deviation of meshed nodes; a pre-processor test, nothing is solved (VM30).

## Equations that matter
$$M_{yp} = \frac{\sigma_{yp}\, b h^2}{6}, \qquad M_{ult} = 1.5\, M_{yp} \tag{VM24}$$
Elastic-limit and fully plastic moments of a rectangular section in pure bending; the load schedule of the plastic hinge test.

$$F_{\text{axial}} = \frac{P \pi d^2}{4} \tag{VM13}$$
Closed-end force applied to the open shell model to simulate the capped vessel; 5,654,866.8 lb at P = 500 psi, d = 120 in.

## Numbers worth citing
- Lowest ratios in the slice sit near 0.95 to 0.97: PLANE182 fixed-end stress ratio 0.965 where PLANE183 gives 1.000 (VM5); SHELL181 pinched-cylinder deflection ratio 0.965 against a target of 0.1139 in, SHELL281 gives 0.990 (VM6).
- Plate stress ratio 0.978 in case 1 because APDL reports at the nearest element centroid, not the node where the theoretical maximum sits (VM15).
- Snap-through displacements run up to ratio 1.051 (SHELL181, UY at A); targets are read from a graphical solution (VM17).
- Plastic hinge rotation ratio 0.975 at $M/M_{yp} = 1.3333$; at 1.5 the target rotation is infinite and APDL reports 0.11850 rad, no ratio (VM24).
- Zero-target stresses return small residuals with no ratio: 6.7 psi radial at r = 8 in under pressure, 49.3 psi radial at r = 4 in under rotation (VM25).
- Large-deflection cantilever targets are to graphical readout accuracy; SHELL181 UX ratio 0.95 (VM26).
- Sticking-sliding switch bracketed between $F_x$ = 5.76720 lb (sliding) and 5.7674 lb (sticking), theoretical value 5.76728 lb (VM29).
- Fillet out-of-plane deviation $2.91 \times 10^{-7}$ mm against a zero target (VM30).
- Peak response PSD 179.18 mm$^2$/Hz at 42.63 Hz against a target of 180.90 mm$^2$/Hz at 42.66 Hz; 2 percent damping (VM19).

## Definitions introduced
- Slow dynamics - quasi-static solution obtained from a nonlinear transient run by adding unit mass and roughly critical damping (VM9).
- SINTMX - stress intensity output defined as twice the maximum shear stress (VM12).
- Ratio - the Mechanical APDL result divided by the reference target; the pass metric in every results table (VM1).

## Figures and tables to return to
- Figure 10 - one axisymmetric tube assembly idealised three ways, pipe, solid sector and shell sector; a template for element-equivalence studies (VM7).
- Figure 19 - displaced shapes of all three circular-plate load cases in one three-window plot (VM15).
- Figure 22 - deflection against total load plot showing the snap-through path from the arc length solution (VM17).
- Figures 32 and 33 - linearised SZ and SX stresses through the cylinder wall under internal pressure (VM25).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM1 | Statically Indeterminate Reaction Force Analysis | Static (ANTYPE=0) | LINK180 | Timoshenko, Strength of Material Pt I, p. 26 |
| VM2 | Beam Stresses and Deflections | Static | BEAM188 | Timoshenko Pt I, p. 98 |
| VM3 | Thermally Loaded Support Structure | Static thermal stress | LINK180 | Timoshenko Pt I, p. 30 |
| VM4 | Deflection of a Hinged Support | Static | LINK180 | Timoshenko Pt I, p. 10 |
| VM5 | Laterally Loaded Tapered Support Structure | Static | PLANE182, PLANE183 | Crandall and Dahl, p. 342 |
| VM6 | Pinched Cylinder | Static | SHELL181, SHELL281 | Cook 1981; Takemoto and Cook 1973 |
| VM7 | Plastic Compression of a Pipe Assembly | Static plastic | PIPE288, SHELL181, SOLID185 | Crandall and Dahl, p. 180 |
| VM8 | Parametric Calculation of Point-to-Point Distances | Parametric arithmetic | none | any basic geometry text |
| VM9 | Large Lateral Deflection of Unequal Stiffness Springs | Nonlinear transient dynamic (ANTYPE=4) | COMBIN14, COMBIN40 | Vanderplaats 1984, pp. 72-73 |
| VM10 | Bending of a Tee-Shaped Beam | Static | BEAM188 | Crandall and Dahl, p. 294 |
| VM11 | Residual Stress Problem | Static plastic | LINK180 | Crandall and Dahl, p. 234 |
| VM12 | Combined Bending and Torsion | Static | PIPE16 (archived), PIPE288 | Timoshenko Pt I, p. 299 |
| VM13 | Cylindrical Shell Under Pressure | Static | SHELL208 | Timoshenko Pt I, p. 45; Ugural and Fenster 1981 |
| VM14 | Large Deflection Eccentric Compression of a Column | Static large deflection | BEAM188 | Timoshenko Pt I, p. 263 |
| VM15 | Bending of a Circular Plate Using Axisymmetric Elements | Static | SHELL208 | Timoshenko Pt II, pp. 96-103 |
| VM16 | Bending of a Solid Beam (Plane Elements) | Static | PLANE42 (archived), PLANE182 | Roark, Formulas for Stress and Strain, pp. 104, 106 |
| VM17 | Snap-Through Buckling of a Hinged Shell | Static, large deflection, arc length | SHELL181, SHELL281 | Chang, Computers and Structures 1991 |
| VM18 | Out-of-Plane Bending of a Curved Bar | Static | PIPE18 (archived), PIPE289 | Timoshenko Pt I, p. 412, eq. 241 |
| VM19 | Random Vibration Analysis of a Deep Simply-Supported Beam | Mode-frequency, spectrum (ANTYPE=8) | BEAM188 | NAFEMS Forced Vibration, Test 5R |
| VM20 | Cylindrical Membrane Under Pressure | Static | SHELL181 | Timoshenko Pt II, p. 121 |
| VM21 | Tie Rod with Lateral Loading | Static, stress stiffening | BEAM188 | Timoshenko Pt II, p. 42 |
| VM22 | Small Deflection of a Belleville Spring | Static | SHELL208 | Timoshenko Pt II, p. 143 |
| VM23 | Thermal-structural Contact of Two Bodies | Static coupled field | PLANE13, PLANE223, CONTA175, TARGE169 | any basic mechanics text |
| VM24 | Plastic Hinge in a Rectangular Beam | Static plastic | BEAM188 | Timoshenko Pt II, article 64 |
| VM25 | Stresses in a Long Cylinder | Static | PLANE183 | Timoshenko Pt II, p. 213 |
| VM26 | Large Deflection of a Cantilever | Static large deflection | SHELL181, SHELL281 | Bathe and Dvorkin 1986 |
| VM27 | Thermal Expansion to Close a Gap | Static thermal stress with contact | LINK180, CONTA178 | Harris, Introduction to Stress Analysis, p. 58 |
| VM28 | Transient Heat Transfer in an Infinite Slab | Transient thermal (ANTYPE=4) | PLANE77 | Holman, Heat Transfer, p. 106 |
| VM29 | Friction on a Support Block | Static with contact | CONTAC12 (archived), CONTA178 | Beer and Johnston, p. 283 |
| VM30 | Solid Model of Surface Fillet | Solid modelling Boolean operations | none (SHELL281 for meshing only) | NAFEMS R0001, p. 23 |

## Links
[[Ansys Mechanical APDL]], [[Finite element verification]], [[Beam bending]], [[Shell elements]], [[Plasticity]], [[Buckling]], [[Random vibration]], [[Heat conduction]], [[Contact mechanics]], [[Thermal stress]]

## Flags
- Every case VMn has a companion input listing page (Hlp_V_VMnTXT.html, file vm*n*.dat) holding the full APDL deck; none were read for this extract.
- VM20 cross-references VM13 for the problem sketch; both sit inside this slice. No case references anything outside VM1-VM30.
- Suspected erratum in VM5: the modelling notes say the second solution uses "higher order PLANE82" while the overview and results tables say PLANE183.
- Suspected erratum in VM30: geometric property list gives "Θ = 1355" with no unit; likely 135 degrees.
- VM29 gives "Θ = 20" without a degree sign; the sketch context implies degrees.
- Several cases deliberately pair a current element with an archived one (PIPE16, PIPE18, PLANE42, CONTAC12); the archived pages live in the ans_arch library, not ans_elem.
- No unreadable pages; VM31 onward continues in the neighbouring slice.
