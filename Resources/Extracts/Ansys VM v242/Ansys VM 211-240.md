---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM211-VM240
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification test cases, VM211 to VM240, each a small benchmark: problem sketch, material and geometry tables, modelling notes, and a target-versus-Mechanical-APDL results table with ratios. The slice is dominated by coupled-field and nonlinear problems: hyperelastic contact (VM211, VM218), naval shock DDAM (VM212), electromagnetics and inductance (VM213, VM214, VM233), thermal-electric and MEMS actuation (VM215, VM223, VM236), buckling and warping beams (VM216, VM217, VM222), diffusion with electromigration and stress-migration (VM220, VM226), radiosity radiation (VM227, VM228, VM230), piezoelectricity and piezoresistivity (VM231, VM237, VM238), fracture (VM232), viscoelasticity (VM234), creep (VM224), shape memory alloy (VM221), pretension (VM225), frictional heating (VM229), prestressed modal analysis (VM219, VM235), and MPC184 joints and rigid bodies (VM239, VM240). Each case names its element types, key commands, and the published reference its target values come from; the job of the slice is to certify those element and command combinations against classical solutions.

## Key ideas
- VM211 solves one rubber-cylinder contact problem twelve ways: four element pairings, each under default contact, Lagrange multipliers (KEYOPT(2) = 3), and exponential pressure-penetration (KEYOPT(6) = 3); its targets are read off a graph in the reference (VM211).
- DDAM shock analysis is a modal run (ANTYPE = 2) followed by a spectrum run (ANTYPE = 8) with ADDAM and VDDAM spectrum constants; outputs are mode frequencies, participation factors, and shock design values (VM212).
- Differential inductance about an operating point comes from a nonlinear static solve plus a linear perturbation solve; the matrix is assembled from incremental energy read from the IENE element record (VM213).
- Velocity effects in a moving conductor are applied with BF,,VELO and a uniform field with DFLX; a static solve then reproduces the induced EMF (VM214).
- Nonlinear buckling is found by driving the frame with an in-plane load and a small out-of-plane perturbation force that is removed near the critical load (VM216).
- BEAM188 and BEAM189 carry a warping degree of freedom; VM222 verifies it against a differential quadrature solution for a doubly fixed I-beam under distributed torque (VM222).
- VM219 and VM235 are the same prestressed beam-transducer modal problem; VM219 re-solves it through APDL Math, writing the assembled matrices with WRFULL and running *EIGEN on the unsymmetric .full matrices (VM219, VM235).
- Electromigration and stress-migration can be modelled two ways: as a transport velocity body load on diffusion elements (PLANE238, BF,,VELO) or with the migration model (TB,MIGR) on coupled-field PLANE223 elements; both routes are benchmarked against the same analytical or published solution (VM220, VM226).
- The radiosity method is verified on finite coaxial cylinders, infinite coaxial cylinders, and concentric spheres, checking view factor rules (F11 = 0, row sums, reciprocity) and radiative heat flux; 2D axisymmetric models can extrude SURF252 radiosity surfaces with RSYMM,,CENT (VM227, VM228, VM230).
- One piezoelectric strip is solved with PLANE13 (extra shape functions), PLANE222 (enhanced strain), and PLANE223, all matching the analytical electro-elastic field; the same case exists in Workbench as vm-wb-mech-109 (VM231).
- A piezoelectric transducer couples to an RLC circuit through CIRCU94; the transient response to a step voltage is checked against a Laplace-transform solution of the equivalent circuit (VM237).
- Four piezoresistors on a stressed beam are wired into a Wheatstone bridge by coupling VOLT degrees of freedom; longitudinal and transverse piezoresistive coefficients set the output voltage (VM238).
- The UMM option of CINT computes stress intensity factors on degenerated tetrahedral meshes without a structured crack-tip mesh (VM232).
- The TEAM20 solenoid benchmark uses the difference scalar potential (DSP) formulation with SOLID98, stated as more accurate than MVP and cheaper than edge elements; the coil is built with RACE (VM233).
- Ogden viscoelasticity under cyclic displacement shows stress accumulation then relaxation to near zero after unloading (VM234).
- Electrostatic pull-in and release hysteresis of a clamped beam uses electroelastic PLANE223 (KEYOPT(1) = 1001) air elements with CONTA178 contact stops (VM236).
- MPC184 supplies universal, revolute, and slider joints plus rigid beams; VM239 runs the same mechanism once fully flexible and once fully rigid, and VM240 embeds thermally expanding rigid beams in an elastic bar (VM239, VM240).
- Bolt-style preload on solids is applied with PRETS179 sections and the SLOAD command (VM225).
- Shape memory alloy response (TB,SMA) is verified by loading to detwinned martensite, unloading, then heating to recover the strain, ending at zero stress and strain (VM221).
- Frictional heating between sliding blocks is solved both with PLANE13 plus contact and with coupled-field PLANE223, including a Lagrange multiplier contact variant (VM229).

