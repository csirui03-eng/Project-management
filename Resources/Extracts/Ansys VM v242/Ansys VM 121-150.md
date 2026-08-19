---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM121-VM150
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification test cases, each a one-page recipe: reference solution, element type, analysis type, input listing, and a target-versus-APDL results table with ratios. The slice is a mixed bag by design. It opens with a voltage-forced electromagnetic coil (VM121), runs a FLUID116 pipe-flow set (VM122 to VM126), then works through classical structural mechanics: Euler buckling three ways (VM127, VM128, VM136), creep (VM132, VM133), plasticity (VM134, VM146), large-deflection shells (VM137 to VM139), and stress concentration and fracture (VM142, VM143). Two pure-APDL maths cases use no elements at all (VM129, VM130). It closes with radiation enclosures (VM125, VM147), substructuring and submodelling procedure demonstrations (VM141, VM142), residual-vector harmonic response (VM149), and moisture diffusion (VM150). Most references are Timoshenko volumes; the job of the slice is to certify individual element and procedure capabilities against textbook closed forms.

## Key ideas
- A voltage step on a stranded coil (SOLID236, KEYOPT(1)=2 giving AZ, VOLT, EMF) reproduces coil current histories from the IEEE reference within 0.5 percent, with and without eddy-current plates (VM121).
- FLUID116 coupled thermal-fluid pipe elements handle turbulent pressure drop (VM122), laminar flow with equivalent-length fittings (VM123), gravity-driven reservoir discharge (VM124), and conjugate heat pickup with a flow-dependent film coefficient (VM126); all need iterative solutions seeded with a guessed friction factor.
- The same hinged Euler column is certified by eigenvalue buckling with BEAM188 (VM127), with PLANE182 enhanced-strain solids (VM128), and by tracing the post-buckled elastica with large deflection (VM136).
- APDL alone, no mesh: `*VOPER` differentiates and integrates a sampled sine (VM129) and builds Fourier coefficients of a saw tooth (VM130).
- Creep is verified both as explicit stress relaxation of a bolt under Norton law (VM132) and as implicit irradiation-induced creep via TB,CREEP generalised exponential (VM133).
- Bilinear kinematic hardening tracks a clamped I-beam through first yield, mid-span yield, and pronounced plastic flow at three load levels (VM134).
- SHELL208 axisymmetric shells solve pressure-loaded membrane and plate large-deflection problems; the membrane needs a thermal prestress load step for stability because it has no bending stiffness (VM137, VM138).
- SHELL181 and SOLSH190 show the membrane-bending coupling a small-deflection solution misses in a long pressurised plate (VM139).
- PLANE83 axisymmetric-harmonic elements take nonaxisymmetric bending, torsion, and axial load on one model (VM140).
- Procedure demonstrations: substructure generation and expansion (VM141), submodelling with cut-boundary interpolation CBDOF (VM142), and KI by both KCALC displacement extrapolation and J-integral in 2D and 3D (VM143).
- One composite-beam problem returns identical answers from four element formulations: SOLID185, layered SOLID186, layered SOLSH190, and offset-nodal-plane SHELL281 pairs (VM144).
- Anisotropic elasticity accepts the same orthotropic data as a flexibility matrix (TB, TBOPT=1) or as labelled MP constants, one element each (VM145).
- SOLID65 concrete cracking with discrete LINK180 reinforcement brackets the theoretical crack depth between integration-point rows (VM146).
- AUX12 radiation matrices are verified for a two-cylinder enclosure (VM125) and a three-surface gray frustum using the non-hidden view factor method (VM147).
- Residual-vector mode-superposition harmonic analysis reproduces the reference's modal truncation augmentation results with one extracted mode (VM149).
- SOLID239 diffusion elements track transient moisture concentration and total weight gain against Crank's series solution (VM150).

## Equations that matter
The manual numbers none of its equations; anchors are the VM case.

$$\mathrm{Nu} = 0.08\,\mathrm{Re}^{0.7}\,\mathrm{Pr}^{0.35} + 1.63$$
Film coefficient correlation supplied as the flow-dependent property table for the heated tube (VM126).

$$\frac{d\varepsilon}{dt} = k\,\sigma^{n}, \qquad k = 4.8\times10^{-30}\ \mathrm{hr^{-1}},\ n = 7$$
Norton creep law driving bolt stress relaxation from an initial strain $\sigma_o/E = 1/30000$ (VM132).

$$\frac{d\varepsilon_{cr}}{dt} = k_1\,\sigma\,\Phi\,e^{-\Phi t/k_2}$$
Irradiation-induced creep rate, mapped onto the TB,CREEP generalised exponential constants C1 to C5 (VM133).

$$F_{cr} = \frac{\pi^2 E I}{4\ell^2} = 38.553\ \mathrm{lb}$$
Euler load of the half-symmetry free-fixed column; the target for VM127 and VM128 and the load normaliser for the elastica steps $F/F_{cr}$ = 1.015 to 1.884 (VM136).

