---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM241-VM270
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification test cases, each a self-contained benchmark with a published reference solution, the analysis type, the element types exercised, a model description, and a target/computed/ratio table. The slice covers a broad sweep of the code: edge-flux electromagnetics and permanent-magnet forces (two TEAM workshop problems), porous acoustics and squeeze-film damping, cyclic symmetry statics and modal analysis, a four-case rotordynamics family built on the Nelson-McVaugh rotor, cohesive-zone and contact-based delamination, gasket, shape memory alloy and Gurson material models, coupled pore-pressure consolidation, fracture parameter extraction with CINT, beam-to-beam and impact contact, and Mullins-effect hyperelasticity. Each case names its APDL input file and the exact commands or KEYOPTs that the test exists to exercise, so the slice doubles as a worked-example index for those features.

## Key ideas
- Rotordynamics family: the same Nelson-McVaugh rotor is solved four ways, beams plus MASS21 and COMBIN14 (VM247), pipes on orthotropic COMBI214 bearings (VM254), internal viscous damping via MP,BETD (VM261), and general axisymmetric SOLID272/273 with CMS superelements (VM263); all activate gyroscopics with CORIOLIS in the stationary frame.
- Delamination benchmark solved twice on one geometry: exponential cohesive-zone interface elements against contact elements (VM248), then contact-based debonding with bilinear CZM, TBOPT = CBDE (VM255); both trace to the same Alfano-Crisfield double cantilever beam.
- The whirl-ratio convention differs between Nelson-McVaugh and Mechanical APDL; reference values for whirl ratio 1/4 are divided by 4 before comparison with slope 4 results (VM247).
- TEAM workshop problem 20 (solenoid actuator force, VM241) and problem 23 (permanent magnet force, VM270) anchor the electromagnetic coverage; VM270 checks Maxwell force on the magnet against Lorentz force on the coil, equal and opposite via EMFT (VM270).
- Johnson-Champoux-Allard five-parameter equivalent fluid predicts the absorption coefficient of a porous layer in an impedance-tube setup; impedance to reflection coefficient to absorption chain evaluated in POST26 (VM242).
- Squeeze-film stiffness and damping constants are extracted from real and imaginary harmonic forces on a FLUID136 film and compared with Blech's analytical coefficients (VM245).
- Gasket loading-unloading response (pressure-closure) is verified against the material definition itself in 2D and 3D (VM249, VM250).
- SMA superelasticity reproduces the Auricchio-Taylor-Lubliner uniaxial hysteresis loop, with the four transformation stress-strain corner points checked (VM251).
- Gurson porous plasticity is benchmarked on bar necking (VM252) and hydrostatic tension (VM253), both from Aravas 1987.
- Fracture toolset: CINT computes KI, J-integral, material force and T-stress on a centre crack (VM256), J-derived KI under thermal gradient (VM262), and mixed-mode KI/KII for an inclined crack (VM267).
- Coupled pore-pressure elements (CPT family) verify Schiffman 2D consolidation (VM260) and Terzaghi 1D consolidation (VM264).
- Impact of an elastic rod on a rigid wall uses HHT with zero numerical damping and impact constraints, KEYOPT(7) = 4 on CONTA177, to conserve energy and momentum (VM265).
- Beam-to-beam frictional contact is verified twice, force-based and traction-based, with an area factor A = 1/(rl) scaling penalties and results between the two formulations (VM266).
- Spectrum analysis with missing mass (ZPA 0.54 g) and rigid response corrections by both Lindley and Gupta methods on the NUREG BM3 piping model (VM259).
- Flexible multibody dynamics: swing with rigid links, HHT with 30 percent numerical damping (VM257), and spin-up manoeuvre of a flexible beam, HHT with 10 percent numerical damping, joint output in the rotating frame (VM258).