## Equations that matter
$$\frac{d^{2}C}{dx^{2}}-\frac{V}{D}\frac{dC}{dx}=0 \tag{226-2}$$
Governing 1D steady advection-diffusion ODE; its solution (226-7) gives the concentration profile the FE results are checked against (VM226). Equations (226-1) to (226-7) and the sphere flux formula (230-1) are typeset as images in the source; the numbers above are their locators.

$$\beta=\frac{1}{27}\,\frac{\omega a^{3}}{E\,I_{col}}, \qquad M_{max}=\frac{19}{54}\,\omega a^{2}$$
Theoretical maximum rotation and bending moment for the portal frame (VM217).

$$\varepsilon = A\,\sigma^{n}t^{m}$$
Creep law with $A = 3.125\times10^{-14}$ per hour, $n = 5$, $m = 0.5$ (VM224).

$$\alpha_{2}=\arctan\!\left(\frac{\tan\alpha_{1}}{\cos\beta}\right)$$
Universal joint output rotation versus input rotation for shafts at relative angle $\beta$ (VM239).

## Numbers worth citing
- Lateral buckling critical load: target 1.09, computed 1.036, ratio 0.951 for both BEAM188 and BEAM189 (VM216).
- Portal frame maximum rotation ratio 1.093 (target 0.195e-2, computed 0.213e-2 rad); bending moment ratio 1.019 (VM217).
- Hyperelastic plate deflection ratios drop to 0.894 (SHELL281 at 24 psi) and sit near 0.92 to 0.93 for all shell types at 24 and 38 psi; near 1.0 only at 4 psi (VM218).
- Electromigration concentration at normalised time 0.01: ratio 1.13 with PLANE238 and 1.05 with PLANE223; ratios recover to 0.99 to 1.03 at later times (VM220).
- View factor F(2-2) for finite coaxial cylinders: target 0.503, computed 0.480, ratio 0.950 (VM227).
- Radiosity heat flux ratios run 0.95 to 0.96 for infinite cylinders (VM228) and 0.95 to 0.97 for the interior flux of concentric spheres (VM230).
- Stress intensity factor with UMM: SOLID185 ratio 1.038; SOLID186 1.005; SOLID187 1.007 against target 0.332e10 (VM232).
- Solenoid actuator: virtual work force 80.1 N ratio 1.001; pole flux density BZ ratio 1.031; arm BZ 2.05 T ratio 0.999 at 5000 A-turns (VM233).
- Viscoelastic relaxation: Cauchy stress 5.994e5 N/m^2 against 6.013e5 at t = 16 s (ratio 0.997); residual 17.7 N/m^2 against target 0 at t = 20 s (VM234).
- Rubber cylinder contact forces stay within ratios 0.966 to 1.024 of targets (250 N at 0.1 m, 1400 N at 0.2 m displacement); targets were read graphically from the reference (VM211).
- RLC-piezoelectric transient voltage ratios span 0.978 to 1.026 over the sampled time points (VM237).
- DDAM shock design values: 2316 and 8133 in/s^2 for modes at 46.3 Hz and 114 Hz, ratios 1.000 (VM212).

## Definitions introduced
- DDAM analysis - shock spectrum analysis for shipboard equipment; the spectrum depends on ship type, mounting location, shock direction, and design type, and yields shock design values per mode (VM212).
- Differential inductance - inductance about an operating point, derived from the incremental energy of linear perturbation solutions (VM213).
- Migration model (TB,MIGR) - material model defining the effective electric charge (electromigration) or migrating particle volume (stress-migration) driving mass transport in diffusion analyses (VM220, VM226).
- UMM - CINT option (CINT,UMM,ON) computing fracture parameters on unstructured or degenerated meshes (VM232).
- DSP formulation - difference scalar potential magnetic formulation; stated as more accurate than MVP and more efficient than edge elements (VM233).
- Pull-in and release hysteresis - the voltage-displacement loop of an electrostatically loaded beam that snaps to contact and releases at different voltages (VM236).

