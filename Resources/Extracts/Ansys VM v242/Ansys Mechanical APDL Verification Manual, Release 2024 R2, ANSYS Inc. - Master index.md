---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
type: master-index
updated: 2026-08-19
tags: [extract, index]
---

## What this source is
The verification manual for Mechanical APDL: 321 test cases plus benchmark studies, each a small model solved against a classical or published target and reported as a ratio, averaging within 1 to 2 % of theory. The cases are a subset of the Ansys QA test library, current to release 2024 R2, so the manual carries ANSYS Inc.'s own quality assurance authority. Four parts: VM1 to VM321 single-feature cases, Part II mesh convergence and element distortion studies, Part III NAFEMS benchmarks, Part IV NRC seismic piping benchmarks. Come here to learn whether an element, command or capability has a validated worked example, which reference it was checked against, and which input deck (vmN.dat, run via /INPUT) reproduces it; the manual states it is verification, not a tutorial.

## Chapter map
- [[Ansys VM - Part I front matter]] - contents, Chapter 1 ground rules (ratio metric, accuracy, input file access), symbol lists, element-number index.
- [[Ansys VM 001-030]] - basic element library on classical statics, plus plasticity, snap-through, random vibration, contact, two utility tests.
- [[Ansys VM 031-060]] - single-feature benchmarks: statics, prestressed modal, electrostatics, VCCT fracture, hyperelasticity, heat generation.
- [[Ansys VM 061-090]] - vibration and dynamics catalogue: modal, transient, harmonic, spectrum, plus Hertz contact and laminated plates.
- [[Ansys VM 091-120]] - thermal core: steady conduction, transients, phase change, radiation links, electrical analogues.
- [[Ansys VM 121-150]] - electromagnetic coil, FLUID116 pipe flow, buckling, creep, fracture, radiation enclosures, substructuring and submodelling.
- [[Ansys VM 151-180]] - magnetics ladder, coupled fields, piezoelectric transducers, acoustics and FSI, analogy methods, a multibody joint.
- [[Ansys VM 181-210]] - electromagnetics, contact algorithms, rubber and viscoelasticity, rotordynamics, XFEM, geomechanics, circuits.
- [[Ansys VM 211-240]] - coupled-field and nonlinear: DDAM shock, migration diffusion, radiosity, piezoelectricity and MEMS, shape memory alloy, joints, APDL Math.
- [[Ansys VM 241-270]] - the Nelson-McVaugh rotor family, delamination, porous acoustics, Gurson, consolidation, spectrum missing mass, TEAM electromagnetic problems.
- [[Ansys VM 271-300]] - contact and wear, the fracture toolset, unbounded domains (PML, infinite elements), acoustics and vibro-acoustics, wind PSD.
- [[Ansys VM 301-321]] - closing cases on newer machinery: multistage cyclic symmetry, harmonic balance, electrostatic-structural pull-in, FGM, sintering, TNM.
- [[Ansys VM - Part II benchmark overview]] - Part II overview plus the VMC convergence and VMD distortion studies; also holds the Part I, III and IV title pages and the NAFEMS and NRC overview chapters (Hlp_V_CH4_1.html, Hlp_V_ch5_1.html).
- [[Ansys VM - NRC piping and misc benchmarks]] - the name understates it: this note holds the true Part III NAFEMS statics (VMFEBSTA, VMLSB2) and free-vibration (VMP09) tests, plus the head of Part IV (pipe element policy and three demonstration problems). It straddles Parts III and IV.
- [[Ansys VM - VMR020 VMR029 VMR031 benchmarks]] - Part III fracture (VMR020), geometric nonlinearity (VMR029), composites (VMR031). Book order runs VMP09-T52 into VMR020-T1A, and VMR020-T8B into the VMR027 series.
- [[Ansys VM - VMR027 VMR049 VMR083 benchmarks]] - Part III creep (VMR027, VMR049-CR), plasticity (VMR049-PL), exterior acoustics (VMR083). Book order: VMR027-12C leads to VMR029-T1, VMR031-T3 to VMR049-CR1, and VMR083-CA2 precedes Part IV.
- [[Ansys VM - NAFEMS benchmarks]] - the name is wrong: this note holds the Part IV NRC piping test cases (VM-NR1677 Vol 1 and Vol 2 series and VM-NR6645 BM3), each in a legacy-element and a current-element build. The true NAFEMS tests sit in the NRC piping and misc note and the two VMR notes.