## Numbers worth citing
- Worst ratio in the slice: 1.097 on the steady-state stretch time in the spin-up manoeuvre; peak axial tip displacement ratio 1.076; targets were read off the reference graphs and are stated to be imprecise (VM258).
- Reaction FZ at node 1 ratios 0.912 (missing mass) and 0.914 (Lindley) in the BM3 spectrum case; the rest of the table sits within about 5 percent (VM259).
- Swing axial force FX ratio 0.951 and transverse displacement UX ratio 1.043, identical for MPC184 and TARGE170 rigid links (VM257).
- T-stress ratio 1.050 with SOLID185, against 1.004-1.005 for PLANE183 and SOLID186 on the same centre crack (VM256).
- SMA transformation strain EPTO-SAS ratio 1.046 across all three element types; stresses stay within 1.2 percent (VM251).
- 2D consolidation pore-pressure ratios spread 0.945 to 1.061 over the depth and time curves (VM260); 1D consolidation worst point 0.963 with CPT217 (VM264).
- Gurson bar-necking force ratio 0.969 for both PLANE182 and PLANE183 (VM252).
- First forward critical speed ratio 1.032 with internal viscous damping; second log decrement ratio 0.964 (VM261).
- Rod release velocity ratio 0.978 after wave reflection; impact-side quantities all within 0.1 percent (VM265).
- Contact-based debonding end reaction ratio 1.036, against 1.012 for the interface-element version of the same beam (VM255, VM248).
- Solenoid actuator: pole flux density ratio 0.981, force 79.5 N computed against 80.1 N target at 5000 A-turns (VM241).
- Absorption coefficient 0.990 computed against 0.988 target at 1700 Hz (VM242).

## Definitions introduced
- Slope (excitation per revolution) - frequency divided by rotational velocity; the inverse of the reference's whirl ratio (VM247).
- Squeeze number sigma - nondimensional group governing squeeze-film behaviour of a rectangular plate, built on effective viscosity, geometry and frequency (VM245).
- Squeeze stiffness coefficient K_s and damping coefficient C - frequency-dependent constants extracted from real and imaginary harmonic force parts (VM245).
- JCA parameter set - flow resistivity, porosity, tortuosity, viscous and thermal characteristic lengths defining the equivalent fluid (VM242).
- Time factor Tv - nondimensional time built on the consolidation coefficient, used to plot pore-pressure decay (VM260).
- Missing mass and rigid response corrections - Lindley and Gupta methods supplementing SRSS mode combination above the spectrum cut-off (VM259).
- Area factor A = 1/(rl) - converts force-based beam contact penalties and results to the traction-based definition (VM266).

