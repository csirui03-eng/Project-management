---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM151-VM180
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification cases, each a small benchmark against a classical or published solution. The block moves through structural dynamics of plates and membranes, a fluid coupling, rate-dependent plasticity, thermal problems including two analogy tricks (seepage and moisture diffusion via the Laplace equation), a run of magnetics from nonlinear statics to transient eddy currents and permanent magnet circuits, coupled-field cases (magneto-structural, electric-thermal, thermal-structural), two piezoelectric transducer cases, a submerged ring fluid-structure case solved five ways, a VCCT fracture case, a jointed-beam multibody transient, and curved beam bending. Every case follows the same template: overview table (reference, analysis type, elements, input listing), test case statement with a problem sketch, material, geometric and loading data, modelling notes, and a results table of target versus Mechanical APDL with a ratio. The slice's job in the manual is to demonstrate element and solver capabilities on problems small enough to check by hand or against the cited source.

## Key ideas
- Axisymmetric-harmonic shell elements extract nonaxisymmetric plate and membrane modes from a 2D mesh; the harmonic index i counts nodal diameters (VM151, VM152).
- Membrane prestress is applied by uniform cooling, the temperature drop back-computed from the target edge tension (VM152, VM153).
- The same stretched membrane is solved in 2D harmonic form and in 3D with a 30 degree cyclic-symmetry sector, side by side (VM152, VM153).
- FLUID38 supplies the hydrodynamic mass of a liquid annulus between a massless cylinder and its containment (VM154).
- Chaboche kinematic hardening combines with a rate-dependent model (TB,CHAB plus TB,RATE) under 23 cycles of displacement loading with hold periods (VM155).
- A nonlinear spring period comes from transient integration with the force-deflection curve entered as eleven discrete points (VM156).
- Acoustic modal analysis handles a step temperature discontinuity (31 percent cool gas) by ideal-gas scaling of sound speed and density (VM157).
- Static equilibrium of a floating body is found by the slow dynamics technique, with mass damping estimated from the out-of-balance force (VM158).
- COMBIN37 control elements switch a heater between set temperatures; the case is self-checking, no external reference (VM159).
- Thermal solvers do double duty through variable substitution: groundwater seepage via permeability analogy (VM163) and slab drying via diffusion analogy (VM164).
- The magnetics run climbs from a nonlinear B-H conductor with infinite elements (VM165), through harmonic (VM166) and transient (VM167) eddy currents, to a solenoid source field via SOURC36 (VM168), permanent magnet circuits (VM169), and Biot-Savart from a line-current loop with the BIOT command (VM170).
- Coupled-field chains: magneto-structural relay with an elastic keeper (VM171), solenoid hoop stress from Lorentz forces (VM172), electric-thermal wire heating (VM173), thermal-structural bimetal with large deflection (VM174).
- Piezoelectric pair: short-circuit resonance versus open-circuit anti-resonance of a PZT4 cube (VM175), then terminal admittance of a composite transducer swept through its first natural frequency near 44 kHz (VM176).
- Fluid-structure coupling gives unsymmetric matrices; the submerged ring frequency is found by unsymmetric modal analysis or by harmonic sweep, in five element combinations (VM177).
- VCCT energy release rate G is computed with the CINT command at a crack tip between contact-paired faces (VM178).
- An MPC184 revolute joint carries stiffness, inertial mass, friction torque and a 5 degree lock; the run includes a mid-analysis restart (VM179).
- Pure bending of a curved beam is checked against the Timoshenko and Goodier elasticity solution using PLANE183 with stiff transmission beams at the free end (VM180).

## Equations that matter
$$S = -E\,\alpha\,t\,\Delta T \tag{VM152}$$
Edge tension induced in a membrane by uniform cooling; used to set the prestress temperature drop (VM152, sign positive in VM153).

$$\alpha \approx \frac{F}{MV} \tag{VM158}$$
Mass damping estimate for slow dynamics: out-of-balance force over buoy mass times an assumed average velocity, giving about 3 s^-1 here (VM158).

$$T(r,\theta) = T_o \left(\frac{r}{r_o}\right)^{2} \cos 2\theta \tag{VM160}$$
Closed-form harmonic (mode 2) temperature field in a solid cylinder against which the PLANE78 solution is checked (VM160).

$$\Delta t_{\max} \approx \frac{\delta^{2}}{4\alpha}, \qquad \alpha = \frac{\rho}{\mu} \tag{VM167}$$
Time step rule from the conduction length of the first element; alpha is the magnetic diffusivity, 0.31822 m^2/s here. The same delta^2/4D rule sets the diffusion time step in VM164 (VM167).

$$Y = \frac{I}{V}, \qquad I = j\omega \sum_i Q_i \tag{VM176}$$
Terminal input admittance from the summed nodal charge on the coupled electrode nodes (VM176).

