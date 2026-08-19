---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM31-VM60
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification cases, VM31 to VM60, each a small classical problem with a published target solution, run in Mechanical APDL and reported as target, computed value, and ratio. The batch spans static structures (cables, tapered members, plates, shells, thick cylinders), plasticity by hinge elements, thermal and coupled thermal-stress analysis, rigid body kinematics, modal and prestressed modal vibration, electrostatics with infinite elements, hyperelasticity, and one fracture case. Every case page follows the same skeleton: an overview table (reference, analysis type, element types, input listing), the test case statement with a problem sketch, a material-geometry-loading table, modelling notes, and a results comparison table. The slice's job in the manual is a library of single-feature benchmarks: each demonstrates one element type or solution capability against a closed-form or literature answer.

## Key ideas
- A cable model needs a seed initial strain ($10^{-7}$) to give stiffness before the iterative stress-stiffened solution converges (VM31).
- One mesh, two element types: thermal solve on PLANE55 then structural solve on PLANE182 over the same grid, with nodal coupling for constant axial strain (VM32).
- Thermal steady state in a transient run is declared when the inner-to-outer wall temperature difference stops changing; time integration is applied to the temperature degree of freedom only (VM33).
- The same tapered cantilever is solved by triangular shells, a tapered beam section, and finite strain shells, all within 0.3 per cent of theory (VM34).
- A bimetallic strip is built from a two-layer shell section; only the centre node of the fixed end is constrained, to match simple beam theory (VM35).
- Plastic hinges are modelled by breakaway COMBIN40 pairs that slide above the limit moment; the second hinge forms at $P_L = 2.5\,M_L/a$ (VM36).
- Tresca-based load estimates may drive a von Mises solver: loads are comparable but the nonlinear stress components are not directly comparable (VM38).
- Axisymmetric plate bending is handled with a 10 degree sector and a 3:1 graded radial mesh (VM39).
- Rigid body rotation is verified kinematically; density is set to $10^{-10}$ lb-sec^2/in^4 so centrifugal effects vanish, and 400 rpm is realised as one revolution in 0.15 s (VM40).
- A rigid member can be modelled two ways: an arbitrarily thick beam, or a constraint equation $\delta_y = L\,\Theta$ (VM41).
- Gravity, constant in magnitude and direction around an axisymmetric model, is applied as two circumferential harmonic loads 90 degrees out of phase (VM43, VM44).
- Lumped mass values come from $m = W/g$; spring length is arbitrary and only sets direction (VM45, VM52).
- Delamination growth is quantified as energy release rate G by VCCT through the CINT command, with contact defined between the crack faces (VM46).
- With mixed-order meshes the infinite element domain is meshed first so PLANE121 drops its midside nodes at the finite-infinite interface (VM49).
- Prestressed vibration runs as linear perturbation modal analysis after a base static solve: string, blade, membrane, and axially loaded bar (VM53, VM54, VM55, VM59).
- Removing the axial load in the bar case recovers the VM50 simply supported beam frequency of 28.766 Hz (VM59).
- Near incompressibility for Mooney-Rivlin material is approximated with $\nu = 0.49$ and reduced integration (VM56).
- Torsion-only pipe models convert shear modulus by $E = 2G(1+\nu)$; five element types give the same two frequencies to within 0.3 per cent (VM57).
- Heat-generating wire: axisymmetry lets a 30 degree sector stand for the whole, with outer node temperatures coupled for symmetry (VM58).

## Numbers worth citing
- Worst target ratio in the slice: 1.047 for UY at point A of the barrel vault roof with SHELL181; SHELL281 on the same model gives 1.003 (VM42).
- Hyperelastic cylinder inner-radius displacement ratio 1.043 (PLANE183 and SOLID185), against a target that assumes fully incompressible $\nu = 1/2$ while the model uses 0.49 (VM56).
- Axial stress at the cylinder inner surface ratio 1.029; hoop 1.014 (VM32).
- VCCT energy release rate ratio 1.027 (VM46).
- Third string mode ratio 1.022; the first two modes sit at 1.002 and 1.010 (VM53).
- SOLID226 tangential stress ratios 0.963 and 0.964 in the transient thermal-stress cylinder; SOLID5 gives 0.975 and 1.005 (VM33).
- Rotating blade frequency ratios 0.983 to 0.986 against Carnegie's 52.75 Hz (VM54).
- Bare wire steady state: centreline 419.9 F, surface 417.9 F, dissipation 341.5 BTU/hr for 111311.7 BTU/hr-ft^3 generation, h = 5 BTU/hr-ft^2-F, all ratios 1.000 (VM58).