## Figures and tables to return to
- Figure 407 - B-H curve of the actuator steel, the only statement of the nonlinear material for TEAM 20 (VM241).
- Table 10 - full subelement-by-subelement rotor geometry; reused conceptually by the whole rotor family (VM247).
- Table 11 - the same rotor scaled for the orthotropic-bearing variant (VM254).
- Table 13 - rotor geometry for the axisymmetric-element variant (VM263).
- Table 12 - the 75-point frequency versus spectral value input curve for BM3 (VM259).
- Figure 413 - absorption coefficient versus frequency against the reference curve (VM242).
- Figures 429 and 431 - Gurson specimen response curves matched to Aravas figures 10 and 7 (VM252, VM253).
- Figures 438-439 - swing displacement and axial force histories, compared to reference figures 15 and 16 (VM257).
- Figures 442-444 - spin-up tip displacement and rotation histories, compared to reference figure 6 (VM258).
- Figures 458-461 - rod impact displacement, velocity, contact force and energy histories (VM265).
- Figures 449-450 - excess pore pressure versus depth and versus time (VM260).
- Figure 467 - stress-stretch loop showing Mullins softening over one cycle (VM268).
- Figure 470 - flux lines through the open INFIN110 boundary (VM270).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM241 | Static Force Computation of a 3D Solenoid Actuator | Static (ANTYPE 0) | SOLID231, SOLID232, SOLID236, SOLID237, MESH200 | Takahashi, Nakata, Morishige, COMPEL 14 (1995) 57-75 (TEAM 20) |
| VM242 | Johnson-Champoux-Allard Equivalent Fluid Model | Harmonic (ANTYPE 3) | FLUID220 | Doutres, Salissou, Attalla, Panneton, Applied Acoustics 71 (2010) 506-509 |
| VM243 | Cantilever Beam with Triangular Loading Defined by Function | Static | PLANE183 | Beer and Johnston, Mechanics of Materials (1981) |
| VM244 | Modal Analysis of a Cyclic Symmetric Annular Plate | Modal (ANTYPE 2), cyclic | SOLID185, SOLID186, SOLID187, SHELL181, SOLSH190, SHELL281 | Blevins, Formulas for Natural Frequency and Mode Shape (1979) |
| VM245 | Squeeze Film Damping: Rectangular Plate | Harmonic (ANTYPE 3) | FLUID136 | Blech, J. Lubrication Technology 105 (1983) 615-620 |
| VM246 | Cyclic Analysis of an End-Loaded Hollow Cylindrical Cantilever Beam | Static | SOLID185, SOLID186, SOLID187 | Beer and Johnston, Mechanics of Materials (1981) p. 598 |
| VM247 | Campbell Diagrams and Critical Speeds Using Symmetric Bearings | Modal (ANTYPE 2) | BEAM188, MASS21, COMBIN14 | Nelson and McVaugh, J. Engineering for Industry (1976) |
| VM248 | Delamination Analysis of Double Cantilever Beam | Static (ANTYPE 0) | PLANE182, PLANE183, SOLID185, INTER202, INTER203, INTER205, CONTA172, CONTA174, TARGE169, TARGE170 | Alfano and Crisfield, IJNME 50 (2001) 1701-1736 |
| VM249 | Gasket Material Under Uniaxial Compression Loading - 2D Analysis | Static (ANTYPE 0) | PLANE182, PLANE183, INTER192, INTER193 | Any nonlinear material verification text |
| VM250 | Gasket Material Under Uniaxial Compression Loading - 3D Analysis | Static (ANTYPE 0) | SOLID185, SOLID186, INTER194, INTER195 | Any nonlinear material verification text |
| VM251 | Shape Memory Alloy Under Uniaxial Tension Load | Static (ANTYPE 0) | PLANE182, PLANE183, SOLID185 | Auricchio, Taylor, Lubliner, CMAME 146 (1997) 281-312 |
| VM252 | Gurson Bar-Necking Benchmark with Applied Displacement - 2D Analysis | Static (ANTYPE 0) | PLANE182, PLANE183 | Aravas, IJNME 24 (1987) 1395-1416, section 5.3 |
| VM253 | Gurson Hydrostatic Tension Benchmark - 3D Analysis | Static (ANTYPE 0) | SOLID185, SOLID186 | Aravas, IJNME 24 (1987) 1395-1416, section 5.2 |
| VM254 | Campbell Diagrams and Critical Speeds Using Symmetric Orthotropic Bearings | Modal (ANTYPE 2) | PIPE16, PIPE288, MASS21, COMBI214 | Nelson and McVaugh, J. Engineering for Industry 98 (1976) 593-600 |
| VM255 | Delamination Analysis using Contact Based Debonding Capability | Static (ANTYPE 0) | PLANE182, CONTA172, TARGE169 | Alfano and Crisfield, IJNME 50 (2001) 1701-1736 |
| VM256 | Evaluation of Fracture Parameters for a Center Crack in a Plate | Static (ANTYPE 0) | PLANE183, SOLID185, SOLID186 | Brown and Srawley, ASTM STP-410 (1966) |
| VM257 | Transient Analysis of a Swing with Two Rigid Links and a Beam | Transient (ANTYPE 4) | BEAM188, MPC184, TARGE170 | Bauchau, Damilano, Theron, IJNME 38 (1995) 2727-2751 |
| VM258 | Spin-up Maneuver of a Flexible Beam | Transient (ANTYPE 4) | BEAM189, MPC184 (general, revolute) | Simo and Vu-Quoc, CMAME 66 (1988) 125-161 |
| VM259 | Missing Mass with Rigid Responses Effects in Spectrum Analysis for BM3 Piping Model | Spectrum (ANTYPE 8) | PIPE16, PIPE18, COMBIN14 | Morante and Wang, NUREG/CR-6645, Brookhaven (1999) |
| VM260 | Two-Dimensional Consolidation Settlement Problem | Static (ANTYPE 0) | CPT212, CPT213 | Schiffman et al., J. Soil Mechanics and Foundation Div. (1969) 285-312 |
| VM261 | Rotating Beam with Internal Viscous Damping | Modal (ANTYPE 2) | BEAM188, COMBI214 | Zorzi and Nelson, ASME J. Engineering for Power 99 (1976) 71-76 |
| VM262 | 2D Fracture Problem Under Thermal Loading | Static (ANTYPE 0) | PLANE182 | Wilson et al., International J. of Fracture (1979) 377-387 |
| VM263 | Critical Speeds for a Rotor Bearing System with Axisymmetric Elements | Modal (ANTYPE 2) | SOLID272, SOLID273, COMBI214, MATRIX50 | Nelson and McVaugh, J. Engineering for Industry (1976) 593-600 |
| VM264 | Terzaghi's One-Dimensional Consolidation Settlement Problem | Static (ANTYPE 0) | CPT213, CPT215, CPT216, CPT217 | Terzaghi, Theoretical Soil Mechanics, Wiley (1942) |
| VM265 | Elastic Rod Impacting a Rigid Wall | Transient (ANTYPE 4) | SHELL181, CONTA177, TARGE170 | Carpenter, Taylor, Katona, IJNME 32 (1991) 103-128 |
| VM266 | 3D Crossing Beams in Contact with Friction | Static (ANTYPE 0) | BEAM188, CONTA177, TARGE170 | Zavarise and Wriggers, IJNME 49 (2000) 977-1006 |
| VM267 | Inclined Crack in 2D Plate Under Uniform Tension Loading | Static (ANTYPE 0) | PLANE182 | T. L. Anderson, Fracture Mechanics, CRC Press (1995) |
| VM268 | Mullins Effect on a Rubber Tube Model Subjected to Tension Loading | Static (ANTYPE 0) | PLANE182 | Ogden et al., Proc. Royal Society London A, 2861-2877 (stated 1989) |
| VM269 | Deformation of Tube and Sphere Modeled with Neo-Hookean Material Model | Static (ANTYPE 0) | PLANE182, SOLID185 | Yosibash, CMAME 196 (2007) 1261-1277 |
| VM270 | Forces in Permanent Magnets | Static (ANTYPE 0) | INFIN110, PLANE233 | Ida and Bastos, TEAM problem 23, Okayama (1996) 49-56 |

