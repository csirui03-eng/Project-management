---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM61-VM90
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification cases, nearly all small vibration and dynamics models checked against classical textbook solutions: modal analysis of rods, wedges, plates, rings and spring-mass chains; transient response to impact, impulse, step and constant forces with viscous, Coulomb and plastic effects; harmonic response of damped single and two mass systems; seismic and random (PSD) spectrum analysis. Four statics cases break the pattern: Hertz contact of a sphere on a rigid plane, thermal expansion closing a gap, transverse shear in a layered cantilever, and a laminated composite plate against Reddy's exact solution. Thomson's Vibration Theory and Applications supplies over half the targets. Each case names its elements, its ANTYPE, and a results table of target versus Mechanical APDL with ratios, so the slice doubles as a worked catalogue of COMBIN40, COMBIN14, MASS21, LINK180, BEAM188/189 and shell element behaviour on problems with known answers.

## Key ideas
- Free-free rod longitudinal modes: rigid-body f1 = 0 filtered as such, Block-Lanczos, BEAM188 with arbitrary unit section properties (VM61).
- Wedge plate fundamental frequency solved four ways: SHELL63 bending-only, SHELL63 bending+membrane, SHELL181, SHELL281, all against 259.16 Hz (VM62).
- Hertz contact radius via axisymmetric PLANE82/PLANE183 with CONTA178 node-to-node contact; midside nodes removed on the contact face, a node placed at the expected contact radius (VM63).
- Heated bar closing a 0.002 in gap against a rigid surface: CONTA175/TARGE169 with PLANE182, stresses match theory to 0.1 percent (VM64).
- Ball drop on flexible surface: nonlinear transient with MASS21 and CONTA175; step size set to about 1/100 of the impact period; results read at nearest POST26 time point (VM65).
- Flat plate fundamental frequency, one target (128.09 Hz) across SHELL63, SOLSH190, SHELL181, SHELL281 (VM66).
- Circular ring in-plane radial vibration, axisymmetric-harmonic PLANE25; coupling enforces mode symmetry for the second harmonic (VM67).
- Two DOF PSD base excitation: modal then spectrum analysis (ANTYPE 2 then 8), 2 percent constant modal damping, one-standard-deviation responses matched exactly (VM68).
- Vibrometer on displacement response spectrum input; spectrum given at 3 points, instrument accuracy defined as 100(Ae - A)/A = 2 percent (VM69).
- Simply supported beam under support motion via displacement response spectrum; BEAM189; flat 0.44 in spectrum from 0.1 to 10 Hz (VM70).
- Released spring-mass-damper for four damping ratios (2.0, 1.0, 0.2, 0.0); damping coefficients computed as c = 2 xi sqrt(km) (VM71).
- Logarithmic decrement: successive peak amplitude ratios and damped periods from a mode-superposition transient (VM72).
- Coulomb (dry friction) damping in free vibration, COMBIN40 slider, full transient (VM73).
- Impulse force on spring-mass, mode-superposition transient, peak displacement ratio 0.996 (VM74).
- Step excitation of spring-mass-damper initially at rest; response tabulated at t = 0.10 s and 0.20 s (VM75).
- Guitar string: static pretension, then linear perturbed modal and linear perturbed harmonic; string plucked so even harmonics show no response (VM76).
- Beam with concentrated mass under a constant transient force: BEAM188 plus MASS21, peak time, deflection and bending stress checked (VM77).
- Transverse shear stress distribution in a layered cantilever, SHELL281; interlaminar shear at the midplane and failure criterion FC3 both hit targets exactly (VM78).
- Bilinear (gap) spring assembly under impulse, mode-superposition transient; problem statement builds on VM74 (VM79).
- Elastic-plastic rod-and-mass response to a suddenly applied constant force; peak displacement good (0.998), time of peak off by 1.6 percent (VM80).
- Drop container solved twice, full transient and mode-superposition, same targets; the mode-superposition run is the weaker at impact (ratio 0.987) (VM81).
- Cross-ply laminated square plate under pressure against Reddy's exact solution; five element types (SOLID185, SOLSH190, SOLID186, SHELL181, SHELL281) all near 0.0683 m deflection (VM82).
- Block impact on a spring scale, full transient with two COMBIN40s; deflection target -7.7 in, ratio 0.989 (VM83).
- Displacement wave propagation along a 4000 ft free-free drill stem, LINK180 mode-superposition transient (VM84).
- Suddenly stopped moving bar: reflected wave displacements and stress; APDL values reported at neighbouring time points, hence ratios 0.96-0.97 on displacement (VM85).
- Machine on springs under harmonic force: amplitude 0.0833 in and phase -90 degrees at the driving condition (VM86).
- Same system as VM86 solved with equivalent structural damping instead of viscous damping; identical response (VM87).
- Counter-rotating eccentric weight exciter: harmonic amplitude 0.6 in with -90 degree phase, -180 degrees beyond resonance (VM88).
- Two-mass-spring normal modes: frequencies and mode shape amplitude ratios (A1/A2) both verified (VM89).
- Same two-mass chain driven harmonically: amplitudes X1, X2 and phase angles at 1.5, 4.0 and 6.5 Hz (VM90).