## Definitions introduced
- STAT (COMBIN40 status): 1 means gap closed (elastic); 2 or -2 mean positive or negative slide, read as a formed plastic hinge (VM36).
- Linear perturbation modal analysis: a modal solve carried out on the prestressed state left by a base static solve (VM53).
- VCCT: virtual crack closure technique; yields G at the crack tip nodes named on the CINT command (VM46).
- Infinite surface flag: SF with Lab = INF marks the exterior face of INFIN110/INFIN111 elements as the far-field boundary (VM49).
- Stress stiffening analysis: static solution in which membrane tension supplies the transverse stiffness, needed for cables (VM31).

## Figures and tables to return to
- Fig. 44 and Fig. 45: temperature difference and tangential stress versus time, the approach to thermal steady state (VM33).
- Fig. 50: axial stress contour on the tapered bar, SOLID45 model (VM37).
- Fig. 53: UZ contours plus displaced edge view of the annular plate (VM39).
- Fig. 55: free-end displacement trace through the full revolution (VM40).
- Fig. 59 and Fig. 61: harmonic-load displacement displays at circumferential angles 0 and 90 degrees (VM43, VM44).
- Figs. 69 to 75: solid model, SOLID122 and SOLID123 meshes, electric field and voltage plots for the charged spheres (VM51).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM31 | Cable Supporting Hanging Loads | Static, stress stiffening | LINK180, CABLE280 | Beer & Johnston, Vector Mechanics for Engineers (1962), p. 260 |
| VM32 | Thermal Stresses in a Long Cylinder | Static, thermal then structural | PLANE55, PLANE182 | Timoshenko, Strength of Materials Part II, 3rd ed. (1956), p. 234 |
| VM33 | Transient Thermal Stress in a Cylinder | Coupled-field transient | SOLID5, SOLID226 | Roark & Young, Formulas for Stress and Strain, 5th ed. (1975), p. 585 |
| VM34 | Bending of a Tapered Plate (Beam) | Static | SHELL63, BEAM188, SHELL181, SHELL281 | Harris, Introduction to Stress Analysis (1959), p. 114 |
| VM35 | Bimetallic Layered Cantilever Plate with Thermal Loading | Static | SHELL281 | Roark & Young, 5th ed. (1975), pp. 113-114 |
| VM36 | Limit Moment Analysis | Static, plastic hinge | COMBIN40, BEAM188 | Crandall & Dahl, Mechanics of Solids (1959), p. 389 |
| VM37 | Elongation of a Solid Bar | Static | SOLID45, SOLID185, SOLSH190 | Harris (1959), p. 237 |
| VM38 | Internal Pressure Loading of a Thick-Walled Cylinder | Static | PLANE182, SURF153, SOLID185, SURF154 | Timoshenko, Part II (1956), p. 388 |
| VM39 | Bending of a Circular Plate with a Center Hole | Static | SHELL63, SHELL181 | Timoshenko, Part II (1956), p. 111 |
| VM40 | Large Deflection and Rotation of a Beam Pinned at One End | Nonlinear transient dynamic | BEAM188 | any basic mathematics book |
| VM41 | Small Deflection of a Rigid Beam | Static | MATRIX27, COMBI250, BEAM188 | any basic statics and strength text |
| VM42 | Barrel Vault Roof Under Self Weight | Static | SHELL181, SHELL281 | Cook, Concepts and Applications of Finite Element Analysis, 2nd ed. (1981), pp. 284-287 |
| VM43 | Bending of an Axisymmetric Thick Pipe | Static, harmonic loading | PLANE25 | Roark, Formulas for Stress and Strain, 4th ed. (1965), p. 112 |
| VM44 | Bending of an Axisymmetric Thin Pipe | Static, harmonic loading | SHELL61 | Roark, 4th ed. (1965), p. 112 |
| VM45 | Natural Frequency of a Spring-Mass System | Modal | COMBIN14, MASS21 | Thomson, Vibration Theory and Applications (1965), p. 6 |
| VM46 | 2D End Notched Flexure Problem | Static, VCCT fracture | PLANE182 | Mandell et al., J. Solar Energy Engineering (2003), pp. 522-530 |
| VM47 | Torsional Frequency of a Suspended Disk | Modal | COMBIN14, MASS21 | Thomson (1965), p. 10 |
| VM48 | Natural Frequency of a Motor-Generator | Modal | BEAM188, MASS21 | Thomson (1965), p. 10 |
| VM49 | Electrostatic Field Analysis of Quadpole Wires | Static electrostatic | PLANE121, INFIN110 | any basic electricity book |
| VM50 | Fundamental Frequency of a Simply Supported Beam | Modal | BEAM189 | Thomson (1965), p. 18 |
| VM51 | Electrostatic Forces Between Charged Spheres | Static electrostatic | SOLID122, SOLID123, INFIN111, PLANE121, MESH200 | any general physics textbook |
| VM52 | Automobile Suspension System Vibration | Modal | BEAM188, COMBIN14, MASS21 | Thomson (1965), p. 181 |
| VM53 | Vibration of a String Under Tension | Static plus perturbed modal | LINK180 | Thomson (1965), p. 264 |
| VM54 | Vibration of a Rotating Cantilever Blade | Static plus perturbed modal | SHELL63, SOLSH190, SHELL181, SHELL281 | Carnegie, J. Mechanical Engineering Science 1(3) (1959), p. 239 |
| VM55 | Vibration of a Stretched Circular Membrane | Perturbed modal | SHELL208 | Timoshenko & Young, Vibration Problems in Engineering, 3rd ed. (1955), p. 439 |
| VM56 | Hyperelastic Thick Cylinder Under Internal Pressure | Static, large deflection | PLANE183, SOLID185, SOLID186 | Oden, Finite Elements of Nonlinear Continua (1972), pp. 325-331 |
| VM57 | Torsional Frequencies of a Drill Pipe | Modal | PIPE16, MASS21, PIPE288, PIPE289, BEAM188, BEAM189 | Thomson (1965), p. 272 |
| VM58 | Centerline Temperature of a Heat Generating Wire | Thermal steady state | PLANE35, SURF151 | Rohsenow & Choi, Heat, Mass and Momentum Transfer (1963), p. 106 |
| VM59 | Lateral Vibration of an Axially-loaded Bar | Static plus perturbed modal | BEAM188 | Timoshenko & Young (1955), p. 374 |
| VM60 | Natural Frequency of a Cross-ply Laminated Shell | Modal | SHELL281 | Reddy, ASCE J. Engineering Mechanics 110(5) (1972), p. 806 |