## Numbers worth citing
- Worst pipe-network match in the slice: reservoir discharge flow ratio 1.036 and Reynolds number ratio 1.035 (target Re $1.94\times10^5$) (VM124).
- Stefan-Boltzmann constant defaults to $0.119\times10^{-10}$ Btu/hr-in²-°R⁴ in the concentric-cylinder case; heat rate ratio 0.984 on a 100 in cylinder length basis (VM125).
- Implicit irradiation creep runs a steady 5 percent low: creep strain ratio 0.950 at t = 0.5, 1.0 and 5.0 hr (VM133).
- Large-deflection plate stresses undershoot: SHELL181 bottom-fibre ratio 0.955 and SOLSH190 0.973 against the 25,280 psi target (VM139).
- Coarse-mesh hole stress ratio 0.902 versus submodel 0.986 (target 3018 psi); discretisation-error bounds quoted as 2855 to 3076 psi, and the manual warns coarse PLANE183 results vary across platforms (VM142).
- Fracture target $K_I$ = 1.0249; all six method-element combinations land between ratio 1.020 and 1.036, displacement extrapolation running higher than J-integral (VM143).
- Concrete crack depth is reported only as a bracket, 3.32 to 4.18 in against the 3.49 in target, set by integration-point spacing; steel stress ratio 1.000 at 387.28 psi (VM146).
- Stefan-Boltzmann constant entered as $5.6696\times10^{-8}$ W/m²-K⁴ for the frustum enclosure; T1 ratio 1.003 at 904 K target (VM147).
- Peak displacement ratio 1.106 and second force peak ratios 1.049 and 0.952; the manual notes targets were read off reference figures, so accuracy is limited (VM149).

## Definitions introduced
- Stranded coil option - SOLID236 KEYOPT(1)=2, carrying AZ, VOLT and EMF degrees of freedom for a voltage-forced winding (VM121).
- Non-hidden method - VTYPE view factor computation valid when every radiating surface fully sees every other, no blocking (VM147).
- Cut-boundary interpolation - CBDOF in POST1 maps coarse-model displacements onto the submodel boundary (VM142).
- Displacement extrapolation - KCALC route to the stress intensity factor from near-tip crack face displacements, alternative to the J-integral (VM143).
- Residual vector - RESVEC augmentation of a truncated mode set in mode-superposition harmonic analysis; equivalent to the reference's modal truncation method (VM149).