## Numbers worth citing
- Free-free rod: f2 ratio 1.003 (126.70 Hz target), f3 ratio 1.014 (253.40 Hz target), coarse BEAM188 mesh (VM61).
- Integration step for impact transient: 0.001 s, about 1/100 of the period during impact; APDL output at nearest stored time point, 0.072 s vs 0.07198 s theory (VM65).
- PSD analysis settings: 2 percent constant modal damping; response evaluated from 10 to 100 Hz at 0.001 Hz frequency spacing (VM68).
- Vibrometer accuracy as defined in the reference: 100(Ae - A)/A = 2 percent; Ae = 1.0200 in matched exactly (VM69).
- Seismic beam max stress: 20158 psi target, APDL 20399 psi, ratio 1.012 (VM70).
- Critically damped release (xi = 1.0): u ratio 1.013, the worst of the four damping cases (VM71).
- Damped natural period: target 0.18507 s, APDL 0.18600 s, ratio 1.005 for all three peak pairs; amplitude ratio target 1.5350 recovered to 1.001-1.003 (VM72).
- Step excitation at t = 0.20 s, undamped: u ratio 1.011 (1.6536 in target) (VM75).
- Plastic response: time of peak 0.0669 s target vs 0.0680 s, ratio 1.016; peak displacement ratio 0.998 (VM80).
- Drop container, mode-superposition run: y at impact ratio 0.987 (-1.00 in target); full transient run gives 1.001 (VM81).
- Spring scale deflection: -7.7000 in target, APDL -7.6135 in, ratio 0.989 (VM83).
- Drill stem end displacement: 4.8000 in target, APDL 4.8404 in, ratio 1.008 (VM84).
- Stopped bar displacement: ratios 0.968 (t = 0.0544 s) and 0.962 (t = 0.0557 s) against theory at t = 0.05573 s, a time-point mismatch noted in footnotes; stress ratio 1.001 (VM85).

## Definitions introduced
- Vibrometer accuracy: 100 x (Ae - A)/A, with Ae the excitation amplitude recovered from the mode shape and A the true amplitude (VM69).

