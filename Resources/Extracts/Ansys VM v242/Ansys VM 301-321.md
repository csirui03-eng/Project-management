---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc. (HTML build)
pages: VM301-VM321
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Final 21 test cases of the manual, closing Part I. The slice leans on newer solver machinery: linear perturbation chains for rotating structures (VM301, VM302), reinforcing and embedded thermal elements (VM303), acoustic FSI sloshing and poroelastic impedance (VM304, VM306), field-variable material tables for functionally graded materials (VM305, VM308), follower edge loads via SFCONTROL (VM307), warping-DOF torsional buckling (VM309), a four-case electrostatic-structural pull-in family on SOLID226 (VM310 to VM313), the Three Network polymer model (VM314), SOVS sintering (VM315), elastic-plastic J-integral (VM316), multistage cyclic symmetry (VM317, VM319), the harmonic balance method for nonlinear harmonics (VM319, VM320), necking with Neo-Hookean plus Voce hardening (VM318), and radiosity radiation with moving-geometry view factor updates (VM321). Each case states reference, analysis type, elements, input listing, model data, modelling notes, and a target-versus-APDL ratio table.

## Key ideas
- Critical speed of a clamped-centre spinning disk from a Campbell diagram at twice-spin excitation; Coriolis omitted because flexural motion lies along the spin axis (VM301).
- Free-free rotating ring: stress stiffening, spin softening, and Coriolis split the in-plane modes; contact elements apply the prestress in the base static solve (VM302).
- Non-conducting block with a heat-generating conducting bar solved six ways: REINF264, embedded LINK33, and thermal-electric LINK228 with Joule heating tuned to match the direct heat load (VM303).
- Sloshing modes of water above a steel cylinder with acoustic FSI; free surface plus rigid lateral wall; modes labelled (i nodal circles, j nodal diameters) (VM304).
- FGM plate with exponentially varying Young's modulus built from 15 interpolation points via TBIN,ALGO; plane strain uniaxial tension (VM305).
- Surface impedance of a 10 cm glass wool layer (porosity 0.94, tortuosity 1.06) under a unit normal-incidence plane wave, harmonic sweep to 1200 Hz in four substeps (VM306).
- Vector-oriented tapered edge load with tangential component excluded (SFCONTROL, KCSYS = 2, KPROJ = 2) under large deflection (VM307).
- FGM hollow cylinder and sphere with conductivity linear in radius, done through TBFIELD,XCOR and a user field variable set by INISTATE (VM308).
- Purely torsional buckling of a doubly symmetric cruciform beam; warping DOF active, unconstrained (VM309).
- Parallel-plate MEMS capacitor: arc-length method traces the displacement-voltage curve through pull-in and back down; linear perturbation static, modal, and harmonic runs from a DC bias (VM310).
- Cylindrical capacitor, same recipe but voltage-controlled with CUTCONTROL,ULIMIT bisection instead of arc length (VM311).
- Spherical capacitor variant of the same family; poorest lin-pert ratios of the three (VM312).
- Fixed-fixed beam actuator: pull-in voltage taken as the last converged voltage using NCNV,2; initial stress 80 MPa included (VM313).
- UHMWPE bar in uniaxial tension with the Three Network Model (TB,TNM); temperature held at 300 K to isolate mechanics (VM314).
- Free sintering of a ZnO bar (TB,SINT, SOVS model); shrinkage starts at the 750 K transition, relative density tracked to 1000 K (VM315).
- J-integral for a middle-crack tension specimen in elastic-plastic deformation, quarter model, MISO approximating Ramberg-Osgood, checked against EPRI J-estimation (VM316).
- Multistage cyclic modal of a clamped-clamped thin-walled cylinder from four stages with sector counts 18, 13, 10, 11 (MSOPT, CECYCMS, CEIMS), harmonic indices 4 and 5, cross-checked against a full 360 degree model (VM317).
- Necking of a geometrically imperfect circular bar (mid radius 0.982 R) solved both axisymmetric 2D and 3D (VM318).
- Cyclic chain of six linear-cubic oscillators solved with the harmonic balance method, three harmonics, one sector modelled with multistage cyclic constraints; nonlinear spring is a USER300 element (VM319).
- Frictional damper on a SDOF oscillator via CONTA178 with prescribed initial penetration; HBM with one harmonic; displacement and frequency scaling (1e-5 and 200) aid convergence (VM320).
- Radiation between a fixed and a moving plate; SURF251 view factors updated as plate 2 displaces (RSURF with VFUP); coupled thermal-structural PLANE222 (VM321).