## Links
[[Ansys]] [[Finite element method]] [[Modal analysis]] [[Thermal stress]] [[Vibration]] [[Hyperelasticity]] [[Fracture mechanics]] [[Electrostatics]] [[Plasticity]] [[Shell elements]] [[Axisymmetric analysis]]

## Flags
- Every case VM31 to VM60 has a companion full APDL input listing page (Hlp_V_VM<N>TXT.html, file vmNN.dat), not read for this extract.
- VM37: the overview element list (SOLID45, SOLID185, SOLSH190) conflicts with the modelling notes bullet list (SOLID95, SOLID186); the results tables follow the overview list. Suspected erratum (VM37).
- VM38: the modelling notes describe a Tresca-based ultimate pressure, but the results table reports only the fully elastic case, and a stray footnote "Output quantity SEQV" attaches to nothing (VM38).
- VM46 and VM51 require supplemental .cdb files (vm46.cdb; vm51_case1.cdb, vm51_case2.cdb) from the 2024 R2 MAPDL test case download; the .dat listing alone does not run (VM46, VM51).
- VM59 cross-references VM50 for the zero-load frequency; both sit inside this slice. No case references outside VM31 to VM60.
- Figure numbering is manual-global: this slice spans Figure 41 (VM31) to Figure 84 (VM60).
- Unread pages: none; all 30 files read in full.