## Figures and tables to return to
- Every case opens with a problem sketch defining geometry, properties and loading; Figures 85 through 128 run consecutively across this slice (VM61-VM90).
- Fig 90 - kinetic energy, velocity and displacement against time for the ball impact, the template POST26 display (VM65).
- Fig 97 - displacement against time for the four damping ratios (VM71).
- Fig 99 - decaying displacement trace behind the logarithmic decrement table (VM72).
- Figs 101, 102 - displacement and sliding force against time under Coulomb damping (VM73).
- Fig 105 - step-excitation displacement history (VM75).
- Fig 107 - string midpoint displacement amplitude against frequency, shows the missing even harmonics (VM76).
- Fig 112 - elastic-plastic displacement history (VM80).
- Fig 116 - block and pan displacements through impact (VM83).
- Figs 118, 119 and 121, 122 - displacement and velocity wave-propagation histories (VM84, VM85).
- Fig 128 - amplitude against frequency for the two-mass system, spans both resonances (VM90).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM61 | Longitudinal Vibration of a Free-free Rod | Modal (ANTYPE 2) | BEAM188 | Thomson, Vibration Theory and Applications, 1965, p. 269, ex. 8.3-1 |
| VM62 | Vibration of a Wedge | Modal (ANTYPE 2) | SHELL63, SHELL181, SHELL281 | Timoshenko and Young, Vibration Problems in Engineering, 3rd ed., 1955, p. 392, art. 62 |
| VM63 | Static Hertz Contact Problem | Static (ANTYPE 0) | PLANE82, PLANE183, CONTA178 | Timoshenko and Goodier, Theory of Elasticity, 3rd ed., 1970, pp. 409-413, art. 140 |
| VM64 | Thermal Expansion to Close a Gap at a Rigid Surface | Static thermal stress (ANTYPE 0) | CONTA175, TARGE169, PLANE182 | Harris, Introduction to Stress Analysis, 1959, p. 58, prob. 8 |
| VM65 | Transient Response of a Ball Impacting a Flexible Surface | Nonlinear transient (ANTYPE 4) | MASS21, CONTA175 | Thomson, 1965, p. 110, ex. 4.6-1 |
| VM66 | Vibration of a Flat Plate | Modal (ANTYPE 2) | SHELL63, SOLSH190, SHELL181, SHELL281 | Timoshenko and Young, 1955, p. 338, art. 53 |
| VM67 | Radial Vibrations of a Circular Ring | Modal, axisymmetric-harmonic (ANTYPE 2) | PLANE25 | Timoshenko and Young, 1955, p. 425, art. 68 |
| VM68 | PSD Response of a Two DOF Spring-mass System | Modal + PSD spectrum (ANTYPE 2, 8) | COMBIN40 | Vierck, Vibration Analysis, 2nd ed., 1979, sec. 7-2, 7-14 |
| VM69 | Seismic Response | Modal, seismic spectrum (ANTYPE 2) | COMBIN40 | Thomson, 1965, p. 78, ex. 3.11-1 |
| VM70 | Seismic Response of a Beam Structure | Modal, seismic spectrum (ANTYPE 2) | BEAM189 | Biggs, Introduction to Structural Dynamics, 1964, p. 262, art. 6.4 |
| VM71 | Transient Response of a Spring-Mass-Damper System | Mode-superposition transient (ANTYPE 4) | COMBIN40 | Thomson, 1965, p. 41, ex. 2.2-1 |
| VM72 | Logarithmic Decrement | Mode-superposition transient (ANTYPE 4) | COMBIN40 | Thomson, 1965, p. 45, ex. 2.3-1 |
| VM73 | Free Vibration with Coulomb Damping | Full transient (ANTYPE 4) | COMBIN40 | Tse, Morse, Hinkle, Mechanical Vibrations, 1963, p. 175, case 1 |
| VM74 | Transient Response to an Impulsive Excitation | Mode-superposition transient (ANTYPE 4) | COMBIN40 | Thomson, 1965, p. 99, art. 4.1 |
| VM75 | Transient Response to a Step Excitation | Mode-superposition transient (ANTYPE 4) | COMBIN40 | Thomson, 1965, p. 102, art. 4.3 |
| VM76 | Harmonic Response of a Guitar String | Static + linear perturbed modal + linear perturbed harmonic | LINK180 | Blevins, Formulas for Natural Frequency and Mode Shape, 1979, p. 90, table 7-1 |
| VM77 | Transient Response to a Constant Force | Mode-superposition transient (ANTYPE 4) | BEAM188, MASS21 | Biggs, 1964, p. 50, ex. E |
| VM78 | Transverse Shear Stresses in a Cantilever Beam | Static (ANTYPE 0) | SHELL281 | Timoshenko and Goodier, Theory of Elasticity, 2nd ed., 1951, p. 35, art. 20 |
| VM79 | Transient Response of a Bilinear Spring Assembly | Mode-superposition transient (ANTYPE 4) | COMBIN40 | Thomson, 1965, p. 150, fig. 5.6-1 |
| VM80 | Plastic Response to a Suddenly Applied Constant Force | Full transient, plastic (ANTYPE 4) | LINK180, MASS21 | Biggs, 1964, p. 69, art. 2.7 |
| VM81 | Transient Response of a Drop Container | Full transient and mode-superposition transient (ANTYPE 4) | COMBIN40, MASS21 | Thomson, 1965, p. 110, ex. 4.6-1 |
| VM82 | Simply Supported Laminated Plate Under Pressure | Static (ANTYPE 0) | SOLID185, SOLSH190, SOLID186, SHELL181, SHELL281 | Reddy, "Exact Solutions of Moderately Thick Laminated Shells", ASCE J. Eng. Mech., Vol. 110 No. 5, 1984, pp. 794-809 |
| VM83 | Impact of a Block on a Spring Scale | Full transient (ANTYPE 4) | COMBIN40 | Beer and Johnston, Vector Mechanics for Engineers, 1962, p. 531, prob. 14.6 |
| VM84 | Displacement Propagation along a Bar with Free Ends | Mode-superposition transient (ANTYPE 4) | LINK180 | Timoshenko and Young, 1955, p. 311, prob. 2 |
| VM85 | Transient Displacements in a Suddenly Stopped Moving Bar | Mode-superposition transient (ANTYPE 4) | LINK180 | Timoshenko and Young, 1955, p. 305, prob. 3 |
| VM86 | Harmonic Response of a Dynamic System | Harmonic (ANTYPE 3) | COMBIN40 | Thomson, 1965, p. 56, ex. 3.1-2 |
| VM87 | Equivalent Structural Damping | Harmonic (ANTYPE 3) | COMBIN40 | Thomson, 1965, p. 72, art. 3.9 and p. 56, ex. 3.1-2 |
| VM88 | Response of an Eccentric Weight Exciter | Harmonic (ANTYPE 3) | COMBIN40 | Thomson, 1965, p. 60, ex. 3.3-1 |
| VM89 | Natural Frequencies of a Two-mass-spring System | Modal (ANTYPE 2) | COMBIN14, MASS21 | Thomson, 1965, p. 163, ex. 6.2-2 |
| VM90 | Harmonic Response of a Two-Mass-Spring System | Harmonic (ANTYPE 3) | COMBIN14, MASS21 | Thomson, 1965, p. 178, ex. 6.6-1 |

## Links
[[Modal analysis]], [[Harmonic response]], [[Transient dynamic analysis]], [[Mode superposition]], [[Response spectrum analysis]], [[Random vibration]], [[Hertz contact]], [[Contact elements]], [[Coulomb damping]], [[Structural damping]], [[Wave propagation in bars]], [[Composite laminates]], [[Ansys VM 031-060]], [[Ansys VM 091-120]]

## Flags
- Every case has a companion input-listing page (Hlp_V_VM<N>TXT.html, file vm<N>.dat); these were excluded from this extract by instruction.
- The source HTML carries no page numbers; VM numbers are the anchors throughout, and figure numbers (85-128) are manual-wide, not per case.
- No numbered equations exist in this slice; mathematics is embedded as SVG images, so the Equations section is omitted.
- Cross-references found, both internal to this slice: VM79 links to VM74 (its problem statement builds on it), and VM87 states its test case is the same as VM86. No case in VM61-VM90 references a case outside the slice.
- Several case pages are single-line minified HTML; content was recovered by pattern extraction and cross-checked, with all 30 cases yielding title, reference, analysis type, elements and results rows. No unreadable pages.