## Equations that matter
Equation bodies in this HTML build are SVG graphics and are not transcribed here; numbers and roles only.
- Eq. (316-1): total J as the sum of elastic and plastic parts, per the EPRI estimation scheme (VM316).
- Eq. (316-2): elastic part of J equated to the elastic energy release rate G (VM316).
- Eq. (319-1): governing equation of one linear-cubic oscillator in the cyclic chain under harmonic forcing (VM319).
- Eq. (320-1): equation of motion of the spring-mass-damper with the frictional force term (VM320).
- Eq. (320-2): elastic Coulomb friction law defining the nonlinear damper force (VM320).
- Eqs. (321-1) to (321-3): analytical plate 2 temperature, plate 1 net flux, and enclosure heat loss for the two-plate radiation problem (VM321).

## Numbers worth citing
- Critical speed target 2650 rpm; shell model ratio 0.993, solid model 1.009 (VM301).
- Worst ring modal ratio 0.985, modes 1 and 2 at 0 rpm, both element types (VM302).
- FGM plate SY ratios 1.029, 1.006, 0.983 at X = 0, 0.5, 1 m (VM305).
- Analytical pull-in voltage 316.85 V, APDL 317.963 V; pull-in displacement ratio 1.077, the worst ratio in the slice (VM310).
- Analytical pull-in voltage 559.23 V, nonlinear run to 559 V (VM311).
- Analytical pull-in voltage 399.73 V, run to 397 V; actuator-mode displacement ratio 1.036, resonance ratio 0.988 (VM312).
- Pull-in voltage target 172.161 V, APDL 168.990 V, ratio 0.982 (VM313).
- Axial stress target 174 MPa at 300 K, engineering strain rate 0.007/s, ratio 1.002 (VM314).
- Relative density target 0.634 at 1000 K after 5 degC/min sintering ramp, ratio 0.993 (VM315).
- J-integral ratios 0.94 for both plane stress (23.76 target) and plane strain (14.64 target) (VM316).
- Cylinder frequency ratio at n = 5: 1.033 multistage, 1.029 full 360 degrees, against the 564 Hz closed-form target; the reference reports similar FEA-analytical gaps (VM317).
- Necking mid-section displacement target -3.740 mm: 2D ratio 0.9989, 3D ratio 1.0163 (VM318).
- Heat balance at D = 10 m: APDL 1089300.39 W against target 1065825.00 W, printed ratio 0.98; every other distance matches to 1.00 (VM321).

## Definitions introduced
- Pull-in voltage V_PI - bias at which electrostatic attraction overcomes the restoring stiffness and the electrodes collapse together; extracted as the last converged voltage (VM310, VM313).
- View factor F_ij - proportion of radiation leaving surface i that strikes surface j (VM321).
- Multistage cyclic symmetry - model assembled from several cyclic stages of differing sector counts joined by interstage constraints (VM317).
- Harmonic balance method - harmonic solution of a nonlinear system retaining a chosen number of harmonics (HROPT,HBM,n) (VM319, VM320).
- Three Network Model (TNM) - thermomechanical constitutive model for UHMWPE, activated by TB,TNM (VM314).
- SOVS sintering model - continuum constitutive model for free sintering, activated by TB,SINT (VM315).
- EPRI J-estimation - reference J from an elastic part (energy release rate) plus a plastic part from published EPRI tables (VM316).
- Functionally graded material - material whose properties vary continuously with position, here via TBIN,ALGO interpolation or TBFIELD field variables (VM305, VM308).