## Links
[[Rotordynamics]], [[Campbell diagram]], [[Modal analysis]], [[Cyclic symmetry]], [[Acoustic absorption]], [[Johnson-Champoux-Allard model]], [[Impedance tube]], [[Squeeze film damping]], [[Cohesive zone model]], [[Delamination]], [[Fracture mechanics]], [[Stress intensity factor]], [[J-integral]], [[Shape memory alloy]], [[Gurson model]], [[Gasket elements]], [[Poroelasticity]], [[Consolidation]], [[Response spectrum analysis]], [[Contact mechanics]], [[Impact]], [[Hyperelasticity]], [[Mullins effect]], [[Magnetostatics]], [[TEAM workshop problems]], [[Ansys Mechanical APDL]]

## Flags
- Every case has a companion input-listing page, Hlp_V_VM241TXT.html through Hlp_V_VM270TXT.html, holding the full APDL deck; not read per instructions.
- VM241, VM256, VM262 and VM267 need supplemental .cdb mesh files from the VM2024R2_MAPDL.zip download; the .dat alone does not run.
- Suspected errata: outer diameter "203" cm in the last row of the rotor geometry table, plausibly 2.03 (VM247, repeated in VM263); aluminium density given as 2700 kg/m^2 (VM257); VM268 dates the Ogden-Roxburgh reference 1989 with pages 2861-2877, which match the 1999 Proc. R. Soc. A paper; in VM263 the first two SOLID272 ratios (1.004, 1.005) do not equal computed/target for the printed values (7693/7929 is roughly 0.970).
- Element naming wobbles between COMBI214 (overview list) and COMBIN14 (notes text) inside VM263.
- Equations appear only as embedded SVG images with no equation numbers anywhere in the slice, so no Equations section could be built without fabrication.
- VM258 targets are digitised from reference graphs and flagged imprecise by the manual itself; treat its ratios accordingly.
- VM241's figure image files carry gvm233 names, a packaging leftover; the figures themselves belong to VM241.
- VM249 and VM250 verify against the input material definition, not an external reference.
- No case in this slice explicitly cross-references a case outside VM241-VM270; the Nelson-McVaugh rotor family and the Alfano-Crisfield beam pair are wholly internal to the slice.