## Numbers worth citing
- Admittance ratios at 42 kHz: 1.400 (SOLID5) and 1.741 (SOLID226); at 45 kHz the target is 0.0 mmhos and APDL returns -1.74 and -1.13 mmhos, ratio shown 0.000. Targets are interpolated from graphical data near anti-resonance, so these are the worst ratios in the slice (VM176).
- Piezoelectric cube mode ratios span 0.949 to 1.038 against experimentally measured breathing modes (VM175).
- Submerged ring: target 10.20 Hz; shell and beam cases run 1.036 to 1.044, FLUID220 with SHELL281 gives 1.008; the finite fluid radius b = 30 in is stated to cost under 1 percent versus an unbounded fluid (VM177).
- Chaboche stress-history ratios 0.973 to 1.003 over the final load cycle (VM155).
- Transient eddy current vector potential at x = 0.6914 m: ratio 0.934, the worst point; other quantities 0.975 to 1.065 (VM167).
- Slab drying: 10.3 percent versus a graphical estimate of 10 percent, ratio 1.027 (VM164).
- VCCT energy release rate 0.192 versus 0.201, ratio 0.955 (VM178).
- Curved beam tensile stress 674.5 psi versus 655.0 psi, ratio 1.030 (VM180).
- Cyclic-symmetry membrane mode f(1,2): ratio 1.017, coarsest of that set (VM153).
- Heater hysteresis: first switch-off between 124.873 and 125.032 degrees F on a 125 degrees F setpoint; first switch-on between 99.2459 and 101.214 degrees F on 100 degrees F; no ratios given (VM159).

## Definitions introduced
- Harmonic index i - number of nodal diameters of an axisymmetric-harmonic mode; j counts nodal circles including the boundary (VM151).
- Hydrodynamic mass - added mass of the liquid annulus that governs the immersed cylinder frequency (VM154).
- Slow dynamics - obtaining a static equilibrium by a damped transient run to steady state (VM158).
- Permeability analogy - temperature maps to pressure head, heat flow rate to fluid flow rate, conductivity to permeability (VM163).
- Diffusion analogy - temperature maps to moisture concentration, conductivity to diffusion coefficient (VM164).
- Magnetic diffusivity - alpha = rho/mu, the time scale parameter for transient eddy currents (VM167).
- Reduced scalar potential (RSP) - scalar potential strategy used when only source fields exist or no current sources are defined (VM168, VM169).
- Resonance and anti-resonance - short-circuit (grounded electrodes) versus open-circuit conditions of a piezoelectric transducer (VM175).
- Input admittance Y - current over applied potential at the transducer terminals (VM176).
- VCCT - virtual crack closure technique used by CINT for energy release rate G (VM178).