## Figures and tables to return to
- Fig. 542 - Campbell diagram from which the critical speed is read (VM301).
- Fig. 555 - the 15 supporting points for TBIN,ALGO; needed to reproduce the FGM definition (VM305).
- Figs. 563, 566, 569, 572 - displacement versus applied voltage curves through pull-in for the four electrostatic cases (VM310, VM311, VM312, VM313).
- Fig. 574 - relative density versus temperature during sintering (VM315).
- Figs. 580, 581 - final necked shape and mid-section displacement versus elongation (VM318).
- Figs. 583, 584 - HBM response curves at excitation amplitudes 1/8 and 1/4 (VM319).
- VM308 results tables - temperature at eleven radii for both cylinder and sphere; useful as a point-by-point FGM conduction benchmark (VM308).
- VM321 results tables - plate 2 temperature, plate 1 flux, and heat balance at ten separations, D = 6 to 15 m (VM321).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM301 | Critical Speed of a Rotating Disk | Static + linear perturbation modal | SHELL281, SOLID186 | Dugdale 1966, J. Mech. Phys. Solids 14 |
| VM302 | Rotating Circular Ring | Static + linear perturbation modal (damped, Coriolis) | SHELL281, SOLID186, CONTA175, TARGE170 | Genta 2005, Dynamics of Rotating Systems, p. 535 |
| VM303 | 1D Steady-State Thermal Conduction in a Reinforced Block | Steady-state thermal | SOLID278, SOLID279, LINK33, REINF264, LINK228 | Jiji 2009, Heat Conduction 3rd ed., pp. 24-25 |
| VM304 | Sloshing Modes in a Hollow Cylindrical Cavity | Modal (acoustic FSI) | FLUID220, SOLID186 | Blevins 2001, Formulas for Natural Frequency and Mode Shape |
| VM305 | Simulation of Functionally Graded Material | Static | PLANE182 | Burlayenko et al. 2017, Appl. Math. Modelling 45, 422-438 |
| VM306 | Surface Impedance for a Single Poroelastic Layer | Harmonic | FLUID220 | Atalla et al. 1998, JASA, 1444-1452 |
| VM307 | Vector-Oriented and Tapered Distributed Edge Load on a Rectangular Plate | Static (large deflection) | SHELL181 | Hibbeler 2010, Engineering Mechanics: Statics 12th ed., p. 183 |
| VM308 | Steady-State Heat Conduction in Functionally Graded Hollow Cylinder and Hollow Sphere | Steady-state thermal | PLANE292, PLANE293 | Obata & Noda 1994, J. Thermal Stresses 17:3, 471-487 |
| VM309 | Torsional Buckling with Cruciform Section Beam | Buckling | BEAM189 | Timoshenko & Gere 1961, Theory of Elastic Stability 2nd ed., p. 229 |
| VM310 | Electrostatic-Structural Analysis of a MEMS Parallel-Plate Capacitor | Nonlinear static + lin. pert. static/modal/harmonic | SOLID226, COMBIN14, MASS21 | Analytical (basic electrostatics) |
| VM311 | Electrostatic-Structural Analysis of a Cylindrical Capacitor | Nonlinear static + lin. pert. static/modal/harmonic | SOLID226, COMBIN14, MASS21 | Analytical (basic electrostatics) |
| VM312 | Electrostatic-Structural Analysis of a Spherical Capacitor | Nonlinear static + lin. pert. static/modal/harmonic | SOLID226, COMBIN14, MASS21 | Analytical (basic electrostatics) |
| VM313 | Pull-In Voltage of an Electrostatically Actuated Fixed-Fixed Beam | Nonlinear static | SOLID226, SOLID186 | Chowdhury et al. 2006, J. Microelectromech. Syst. 15(3), 639-651 |
| VM314 | Stresses of UHMWPE under Uniaxial Tension | Static (TNM material) | SOLID185 | Bergstrom & Bischoff 2010, Int. J. Structural Changes in Solids 2, 31-39 |
| VM315 | Simulation of Free Sintering | Static (SINT material) | SOLID185 | Arguello, Reiterer & Ewsuk 2009, J. Am. Ceram. Soc. 92(7), 1442-1449 |
| VM316 | J-integral for a Middle-Crack Tension Specimen Under Elastic-Plastic Deformation | Static (CINT) | PLANE183 | Anderson 2005, Fracture Mechanics 3rd ed., pp. 398-444 (EPRI) |
| VM317 | Multistage Cyclic Modal Analysis of a Hollow Cylinder | Modal, multistage cyclic | SHELL181 | Cammalleri & Costanza 2016, Int. J. Mech. Sci. 110, 116-126 |
| VM318 | Simulation of Necking of a Circular Bar | Static (nonlinear) | PLANE182, SOLID185 | Simo 1992, Comput. Methods Appl. Mech. Eng. 99, 61-112 |
| VM319 | Nonlinear Harmonic Analysis of a Cyclic Chain of Oscillators | MSUP harmonic (HBM, 3 harmonics) | COMBIN14, MASS21, USER300 | Grolet & Thouverez 2011, J. Eng. Gas Turbines Power 133(2) |
| VM320 | Nonlinear Harmonic Analysis of a Frictional Damper | Harmonic (HBM, 1 harmonic) | COMBIN14, MASS21, CONTA178 | Guillen 1999, PhD thesis, Univ. of Michigan |
| VM321 | Steady-State Radiation Between a Fixed Plate and a Moving Plate | Steady-state thermal (radiosity) | PLANE222, SURF251 | Lienhard & Lienhard 2008, A Heat Transfer Textbook 3rd ed. |