## Figures and tables to return to
- Fig. 333 and Fig. 335 - rubber cylinder problem sketch and force-deflection curve, the shape the twelve contact variants must reproduce (VM211).
- Fig. 336 - schematic of the 2-DOF equipment-foundation system for DDAM (VM212).
- VM218 results table - deflection versus pressure for four shell formulations, a ready-made shell benchmark grid (VM218).
- Fig. 369 - microactuator geometry with the d1 to d11 dimension labels the input file uses (VM223).
- Fig. 388 - crack geometry and dimensions for the UMM stress intensity case (VM232).
- Fig. 389 - B-H curve used in the TEAM20 solenoid benchmark (VM233).
- Fig. 392 - Cauchy stress evolution over the four load cycles plus relaxation (VM234).
- Figs. 400 and 401 - piezoresistor placement and Wheatstone bridge wiring (VM238).
- Fig. 402 - shaft-driven slider-crank mechanism layout with joint labels (VM239).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|----|-------|---------------|----------|---------------------------|
| VM211 | Rubber Cylinder Pressed Between Two Plates | Static, hyperelastic contact | PLANE182, PLANE183, SOLID185, SOLID186, CONTA172, CONTA174, TARGE169, TARGE170 | Tussman and Bathe, Computers and Structures 26, 1987 |
| VM212 | DDAM Analysis of Foundation System (2-DOF System) | Modal + spectrum (DDAM) | MASS21, COMBIN40, BEAM188 | O'Hara and Cunniff, NRL Memo Report 1396, 1963 |
| VM213 | Differential Inductance of a Transformer | Nonlinear magnetic static + linear perturbation | SOLID236 | Gyimesi and Ostergaard, IEEE Trans. Magnetics 35(3) |
| VM214 | Rotating Rod in a Uniform Magnetic Field | Electromagnetic static | SOLID236 | Basic electromagnetics textbook |
| VM215 | Thermal-Electric Hemispherical Shell with Hole | Coupled thermal-electric | SHELL157 | Standard electrical engineering text |
| VM216 | Lateral Buckling of a Right Angle Frame | Static, nonlinear buckling | BEAM188, BEAM189 | Simo and Vu-Quoc, CMAME 58, 1986 |
| VM217 | Portal Frame Under Symmetric Loading | Static structural | BEAM188, BEAM189 | Hoff, The Analysis of Structures, 1956 |
| VM218 | Hyperelastic Circular Plate | Static, hyperelastic | SHELL181, SHELL208, SHELL209, SHELL281 | Oden, Finite Elements of Nonlinear Continua, 1972 |
| VM219 | Frequency Response of a Prestressed Beam using APDL MATH Commands | Prestressed modal via *EIGEN | BEAM188, TRANS126 | Blevins, Formulas for Natural Frequency and Mode Shape, eq. 8-20 |
| VM220 | Electromigration Diffusion Problem with Perfectly Blocking Diffusion Barrier | Transient diffusion | PLANE238, PLANE223 | Clement and Lloyd, J. Applied Physics 71(4), 1992 |
| VM221 | Simulation of Shape Memory Alloy Effect | Static, SMA | SOLID185 | Souza et al., Eur. J. Mech. A/Solids 17, 1998 |
| VM222 | Warping Torsion Bar | Static structural | BEAM188, BEAM189 | Chen, Computers and Structures 66(2-3), 1998 |
| VM223 | Electro-Thermal Microactuator Analysis | Static structural-thermoelectric | SOLID227 | Mankame and Ananthasuresh, J. Micromech. Microeng. 11, 2001 |
| VM224 | Implicit Creep under Biaxial Load | 2D plane stress creep | PLANE182, PLANE183 | Becker and Hyde, NAFEMS R0027, Test 10a |
| VM225 | Rectangular Cross-Section Bar with Preload | Static, pretension | SOLID185, SOLID186, PRETS179 | Engineering statics text |
| VM226 | 1D Advection Diffusion Problem | Static diffusion | PLANE238, PLANE223 | Analytical solution derived in the case |
| VM227 | Radiation Between Finite Coaxial Cylinders | Steady-state radiosity | PLANE77 | Modest, Radiative Heat Transfer, 1992, p. 791 |
| VM228 | Radiation Between Infinite Coaxial Cylinders | Steady-state radiosity | PLANE35, SURF251 | Siegel and Howell, Thermal Radiation Heat Transfer, 3rd ed. |
| VM229 | Friction Heating of Sliding Block | Transient coupled thermomechanical contact | PLANE13, TARGE169, CONTA172, PLANE223 | Wiggers and Miehe, CMAME 113, 1994 |
| VM230 | Radiation Between Two Concentric Spheres | Steady-state radiosity | PLANE77, SURF251, SOLID90, SURF252 | Modest, Radiative Heat Transfer, 3rd ed., pp. 205-206 |
| VM231 | Piezoelectric Rectangular Strip Under Pure Bending Load | Static piezoelectric | PLANE13, PLANE222, PLANE223 | Parton, Kudryavtsev, Senik, Applied Mechanics: Soviet Review 2 |
| VM232 | Stress Intensity Factor for a Single Edge Crack with Pressure Load Using UMM Method | Static fracture | SOLID185, SOLID186, SOLID187 | Stephens et al., Metal Fatigue in Engineering, 2nd ed., p. 130 |
| VM233 | Static Force Computation of a 3D Solenoid Actuator | Magnetostatic (TEAM20) | SOLID98 | Gyimesi and Ostergaard, TEAM/COMPUMAG and IEEE Trans. Magnetics papers |
| VM234 | Cyclic Loading of a Rubber Block | Transient viscoelastic | SOLID185 | Holzapfel, IJNME 39, 1996 |
| VM235 | Frequency Response of a Prestressed Beam | Prestressed modal | BEAM188, TRANS126 | Blevins, Formulas for Natural Frequency and Mode Shape, eq. 8-20 |
| VM236 | Hysteresis Calculation of a Beam Under Electrostatic Load | Static electroelastic with contact | PLANE223, PLANE182, CONTA178 | Gilbert, Ananthasuresh, Senturia, MEMS, 1996 |
| VM237 | RLC Circuit with Piezoelectric Transducer | Static + transient circuit-coupled piezoelectric | PLANE223, CIRCU94 | IEEE Std 176-1987; Vlach, Basic Network Theory, 1992 |
| VM238 | Wheatstone Bridge Connection of Piezoresistors | Static piezoresistive | PLANE223, PLANE183 | Bao, Handbook of Sensors and Actuators, v. 8, ch. 5 |
| VM239 | Mechanics of the Revolute and Universal Joints | Static multibody | BEAM188, MPC184 | Shigley and Uicker, Theory of Machines and Mechanisms, 2nd ed., p. 115 |
| VM240 | Thermal Expansion of Rigid Beams in a Composite Bar | Static thermal-structural | SOLID185, MPC184 | Gere and Timoshenko, Mechanics of Materials, 2nd ed. |