## Where to find what
| Topic | Chapter | Locator |
| --- | --- | --- |
| **Using the manual** | | |
| Manual contents: Parts I to IV, appendices A to D, VM1 to VM321 | [[Ansys VM - Part I front matter]] | Hlp_V_VMTOC.html |
| Purpose, program history, element library overview | [[Ansys VM - Part I front matter]] | Hlp_V_CH1.html, Hlp_V_CH1_2.html |
| Program verification, QA test library, QA Services subscription | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_3.html |
| Finding test cases; index from element number to test case | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_4.html, Hlp_V_CH1_IDXELEMNUM.html |
| Input file download (VM2024R2_MAPDL.zip), /INPUT usage | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_7.html |
| Expected accuracy (1 to 2 %), ratio metric, machine dependence | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_8.html, Hlp_V_CH1_10.html |
| Case selection, choice of references, fixed case format | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_9.html, Hlp_V_CH1_11.html, Hlp_V_CH1_12.html |
| Symbols, units, figure conventions | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_13.html, Hlp_V_CH1_15_1.html, Hlp_V_CH1_15_2.html |
| Manual versus other documentation; memory and run times | [[Ansys VM - Part I front matter]] | Hlp_V_CH1_6.html, Hlp_V_CH1_14.html |
| **Acoustics and vibro-acoustics** | | |
| Acoustic modal analysis with a step temperature change, FLUID30 | [[Ansys VM 151-180]] | VM157 |
| Submerged ring: unsymmetric FSI modal and harmonic sweep, five element sets | [[Ansys VM 151-180]] | VM177 |
| Fluid coupling hydrodynamic mass, FLUID38 | [[Ansys VM 151-180]] | VM154 |
| Piezoelectric transducer resonance and anti-resonance, PZT4 cube | [[Ansys VM 151-180]] | VM175 |
| Electrical input admittance of a composite transducer near 44 kHz | [[Ansys VM 151-180]] | VM176 |
| Enforced-motion MSUP admittance; reuses the VM176 problem | [[Ansys VM 271-300]] | VM288 |
| Piston-fluid column MSUP harmonic, FSI flag, MPC contact | [[Ansys VM 271-300]] | VM282 |
| Porous absorber: JCA equivalent fluid, impedance-tube absorption | [[Ansys VM 241-270]] | VM242 |
| Surface impedance of a poroelastic glass wool layer | [[Ansys VM 301-321]] | VM306 |
| Visco-thermal (low reduced frequency) fluid: double-wall transmission loss | [[Ansys VM 271-300]] | VM283 |
| Muffler transmission with mean flow at Mach 0.3, FLUID220 | [[Ansys VM 271-300]] | VM297 |
| Room-acoustic diffusion model: flat room SPL; coupled rooms through a partition | [[Ansys VM 271-300]] | VM299, VM300 |
| Sloshing modes of water in a cylindrical cavity, acoustic FSI | [[Ansys VM 301-321]] | VM304 |
| Exterior radiation: pulsating sphere SPL; cylinder directivity at k = 1 and 2 | [[Ansys VM - VMR027 VMR049 VMR083 benchmarks]] | VMR083-CA1, VMR083-CA2 |
| Squeeze-film damping stiffness and damping constants, FLUID136 | [[Ansys VM 241-270]] | VM245 |
| **Vibration: modal analysis** | | |
| Spring-mass frequencies: single mass, suspended disk, motor-generator, car suspension | [[Ansys VM 031-060]] | VM45, VM47, VM48, VM52 |
| Two-mass-spring normal modes and mode shape ratios | [[Ansys VM 061-090]] | VM89 |
| Simply supported beam fundamental frequency | [[Ansys VM 031-060]] | VM50 |
| Prestressed (linear perturbation) modal: string, rotating blade, stretched membrane, axially loaded bar | [[Ansys VM 031-060]] | VM53, VM54, VM55, VM59 |
| Torsional frequencies of a drill pipe, five element types | [[Ansys VM 031-060]] | VM57 |
| Cross-ply laminated shell frequency | [[Ansys VM 031-060]] | VM60 |
| Free-free rod, wedge plate, flat plate, circular ring modes | [[Ansys VM 061-090]] | VM61, VM62, VM66, VM67 |
| Nonaxisymmetric plate and membrane modes: 2D harmonic elements plus 3D cyclic sector | [[Ansys VM 151-180]] | VM151, VM152, VM153 |
| Nonlinear spring-mass frequency by transient integration | [[Ansys VM 151-180]] | VM156 |
| Flat circular plate frequencies, PLANE183 | [[Ansys VM 181-210]] | VM181 |
| Transverse vibration of a shear beam | [[Ansys VM 181-210]] | VM202 |
| Cyclic symmetric annular plate modal, six element types | [[Ansys VM 241-270]] | VM244 |
| Multistage cyclic modal of a thin-walled cylinder, sector counts 18/13/10/11 | [[Ansys VM 301-321]] | VM317 |
| Stress stiffening versus spin softening on a rotating plate | [[Ansys VM 271-300]] | VM281 |
| NAFEMS free-vibration set: crosses, beams, plates, membrane, solid plate | [[Ansys VM - NRC piping and misc benchmarks]] | VMP09-T2, T4, T5, T12, T15, T33, T52 |
| Repeated eigenvalues; rigid body modes (benchmark studies) | [[Ansys VM - Part II benchmark overview]] | VMC4, VMC5 |
| Element distortion effect on frequencies | [[Ansys VM - Part II benchmark overview]] | VMD3 |
| **Rotordynamics** | | |
| Nelson-McVaugh rotor: Campbell diagrams and critical speeds four ways (beams, pipes on orthotropic bearings, internal damping, axisymmetric solids with CMS) | [[Ansys VM 241-270]] | VM247, VM254, VM261, VM263 |
| Rotating elastic system: Campbell diagram, stability thresholds | [[Ansys VM 181-210]] | VM197 |
| Oil film bearing stiffness and damping, COMBI214 and FLUID218 | [[Ansys VM 181-210]] | VM199 |
| Critical speed of a spinning disk; rotating ring with Coriolis | [[Ansys VM 301-321]] | VM301, VM302 |
| **Vibration: transient and harmonic response** | | |
| Spring-mass-damper transients: release at four damping ratios, log decrement, Coulomb damping, impulse, step, bilinear spring, drop container, spring-scale impact | [[Ansys VM 061-090]] | VM71 to VM75, VM79, VM81, VM83 |
| Ball impact on a flexible surface | [[Ansys VM 061-090]] | VM65 |
| Beam with mass under constant force; plastic response to a step force | [[Ansys VM 061-090]] | VM77, VM80 |
| Wave propagation: free-free drill stem; suddenly stopped moving bar | [[Ansys VM 061-090]] | VM84, VM85 |
| Elastic rod impact on a rigid wall, energy-conserving contact | [[Ansys VM 241-270]] | VM265 |
| Harmonic response: viscous versus structural damping, eccentric exciter, two-mass chain | [[Ansys VM 061-090]] | VM86, VM87, VM88, VM90 |
| Guitar string: static, perturbed modal, perturbed harmonic, missing even harmonics | [[Ansys VM 061-090]] | VM76 |
| Spring-mass transient and harmonic by mode superposition | [[Ansys VM 181-210]] | VM182, VM183 |
| Residual vector MSUP harmonic (modal truncation augmentation) | [[Ansys VM 121-150]] | VM149 |
| Prestressed beam frequency response; same problem re-solved through APDL Math (WRFULL, *EIGEN) | [[Ansys VM 211-240]] | VM219, VM235 |
| Harmonic balance method: cyclic oscillator chain (3 harmonics); frictional damper (1 harmonic) | [[Ansys VM 301-321]] | VM319, VM320 |
| Slow dynamics: unequal-stiffness springs | [[Ansys VM 001-030]] | VM9 |
| Slow dynamics: bobbing buoy equilibrium | [[Ansys VM 151-180]] | VM158 |
| Large rotation of a beam pinned at one end, full revolution | [[Ansys VM 031-060]] | VM40 |
| Large rotation of a swinging pendulum | [[Ansys VM 091-120]] | VM91 |
| **Spectrum, PSD and shock** | | |
| Random vibration of a deep simply supported beam, NAFEMS Test 5R | [[Ansys VM 001-030]] | VM19 |
| PSD base excitation of a two-DOF system | [[Ansys VM 061-090]] | VM68 |
| Vibrometer on a displacement spectrum; beam under support motion spectrum | [[Ansys VM 061-090]] | VM69, VM70 |
| Thick plate under white-noise pressure PSD, NAFEMS Test 21R | [[Ansys VM 181-210]] | VM203 |
| DDAM shipboard shock of a two-DOF foundation | [[Ansys VM 211-240]] | VM212 |
| Missing mass and rigid response (Lindley, Gupta) on the NUREG BM3 piping model | [[Ansys VM 241-270]] | VM259 |
| Missing mass in single-point response spectrum | [[Ansys VM 271-300]] | VM284 |
| Wind PSD (Davenport spectrum) on a 40-storey stick model | [[Ansys VM 271-300]] | VM298 |
| **NRC piping seismic benchmarks (Part IV)** | | |
| Pipe element policy: archived PIPE16/PIPE18 versus current PIPE289/ELBOW290; why current results are not compared to NUREG | [[Ansys VM - NRC piping and misc benchmarks]] | vm.ch5.pipben.html, vmnmrc_pipbencur.html |
| Demonstration problems: pipe generations against a SHELL281 reference, modal plus spectrum | [[Ansys VM - NRC piping and misc benchmarks]] | vnmr_prob1.html, vnmr_prob2.html, vnmr_prob3.html |
| NUREG/CR-1677 Vol 1 benchmarks, uniform support spectrum | [[Ansys VM - NAFEMS benchmarks]] | VM-NR1677-01-1 to 01-7, each with -a build |
| NUREG/CR-1677 Vol 2, independent support motion (envelope, SRSS, absolute sum) | [[Ansys VM - NAFEMS benchmarks]] | VM-NR1677-02-1 to 02-4, each with -a build |
| NUREG/CR-6645 BM3, missing mass plus Lindley correction | [[Ansys VM - NAFEMS benchmarks]] | VM-NR6645-01-1, with -a build |
| **Statics: bars, beams, frames** | | |
| Indeterminate bar reactions; thermally loaded support; hinged truss deflection | [[Ansys VM 001-030]] | VM1, VM3, VM4 |
| Beam stresses: WF overhang beam, T-section, bending plus torsion, curved bar out of plane | [[Ansys VM 001-030]] | VM2, VM10, VM12, VM18 |
| Tapered plane-stress cantilever | [[Ansys VM 001-030]] | VM5 |
| Tie rod with lateral load, stress stiffening | [[Ansys VM 001-030]] | VM21 |
| Cable under hanging loads, seed initial strain | [[Ansys VM 031-060]] | VM31 |
| Tapered plate three ways; solid bar elongation; rigid beam by constraint equation | [[Ansys VM 031-060]] | VM34, VM37, VM41 |
| Beam on elastic foundation; parabolic beam | [[Ansys VM 121-150]] | VM135, VM148 |
| Curved beam pure bending against the elasticity solution | [[Ansys VM 151-180]] | VM180 |
| Straight cantilever and curved beam cross-checks of four tet and solid elements | [[Ansys VM 181-210]] | VM184, VM187 |
| Portal frame; warping torsion of a doubly fixed I-beam | [[Ansys VM 211-240]] | VM217, VM222 |
| Function-defined triangular load; end-loaded hollow cylindrical cantilever | [[Ansys VM 241-270]] | VM243, VM246 |
| Crane boom acceleration in rotating frames | [[Ansys VM 121-150]] | VM131 |
| Vector-oriented tapered edge load via SFCONTROL | [[Ansys VM 301-321]] | VM307 |
| NAFEMS linear statics: elliptical membrane; Z-section cantilever plate | [[Ansys VM - NRC piping and misc benchmarks]] | VMFEBSTA-LE1, VMFEBSTA-LE5 |
| **Statics: plates, shells, membranes** | | |
| Pinched cylinder; cylindrical shell and membrane under pressure; Belleville spring | [[Ansys VM 001-030]] | VM6, VM13, VM20, VM22 |
| Circular plate bending, three load cases; solid beam with plane elements | [[Ansys VM 001-030]] | VM15, VM16 |
| Circular plate with centre hole; barrel vault roof; axisymmetric pipes under harmonic gravity | [[Ansys VM 031-060]] | VM39, VM42, VM43, VM44 |
| Long plate membrane-bending coupling; shaft under nonaxisymmetric loading, PLANE83 | [[Ansys VM 121-150]] | VM139, VM140 |
| Transverse shear stresses in a layered cantilever shell | [[Ansys VM 061-090]] | VM78 |
| NAFEMS axisymmetric shells under pressure; axisymmetric solid under thermal field | [[Ansys VM - NRC piping and misc benchmarks]] | VMLSB2-LE8, LE9, LE11 |
| **Buckling and large deflection** | | |
| Eccentric column; snap-through of a hinged shell (arc length); rolled-up cantilever with restart | [[Ansys VM 001-030]] | VM14, VM17, VM26 |
| Euler column by eigenvalue buckling (line and area elements); post-buckled elastica | [[Ansys VM 121-150]] | VM127, VM128, VM136 |
| Large-deflection circular membrane and circular plate | [[Ansys VM 121-150]] | VM137, VM138 |
| Lateral buckling of a right-angle frame with perturbation force | [[Ansys VM 211-240]] | VM216 |
| Torsional buckling of a cruciform beam, warping DOF | [[Ansys VM 301-321]] | VM309 |
| NAFEMS geometric nonlinearity: Z-cantilever, lateral torsional buckling, curved cantilever, spherical shell limit loads, pinched hemisphere | [[Ansys VM - VMR020 VMR029 VMR031 benchmarks]] | VMR029-T1, T4, T5, T7, T9 |
| **Plasticity and hardening** | | |
| Plastic pipe assembly three ways; residual stress; plastic hinge | [[Ansys VM 001-030]] | VM7, VM11, VM24 |
| Limit moment by breakaway hinge elements; thick cylinder under pressure | [[Ansys VM 031-060]] | VM36, VM38 |
| Plastic bending of a clamped I-beam, bilinear kinematic hardening | [[Ansys VM 121-150]] | VM134 |
| Chaboche rate-dependent plasticity under cyclic loading | [[Ansys VM 151-180]] | VM155 |
| Large strain in-plane torsion; MAP2DTO3D extrusion | [[Ansys VM 181-210]] | VM198 |
| Necking of an imperfect circular bar, 2D and 3D | [[Ansys VM 301-321]] | VM318 |
| Gurson porous plasticity: bar necking; hydrostatic tension | [[Ansys VM 241-270]] | VM252, VM253 |
| NAFEMS plasticity: plane strain, plane stress, 3D, pressurised cylinder | [[Ansys VM - VMR027 VMR049 VMR083 benchmarks]] | VMR049-PL1, PL2, PL3, PL5 |
| Bar impact plasticity (benchmark study) | [[Ansys VM - Part II benchmark overview]] | VMC8 |
| **Creep** | | |
| Bolt stress relaxation (Norton); irradiation-induced creep | [[Ansys VM 121-150]] | VM132, VM133 |
| Implicit creep under biaxial load, NAFEMS R0027 Test 10a | [[Ansys VM 211-240]] | VM224 |
| NAFEMS creep squares: secondary, primary, stepped load, combined law, shear, plane strain, 3D | [[Ansys VM - VMR027 VMR049 VMR083 benchmarks]] | VMR027-3A, 3B, 4C, 5B, 6B, 10A, 10B, 10C, 12B, 12C |
| NAFEMS creep: constant load, constant displacement, variable load, pressurised cylinder, torsion, thermally induced | [[Ansys VM - VMR027 VMR049 VMR083 benchmarks]] | VMR049-CR1 to CR6 |
| **Hyperelasticity, viscoelasticity, rubber** | | |
| Hyperelastic thick cylinder, Mooney-Rivlin near incompressibility | [[Ansys VM 031-060]] | VM56 |
| Hyperelastic circular plate, four shell formulations | [[Ansys VM 211-240]] | VM218 |
| Bergstrom-Boyce rubber relaxation; viscoelastic sandwich seal | [[Ansys VM 181-210]] | VM189, VM200 |
| Ogden viscoelastic rubber block under cyclic load | [[Ansys VM 211-240]] | VM234 |
| Neo-Hookean tube and sphere; Mullins softening of a rubber tube | [[Ansys VM 241-270]] | VM268, VM269 |
| Rubber cylinder pressed between plates | [[Ansys VM 181-210]] | VM201 |
| Same rubber cylinder re-solved twelve ways (contact algorithm and element matrix) | [[Ansys VM 211-240]] | VM211 |
| **Advanced material models** | | |
| Shape memory alloy: load, unload, heat to recover | [[Ansys VM 211-240]] | VM221 |
| Shape memory alloy superelastic hysteresis loop | [[Ansys VM 241-270]] | VM251 |
| Shape memory alloy with thermal effect, tension-compression cycle | [[Ansys VM 271-300]] | VM273 |
| Gasket pressure-closure response, 2D and 3D | [[Ansys VM 241-270]] | VM249, VM250 |
| Three Network polymer model, UHMWPE tension | [[Ansys VM 301-321]] | VM314 |
| SOVS free sintering of a ZnO bar | [[Ansys VM 301-321]] | VM315 |
| Functionally graded materials: plate via TBIN; conduction in cylinder and sphere via TBFIELD | [[Ansys VM 301-321]] | VM305, VM308 |
| Anisotropic elasticity: matrix input versus MP constants | [[Ansys VM 121-150]] | VM145 |
| Reinforced concrete beam cracking with discrete reinforcement | [[Ansys VM 121-150]] | VM146 |
| **Contact, friction, wear** | | |
| Friction block sticking-sliding transition; heated bar closing a gap | [[Ansys VM 001-030]] | VM27, VM29 |
| Thermal-structural contact of two bodies, interface conductance | [[Ansys VM 001-030]] | VM23 |
| Hertz contact of a sphere on a rigid plane; thermal gap closure at a rigid surface | [[Ansys VM 061-090]] | VM63, VM64 |
| Hertz contact between two cylinders, augmented Lagrangian versus Lagrange multiplier | [[Ansys VM 181-210]] | VM191 |
| 2D and 3D frictional Hertz contact, surface-projection option | [[Ansys VM 271-300]] | VM272 |
| Interference fit with contact geometry correction | [[Ansys VM 271-300]] | VM292 |
| Pipe on rigid ground, traction-based line contact | [[Ansys VM 271-300]] | VM278 |
| Crossing beams in frictional contact, force and traction based | [[Ansys VM 241-270]] | VM266 |
| Archard wear of a block under compression and sliding | [[Ansys VM 271-300]] | VM286 |
| Squeal: stabilising damping via FDMS; pin-disc mode lock-in, three procedures | [[Ansys VM 271-300]] | VM274, VM275 |
| Frictional heating of sliding blocks, two formulations | [[Ansys VM 211-240]] | VM229 |
| **Fracture mechanics** | | |
| VCCT energy release rate: end notched flexure | [[Ansys VM 031-060]] | VM46 |
| VCCT double cantilever beam with contact-paired faces | [[Ansys VM 151-180]] | VM178 |
| K_I by displacement extrapolation (KCALC) and J-integral, 2D and 3D | [[Ansys VM 121-150]] | VM143 |
| Centre crack fracture parameters: K, J, material force, T-stress | [[Ansys VM 241-270]] | VM256 |
| T-stress via CINT, plane strain 2D and 3D | [[Ansys VM 271-300]] | VM279 |
| Fracture under thermal gradient; mixed-mode inclined crack | [[Ansys VM 241-270]] | VM262, VM267 |
| XFEM: SIFs of an inclined crack without conforming mesh | [[Ansys VM 181-210]] | VM193 |
| XFEM initial crack-growth angle in pure shear | [[Ansys VM 271-300]] | VM287 |
| Unstructured mesh method (UMM): edge crack SIF on degenerate meshes | [[Ansys VM 211-240]] | VM232 |
| UMM: K_I along a penny-shaped crack front, SOLID285 | [[Ansys VM 271-300]] | VM293 |
| C* integral for creep crack growth | [[Ansys VM 271-300]] | VM285 |
| Elastic-plastic J-integral against EPRI estimation | [[Ansys VM 301-321]] | VM316 |
| Delamination: cohesive-zone interface elements versus contact-based debonding, same beam | [[Ansys VM 241-270]] | VM248, VM255 |
| NAFEMS 2D fracture family: centre, edge, angled, hole, axisymmetric bar, compact tension, V-notch (T3B and T3C source files carry each other's content) | [[Ansys VM - VMR020 VMR029 VMR031 benchmarks]] | VMR020-T1A, T1B, T2A, T2B, T3A, T3B, T3C, T4A, T4B, T5, T6, T8A, T8B |
| **Composites and layered structures** | | |
| Laminated plate under pressure against Reddy's exact solution, five element types | [[Ansys VM 061-090]] | VM82 |
| Composite beam bending, four element formulations | [[Ansys VM 121-150]] | VM144 |
| Bimetallic layered cantilever plate under thermal load | [[Ansys VM 031-060]] | VM35 |
| NAFEMS composites: laminated strip, wrapped cylinder (pressure and thermal), sandwich shell | [[Ansys VM - VMR020 VMR029 VMR031 benchmarks]] | VMR031-T1, T2, T3 |
| **Thermal: steady conduction** | | |
| 1D chains: insulated wall, k(T), heat-generating plate, cooling spine | [[Ansys VM 091-120]] | VM92 to VM95 |
| Fins: straight, tapered, trapezoidal | [[Ansys VM 091-120]] | VM97, VM98, VM99 |
| Solid cylinders and chimney section, 3D and sector models | [[Ansys VM 091-120]] | VM96, VM100, VM101, VM102 |
| Thin plate with central heat source, thermal shells | [[Ansys VM 091-120]] | VM103 |
| Heat-generating wire centreline temperature | [[Ansys VM 031-060]] | VM58 |
| Heat-generating coil with temperature-dependent conductivity | [[Ansys VM 091-120]] | VM105 |
| Harmonic (mode 1) temperature on axisymmetric-harmonic elements | [[Ansys VM 091-120]] | VM108 |
| Harmonic (mode 2) temperature, PLANE78 | [[Ansys VM 151-180]] | VM160 |
| Insulated pipe heat flow; circular fin of rectangular profile | [[Ansys VM 151-180]] | VM161, VM162 |
| Doubly insulated steam pipe; hollow cylinder with fluid flow convection (FLUID116 plus SURF152) | [[Ansys VM 271-300]] | VM280, VM271 |
| Reinforced block conduction six ways (REINF264, embedded LINK33, LINK228) | [[Ansys VM 301-321]] | VM303 |
| Analogy methods: groundwater seepage; slab drying by diffusion | [[Ansys VM 151-180]] | VM163, VM164 |
| Steady conduction with convection, convergence study | [[Ansys VM - Part II benchmark overview]] | VMC6 |
| **Thermal: transient** | | |
| Semi-infinite slab under sudden convection | [[Ansys VM 001-030]] | VM28 |
| Cooled wire, slab, spheres, orthotropic bar, ramped and temperature-dependent h; ITS rule delta^2/4alpha | [[Ansys VM 091-120]] | VM109 to VM116 |
| Liquid-solid phase change by enthalpy method | [[Ansys VM 091-120]] | VM104 |
| Temperature-controlled heater, COMBIN37 switching | [[Ansys VM 151-180]] | VM159 |
| Transient conduction with time-step optimisation (benchmark study) | [[Ansys VM - Part II benchmark overview]] | VMC7 |
| **Thermal radiation** | | |
| Radiant emission; thermocouple radiation, LINK31 | [[Ansys VM 091-120]] | VM106, VM107 |
| AUX12 view factor matrices: concentric cylinders; gray-body frustum | [[Ansys VM 121-150]] | VM125, VM147 |
| Radiosity method: finite and infinite coaxial cylinders, concentric spheres | [[Ansys VM 211-240]] | VM227, VM228, VM230 |
| Billet cooling by radiation, one-element model | [[Ansys VM 181-210]] | VM192 |
| Radiosity with moving geometry, view factor updates | [[Ansys VM 301-321]] | VM321 |
| **Coupled thermal-structural and thermal-electric** | | |
| Thermal stresses in a long cylinder; transient thermal stress, coupled field | [[Ansys VM 031-060]] | VM32, VM33 |
| Bimetallic beam under thermal load, coupled field | [[Ansys VM 151-180]] | VM174 |
| Joule heating of a wire: heat-generation form versus coupled thermal-electric | [[Ansys VM 091-120]] | VM118, VM119 |
| Electrical wire centreline temperature, SOLID5 | [[Ansys VM 151-180]] | VM173 |
| Thermal-electric hemispherical shell; electro-thermal microactuator | [[Ansys VM 211-240]] | VM215, VM223 |
| Thermoplastic cylinder expansion, Taylor-Quinney heating | [[Ansys VM 271-300]] | VM296 |
| Electric current network: conduction elements and CIRCU124 | [[Ansys VM 091-120]] | VM117 |
| **Electromagnetics and electrostatics** | | |
| Electrostatics: quadpole wires with infinite elements; charged spheres | [[Ansys VM 031-060]] | VM49, VM51 |
| Microstrip capacitance from field energy | [[Ansys VM 091-120]] | VM120 |
| Voltage-forced stranded coil transient, SOLID236 | [[Ansys VM 121-150]] | VM121 |
| Magnetics ladder: nonlinear B-H conductor, harmonic and transient eddy currents, solenoid source field, permanent magnet circuit, Biot-Savart loop | [[Ansys VM 151-180]] | VM165 to VM170 |
| Magneto-structural coupling: relay with elastic keeper; solenoid hoop stress | [[Ansys VM 151-180]] | VM171, VM172 |
| Slot conductor AC and transient; conductor force; ferromagnetic inductor (GSP) | [[Ansys VM 181-210]] | VM185, VM186, VM188, VM190 |
| Stranded coil: voltage excitation; external circuit drive | [[Ansys VM 181-210]] | VM206, VM207 |
| Differential inductance; moving conductor EMF; TEAM 20 solenoid force (DSP) | [[Ansys VM 211-240]] | VM213, VM214, VM233 |
| TEAM 20 with edge elements; TEAM 23 permanent magnet forces | [[Ansys VM 241-270]] | VM241, VM270 |
| Hall plate in a uniform magnetic field | [[Ansys VM 271-300]] | VM277 |
| **Piezoelectricity, piezoresistivity, MEMS** | | |
| Piezoelectric strip in pure bending, three element types | [[Ansys VM 211-240]] | VM231 |
| RLC circuit with piezoelectric transducer; piezoresistive Wheatstone bridge | [[Ansys VM 211-240]] | VM237, VM238 |
| Electrostatic pull-in and release hysteresis of a clamped beam | [[Ansys VM 211-240]] | VM236 |
| Electrostatic-structural pull-in family: parallel plate, cylindrical, spherical, fixed-fixed beam | [[Ansys VM 301-321]] | VM310 to VM313 |
| **Circuits** | | |
| RL circuit with controlled source | [[Ansys VM 181-210]] | VM208 |
| Diode-rectified circuit Fourier analysis, CIRCU125 | [[Ansys VM 271-300]] | VM294 |
| **Fluid flow, diffusion, porous media** | | |
| FLUID116 pipe networks: turbulent drop, laminar fittings, reservoir discharge, heated flow | [[Ansys VM 121-150]] | VM122, VM123, VM124, VM126 |
| Moisture diffusion under constant surface concentration | [[Ansys VM 121-150]] | VM150 |
| Moisture diffusion under constant flux, normalised concentration | [[Ansys VM 271-300]] | VM276 |
| Electromigration and 1D advection-diffusion, migration model (TB,MIGR) | [[Ansys VM 211-240]] | VM220, VM226 |
| Consolidation: Schiffman 2D; Terzaghi 1D, CPT elements | [[Ansys VM 241-270]] | VM260, VM264 |
| Terzaghi consolidation with depth-varying permeability | [[Ansys VM 271-300]] | VM295 |
| Hydrostatic fluid air spring, GAS and PVDATA options | [[Ansys VM 181-210]] | VM209 |
| **Geomechanics** | | |
| Mohr-Coulomb earth pressure to the active state | [[Ansys VM 181-210]] | VM205 |
| **Unbounded domains** | | |
| Pressurised spherical cavity: PML truncation; INFIN257 infinite elements | [[Ansys VM 271-300]] | VM289, VM290 |
| Boussinesq point load on a half space | [[Ansys VM 271-300]] | VM291 |
| **Multibody, joints, mechanisms** | | |
| Jointed beam with revolute joint, friction torque and lock, mid-run restart | [[Ansys VM 151-180]] | VM179 |
| Toggle mechanism with MPC184 | [[Ansys VM 181-210]] | VM195 |
| Revolute and universal joints; rigid beams in a composite bar | [[Ansys VM 211-240]] | VM239, VM240 |
| Swing with rigid links; spin-up of a flexible beam | [[Ansys VM 241-270]] | VM257, VM258 |
| **Procedures, APDL scripting, meshing** | | |
| Parametric macro arithmetic with *CREATE, no elements | [[Ansys VM 001-030]] | VM8 |
| Numerical differentiation and integration (*VOPER); Fourier series generation, APDL only | [[Ansys VM 121-150]] | VM129, VM130 |
| Substructuring; submodelling with CBDOF interpolation | [[Ansys VM 121-150]] | VM141, VM142 |
| Inertia relief three ways, including CMS superelement retrieval | [[Ansys VM 181-210]] | VM196 |
| Element birth and death, strain-free rebirth | [[Ansys VM 181-210]] | VM194 |
| Bolt pretension via PRETS179 sections and SLOAD | [[Ansys VM 211-240]] | VM225 |
| Solid-model Boolean accuracy: surface fillet | [[Ansys VM 001-030]] | VM30 |
| Solid-model Boolean accuracy: axial bearing | [[Ansys VM 181-210]] | VM204 |
| Hex-tet pyramid transition under pure bending | [[Ansys VM 181-210]] | VM210 |
| **Benchmark studies (Part II)** | | |
| Overview: purpose, deliberate improper modelling, format, running inputs, energy error norm, coverage index | [[Ansys VM - Part II benchmark overview]] | Hlp_V_CH2_1.html to Hlp_V_CH2_5.html, Hlp_V_CH2Ind.html |
| Convergence studies: built-in plate, elliptic membrane, barrel vault roof | [[Ansys VM - Part II benchmark overview]] | VMC1, VMC2, VMC3 |
| Element distortion: cantilever shape matrix; skewed barrel vault meshes | [[Ansys VM - Part II benchmark overview]] | VMD1, VMD2 |
| Part title pages and the NAFEMS and NRC overview chapters | [[Ansys VM - Part II benchmark overview]] | vm.testcases.html, vm_nafems.html, vm_nrcbench.html, Hlp_V_CH4_1.html, Hlp_V_ch5_1.html |

## Start here
- [[Ansys VM - Part I front matter]]: the element-number index (Hlp_V_CH1_IDXELEMNUM.html) is the fastest route from any element in a working model to its validated cases, and Hlp_V_CH1_7.html gives the /INPUT discipline for running the decks as scripts.
- [[Ansys VM 061-090]]: the vibration workbench; modal, transient, harmonic and spectrum recipes on COMBIN40, MASS21, LINK180 and BEAM188 models small enough to lift into MAPDL scripts.
- [[Ansys VM 271-300]]: the acoustics and vibro-acoustics concentration; transmission loss, muffler with mean flow, room diffusion models, PML and infinite elements, plus missing mass and wind PSD spectrum methods.

## Not yet extracted
- All four parts and the 321 cases are covered by the seventeen extract notes; the manual holds VM1 to VM321 with no gaps in numbering.
- Deliberately left unextracted: the APDL input listing pages (every Hlp_V_VM(N)TXT.html and *txt.html companion) and appendices A to D, which hold input listings only.
- Absent from this HTML build itself, not extraction gaps: VMR020-T7 and VMR049-PL4.