## Figures and tables to return to
- Fig. 174 - coil current versus time against the reference paper's Figure 4, both plate and free-space cases (VM121).
- Fig. 183 - saw tooth wave overlaid with its 24-term Fourier reconstruction (VM130).
- Fig. 190 - elastica deformed shapes at six load ratios overlaid via /NOERASE (VM136).
- Figs. 197 and 198 - stress concentration fields, coarse model versus submodel, the visual argument for submodelling (VM142).
- Figs. 206 and 207 - displacement and spring force amplitude versus frequency for full modal set and one-mode-plus-residual runs (VM149).
- Figs. 209 and 210 - concentration and moisture weight gain histories against Crank's series (VM150).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM121 | Voltage Forced Coil | Transient electromagnetic (ANTYPE=4) | SOLID236 | Leonard and Rodger, IEEE Trans. Magnetics 24(6), 1988 |
| VM122 | Pressure Drop in a Turbulent Flowing Fluid | Thermal (pressure) static (ANTYPE=0) | FLUID116 | Binder, Fluid Mechanics, 3rd ed., 1956 |
| VM123 | Laminar Flow in a Piping System | Thermal (pressure) static | FLUID116 | Crane Co. Technical Paper 410, 1969 |
| VM124 | Discharge of Water from a Reservoir | Thermal (pressure) static | FLUID116 | Brenkert, Elementary Theoretical Fluid Mechanics, 1960 |
| VM125 | Radiation Heat Transfer Between Concentric Cylinders | Thermal static plus AUX12 view factors | LINK33, MATRIX50 | Kreith, Principles of Heat Transfer, 1959 |
| VM126 | Heat Transferred to a Flowing Fluid | Thermal (fluid flow) static | FLUID116 | Rohsenow and Choi, Heat, Mass and Momentum Transfer, 1963 |
| VM127 | Buckling of a Bar with Hinged Ends (Line Elements) | Linear perturbed buckling (ANTYPE=1) | BEAM188 | Timoshenko, Strength of Materials II, 1956 |
| VM128 | Buckling of a Bar with Hinged Ends (Area Elements) | Linear perturbed buckling (ANTYPE=1) | PLANE182 | Timoshenko, Strength of Materials II, 1956 |
| VM129 | Numerical Differentiation and Integration | APDL *VOPER only, no FE model | none | any basic calculus book |
| VM130 | Fourier Series Generation for a Saw Tooth Wave | APDL only, no FE model | none | Timoshenko and Young, Vibration Problems in Engineering, 1955 |
| VM131 | Acceleration of a Rotating Crane Boom | Static (ANTYPE=0), rotating frames | MASS21 | Beer and Johnston, Vector Mechanics for Engineers, 1962 |
| VM132 | Stress Relaxation of a Tightened Bolt Due to Creep | Static with creep and initial strain | LINK180 | Timoshenko, Strength of Materials II, 1956 |
| VM133 | Motion of a Rod Due to Irradiation Induced Creep | Static with implicit creep | BEAM188 | any basic calculus book |
| VM134 | Plastic Bending of a Clamped I-Beam | Static plastic, bilinear kinematic hardening | BEAM188 | Hoff, The Analysis of Structures, 1956 |
| VM135 | Bending of a Beam on an Elastic Foundation | Static | BEAM189, SURF156 | Timoshenko, Strength of Materials II, 1956 |
| VM136 | Large Deflection of a Buckled Bar (the Elastica) | Static, large deflection | BEAM188 | Timoshenko and Gere, Theory of Elastic Stability, 1961 |
| VM137 | Large Deflection of a Circular Membrane | Static, large deflection, stress stiffening | SHELL208 | Timoshenko and Woinowsky-Krieger, Theory of Plates and Shells, 1959 |
| VM138 | Large Deflection Bending of a Circular Plate | Static, large deflection, stress stiffening | SHELL208 | Timoshenko and Woinowsky-Krieger, Theory of Plates and Shells, 1959 |
| VM139 | Bending of a Long Uniformly Loaded Rectangular Plate | Static, small and large deflection | SHELL181, SOLSH190 | Timoshenko, Strength of Materials II, 1956 |
| VM140 | Stretching, Twisting and Bending of a Long Shaft | Static, nonaxisymmetric loading | PLANE83 | Timoshenko, Strength of Materials I, 1955 |
| VM141 | Diametral Compression of a Disk | Static plus substructure (ANTYPE=7) | PLANE82, PLANE183, MATRIX50, SHELL181, SHELL281 | Timoshenko and Goodier, Theory of Elasticity, 1951 |
| VM142 | Stress Concentration At a Hole in a Plate | Static with submodelling | PLANE182, PLANE183 | Roark, Formulas for Stress and Strain, 4th ed., 1965 |
| VM143 | Fracture Mechanics Stress for a Crack in a Plate | Static, KCALC and J-integral | SOLID95, SOLID45, PLANE183, SOLID186, SOLID185 | Brown and Srawley, ASTM STP-410, 1966 |
| VM144 | Bending of a Composite Beam | Static, layered, thermal plus end moment | SOLID185, SOLID186, SOLSH190, SHELL281 | Roark and Young, Formulas for Stress and Strain, 1975 |
| VM145 | Stretching of an Orthotropic Solid | Static, anisotropic matrix input | SOLID185 | Crandall and Dahl, Mechanics of Solids, 1959 |
| VM146 | Bending of a Reinforced Concrete Beam | Static, cracking nonlinearity | SOLID65, LINK180, PIPE288 | Timoshenko, Strength of Materials I, 1955 |
| VM147 | Gray-Body Radiation within a Frustum of a Cone | Thermal static plus AUX12 view factors | LINK33, SURF151, MATRIX50 | Siegel and Howell, Thermal Radiation Heat Transfer, 1981 |
| VM148 | Bending of a Parabolic Beam | Static | SOLID95, SOLID186 | Timoshenko, Strength of Materials I, 1955 |
| VM149 | Residual Vector in Mode-Superposition Harmonic Analysis | Modal (ANTYPE=2) plus harmonic (ANTYPE=3) | COMBIN14, MASS21 | Dickens, Nakagawa and Wittbrodt, Computers and Structures 62, 1997 |
| VM150 | Moisture Diffusion in a Plate Under Constant Surface Concentration | Transient diffusion (ANTYPE=4) | SOLID239 | Crank, The Mathematics of Diffusion, 1975 |

## Links
[[Ansys VM index]], [[Euler buckling]], [[Creep]], [[Plasticity]], [[Fracture mechanics]], [[Pipe flow]], [[Thermal radiation]], [[Large deflection shells]], [[Composite beams]], [[Orthotropic elasticity]], [[Modal superposition]], [[Substructuring]], [[Submodelling]], [[Moisture diffusion]], [[Electromagnetics]]

## Flags
- Every case has a companion input-listing page (Hlp_V_VM(N)TXT.html, file vm(N).dat) with the full APDL deck; not read in this pass.
- Source is HTML with no page numbers; VM case numbers serve as locators throughout, per slice instructions.
- Suspected erratum: VM147 prints the Stefan-Boltzmann units as W/m²-K, missing the fourth power on temperature (VM147).
- Suspected erratum: VM137 and VM138 spell the reference author "Woinowsky-Knieger"; standard spelling is Woinowsky-Krieger.
- Typesetting garbles in property tables: "c = 1.002 x 18⁸" for specific heat and a broken flow-rate unit (VM126); "w = 2.345 slugs/se/sec" (VM123); "A = 0.25 in 2" (VM128).
- VM134 results table reuses the "End Status"/"Mid Status" row labels at w3 to hold total strain values 0.0200 and 0.0089 rather than status words.
- Inline length symbols (script l) render as SVG images in the HTML and are lost to text extraction; dimensions were recovered from context.
- VM138 problem sketch reuses the VM137 graphic file (gvm137-1.svg); the geometry differs, so treat the sketch as schematic only.
- No case in this slice explicitly cross-references a case outside VM121 to VM150; the slice is self-contained.