## Links
[[Rotordynamics]], [[Campbell diagram]], [[Cyclic symmetry]], [[Harmonic balance method]], [[Acoustics]], [[Poroelasticity]], [[Fluid-structure interaction]], [[Sloshing]], [[Electrostatic actuation]], [[MEMS]], [[Fracture mechanics]], [[J-integral]], [[Functionally graded materials]], [[Heat conduction]], [[Thermal radiation]], [[Hyperelasticity]], [[Plasticity]], [[Buckling]], [[Sintering]], [[Ansys VM index]]

## Flags
- Every case in the slice has a companion input listing page (Hlp_V_VM<N>TXT.html, the full APDL deck); not read per brief.
- VM301 material table prints density as 7850 kg/m2; suspected erratum for kg/m3. The same table mixes SI properties with inch geometry.
- VM303 notes say "KO(1)110" for LINK228; presumably KEYOPT(1) = 110 as printed.
- VM310 actuator-mode harmonic table is internally inconsistent: target 0.560236E-02, APDL 0.8460001E-02, printed ratio 1.006133. The lin-pert static target 0.840715E-02 suggests a copy error in the target.
- VM312 loading table lists the DC bias (402.48 V) above the stated pull-in (about 397 V); as printed.
- VM317 notes carry a caption "Figure 581: Multistage cyclic stages with mesh" although figures 580 and 581 are numbered inside VM318; figure numbering clash between the two cases.
- VM320 sweep is specified 20 to 350 rad/s but the results table header labels the peak frequency in Hz (209); unit ambiguity as printed.
- VM321 flux row at D = 10 m prints ratio 1.02 for values that agree to seven figures (106582.50 versus 106582.54); suspected erratum. The heat balance at the same distance genuinely disagrees by 2 percent.
- Equation bodies throughout are SVG images in this build; equation numbers and purposes are recorded, bodies not transcribed.
- Supplemental .cdb files (VM2024R2_MAPDL.zip download) are required for VM303, VM304, VM305, VM306, VM308, VM312, VM313, VM316, VM317, VM321.
- No cross-reference to any case outside VM301-VM321 was found; VM321 is the last case, followed by Part II (Benchmark Studies).
- Unread pages: none; all 21 files read in full.