## Links
[[Ansys VM 181-210]] · [[Ansys VM 241-270]] · [[Mechanical APDL]] · [[Finite element verification]] · [[Contact mechanics]] · [[Hyperelasticity]] · [[Viscoelasticity]] · [[Creep]] · [[Shape memory alloys]] · [[Radiation heat transfer]] · [[Piezoelectricity]] · [[Fracture mechanics]] · [[Electromagnetics]] · [[MEMS]] · [[Shock and vibration]]

## Flags
- Every case has a companion input-listing page (Hlp_V_VM&lt;N&gt;TXT.html, file vm&lt;N&gt;.dat) with the full APDL deck; not read in this pass.
- VM211 explicitly re-solves the problem of VM201, which sits in the neighbouring VM181-VM210 slice; the indexer should link them.
- VM219 and VM235 share one physical problem and identical target frequencies; VM219 is the APDL Math variant.
- Four cases require supplemental files from the VM2024R2_MAPDL.zip download before they run: VM228 (.cdb, .iges), VM230 (.cdb, .rsm), VM232 (.cdb), VM233 (.cdb, .iges).
- Suspected errata in the source: VM213 Figure 340 is captioned "Harmonic Analysis of a Coaxial Cable", unrelated to the transformer case; VM234 header reads "Static Structural Analysis (ANTYPE = 4)" though ANTYPE = 4 is transient; VM237 header reads "Static (ANTYPE = 1)" though ANTYPE = 1 is buckling; VM212 tables contain typos ("Sprint constant", "arbitratry section") and give moment of inertia in in-lb-sec^2; VM216 lists "lzz = 0.54 in" beside "lyy = 1350 in^4"; VM229 prints the reference author as "Wiggers" (usually Wriggers).
- Units are unstated in some results tables (VM213 inductance, VM219/VM235 frequency, VM236 displacement); values recorded as printed.
- The source HTML has no page numbers; VM numbers are the anchors throughout, and equations are embedded as SVG images, so only equation (226-2) was transcribed to MathJax with confidence.