## Figures and tables to return to
- Table 2 (within VM165) - nine-point B-H curve for cast steel, graph-estimated from the reference; the only tabulated material curve in the slice (VM165).
- Fig. 218 - the 23-cycle loading history with the constant-displacement gaps at 910 to 940 s and 960 to 990 s (VM155).
- Fig. 219 - force-deflection curve of the nonlinear spring, needed to rebuild the COMBIN39 input (VM156).
- Constitutive matrices sections - full stiffness, piezoelectric and dielectric matrices for PZT4 (VM175) and NEPEC 6 (VM176), given only as equation images.
- Fig. 264 - electrical input admittance versus frequency, SOLID5 and SOLID226 overlaid (VM176).
- Fig. 266 - node displacement versus driving frequency near the first bending mode; how the harmonic-sweep frequency brackets were read (VM177).
- Figs. 243 and 244 - vector displays of flux density and field intensity in the magnet circuit (VM169).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM151 | Nonaxisymmetric vibration of a circular plate | Modal | SHELL61 | Blevins 1979, p. 240 |
| VM152 | 2D nonaxisymmetric vibration of a stretched membrane | Modal + static prestress | SHELL61 | Timoshenko & Young 1955, pp. 438-439 |
| VM153 | 3D nonaxisymmetric vibration of a stretched membrane | Linear perturbation modal + static | SHELL181 | Timoshenko & Young 1955, p. 439 |
| VM154 | Vibration of a fluid coupling | Modal | FLUID38, COMBIN14 | Fritz 1972, ASME J. Eng. for Industry |
| VM155 | Chaboche rate-dependent plastic material under cyclic loading | Static | PLANE182 | Lin, Betten & Brocks 2006 |
| VM156 | Natural frequency of a nonlinear spring-mass system | Full transient | COMBIN39, MASS21 | Timoshenko & Young 1955, p. 141 |
| VM157 | 3D acoustic modal analysis with temperature change | Modal (acoustic) | FLUID30 | Oberg, Ryan & Baer, AIAA J. 6(6) |
| VM158 | Motion of a bobbing buoy | Full transient | PIPE288 | Brenkert 1960, p. 37 |
| VM159 | Temperature-controlled heater | Transient thermal | COMBIN37, LINK34, MASS71 | Self-checking |
| VM160 | Solid cylinder with harmonic temperature load | Static thermal (harmonic) | PLANE78 | Hildebrand 1976, p. 447 |
| VM161 | Heat flow from an insulated pipe | Static thermal | SOLID90 | Kreith 1959, p. 36 |
| VM162 | Cooling of a circular fin of rectangular profile | Static thermal | SOLID90 | Schneider 1957, p. 82 |
| VM163 | Groundwater seepage (permeability analogy) | Static thermal analogy | PLANE55 | Owen & Hinton 1980, p. 89 |
| VM164 | Drying of a thick wooden slab (diffusion analogy) | Transient thermal analogy | LINK33 | Rohsenow & Choi 1963, p. 392 |
| VM165 | Current-carrying ferromagnetic conductor | Nonlinear static magnetic | PLANE233, INFIN110 | Boast 1948, p. 225 |
| VM166 | Long cylinder in a sinusoidal magnetic field | Full harmonic magnetic | PLANE13, PLANE233 | Emson 1986, RAL-86-049, p. 39 |
| VM167 | Transient eddy currents in a semi-infinite solid | Transient magnetic | PLANE13, PLANE233 | Holman 1976, p. 104 (analogous solution) |
| VM168 | Magnetic field in a nonferrous solenoid | Static magnetic | SOLID5, SOURC36 | Boast 1948, p. 243 |
| VM169 | Permanent magnet circuit with an air gap | Static magnetic | SOLID98 | Moon 1984, p. 275 |
| VM170 | Magnetic field from a square current loop | Coupled-field static | LINK68 | Boast 1948, pp. 199-200 |
| VM171 | Permanent magnet circuit with an elastic keeper | Coupled-field static | PLANE13, PLANE223, COMBIN14 | Moon 1984, p. 275 |
| VM172 | Stress analysis of a long, thick, isotropic solenoid | Coupled-field static | PLANE13 | Moon 1984, p. 275 |
| VM173 | Centerline temperature of an electrical wire | Coupled-field static | SOLID5 | Rohsenow & Choi 1963, p. 106 |
| VM174 | Bimetallic beam under thermal load | Coupled-field static | PLANE13, PLANE223 | Boley & Weiner 1985, p. 429 |
| VM175 | Natural frequency of a piezoelectric transducer | Modal (piezoelectric) | SOLID5, SOLID226 | Boucher, Lagier & Maerfeld 1981, IEEE |
| VM176 | Frequency response of electrical input admittance | Full harmonic (piezoelectric) | SOLID5, SOLID226, SOLID186 | Kagawa & Yamabuchi 1979, IEEE |
| VM177 | Natural frequency of a submerged ring | Unsymmetric modal + full harmonic | FLUID30, SHELL63, FLUID29, BEAM188, SHELL181, FLUID220, FLUID221, SHELL281 | Schroeder & Marcus 1975 |
| VM178 | 2D double cantilever beam problem | Static (fracture, VCCT) | PLANE182 | Mandell et al. 2003 |
| VM179 | Dynamic double rotation of a jointed beam | Full transient (HHT) | MPC184, MASS21, BEAM188 | Basic mechanics text (unspecified) |
| VM180 | Bending of a curved beam | Static | PLANE183, BEAM188 | Timoshenko & Goodier 1970, p. 73 |

## Links
[[Modal analysis]], [[Cyclic symmetry]], [[Fluid-structure interaction]], [[Acoustics]], [[Piezoelectricity]], [[Eddy currents]], [[Magnetostatics]], [[Heat conduction]], [[Analogy methods in FEA]], [[Chaboche plasticity]], [[Fracture mechanics]], [[Multibody joints]], [[Ansys VM 121-150]], [[Ansys VM 181-210]]

## Flags
- Every case has a companion full APDL input listing page (Hlp_V_VM<N>TXT.html, vm<N>.dat); not read in this pass by instruction.
- VM169 requires a supplemental vm169.cdb file from the VM2024R2_MAPDL.zip download; geometry and mesh must be regenerated for the case to run (VM169).
- VM152 and VM153 cross-reference each other as 2D and 3D solutions of the same problem; both sit inside this slice. No case references anything outside VM151 to VM180.
- Suspected errata: sound speeds printed with units in/s^2 (VM157); frequency results tabled under kHz with values that read as Hz (VM175); inputs in SI but result deflections tabled in inches, and E given as N-m (VM179); the current density line equates 2.28019 x 10^-4 A/in^2 to 438559 A/m^2, which is inconsistent (VM165); the problem figure and internal anchor are titled End Notched Flexure under a double cantilever case heading (VM178).
- VM155 results table gives stresses near 0.68 x 10^9 with no unit stated while material data are in MPa; values are consistent with Pa (VM155).
- VM159 reports a hysteresis band rather than a ratio; VM168 requests flux density at three locations but tables only two (VM159, VM168).
- Harmonic-sweep results in VM177 are frequency brackets (for example 10.560 < f < 10.580 Hz), not point values (VM177).
