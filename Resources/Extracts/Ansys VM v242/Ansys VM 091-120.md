---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VM91-VM120
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Thirty verification cases, and this slice is the thermal core of the manual. VM91 opens as an outlier: a large-rotation swinging pendulum solved as a full transient dynamic. VM92 to VM103 then walk steady-state conduction from 1D link chains (insulated wall, fins, spines) up through 2D and 3D solids (chimney section, cylinders, plate with a central heat source), including temperature-dependent conductivity. VM104 to VM116 cover transients: phase change by the enthalpy method, quenched bars and slabs, cooled spheres and wires, ramped surface temperatures, and a temperature-dependent film coefficient. VM117 to VM120 close with the electrical analogues: a resistor bridge, Joule-heated wires (thermal-electric coupling), and an electrostatic microstrip capacitance. Each case states its textbook reference, element types, load data with units, modelling shortcuts (symmetry sectors, arbitrary node locations, time-step rules), and a target-versus-computed table with ratios.

## Key ideas
- Pendulum swing needs large deflection on plus an initial small time step (0.002 s) so the step change in acceleration is followed; later steps are 1/24 of the period (VM91).
- Series thermal resistance wall: two conduction links and two convection links reproduce the textbook heat loss to 0.2 per cent (VM92).
- Temperature-dependent conductivity $k(T) = C_0 + C_1 T$ handled directly by material property tables (VM93, VM102, VM105).
- Half-symmetry with internal heat generation gives plate centre temperature and heat flow to fluid (VM94).
- The same spine problem solved twice, LINK33/LINK34 chain versus SOLID70 mesh, lands identical results, a deliberate element cross-check (VM95).
- Axisymmetric problems modelled as thin wedge sectors (10 to 45 degrees) with coupled nodes or adiabatic edges standing in for circumferential symmetry (VM96, VM101, VM103, VM105, VM111, VM112, VM118, VM119).
- Fin family: straight fin on thermal shells (VM97), tapered fin on PLANE55 (VM98), trapezoidal fin meshed to match the reference relaxation grid node for node (VM99).
- Chimney cross-section uses one-eighth symmetry and reproduces a relaxation solution node by node (VM100).
- Reissuing MP in a second load step switches constant k to k(T) within one run (VM102).
- Phase change by rapid enthalpy variation over a 1 degree C mushy zone; adjusted specific heat $L_f/\Delta T$; more than one time step must fall inside the freezing zone (VM104).
- Radiation link elements need absolute temperatures: add the 460 degree F offset, and mind the Stefan-Boltzmann constant units (VM106, VM107).
- Harmonic (mode 1) temperature loading on axisymmetric-harmonic elements gives the sinusoidal circumferential distribution (VM108).
- Lumped-capacity transient: one convection link plus one thermal mass reproduces the cooled-wire response (VM109).
- Recurring transient rule: initial integration time step at or above $\delta^2/4\alpha$ with $\delta$ the element conducting length and $\alpha$ the diffusivity (VM110 to VM116).
- VM112 repeats VM111 with 8-node PLANE77 instead of PLANE55; curved-side versus straight-side boundary is the only change (VM112).
- Film coefficient as a function of surface temperature, $h = 2.0 + 0.02(T - T_\infty)$, solved with a steady-state first load step then transient (VM116).
- Resistor network mapped to conduction elements via $A = \rho \ell / R$, and solved again with CIRCU124 circuit elements; identical branch currents (VM117).
- Joule heating: heat-generation-rate form (VM118) versus coupled thermal-electric form with resistivity converted by 3.415 (Btu/hr)/W (VM119).
- Capacitance from field energy, not charge: sum element electrostatic energies and invert $W_e = \tfrac12 C V^2$ (VM120).

## Equations that matter
$$T(r,\Theta) = T_0 \,\frac{r}{r_0}\, \cos\Theta \tag{VM108}$$
Closed-form steady temperature in a solid cylinder under mode 1 sinusoidal circumferential surface temperature; the target for the harmonic-element test.

$$\mathrm{ITS} \geq \frac{\delta^2}{4\alpha} \tag{VM110}$$
Minimum recommended initial integration time step for transient conduction; $\delta$ is element conducting length, $\alpha = k/\rho c$. Applied in VM110 through VM116.

$$H = \rho \int c \, dT \tag{VM104}$$
Enthalpy curve for the phase-change run; the latent heat enters as an adjusted specific heat $L_f/\Delta T$ over the mushy zone.

$$W_e = \tfrac{1}{2}\, C \,(V_1 - V_0)^2 \tag{VM120}$$
Capacitance extracted from summed element electrostatic energy under a known potential difference.

## Numbers worth citing
- Worst pendulum ratio 1.031 (x deflection at three-quarter period); rows with zero target show absolute drift up to 0.23 in at one full period (VM91).
- Trapezoidal fin heat rate ratio 0.982 against the recalculated reference value 3545 Btu/hr (VM99).
- Chimney node ratios span 0.93 to 1.07 (nodes 11, 12, 15); heat rate 773.5 versus 775.2 Btu/hr (VM100).
- Coarse sector model runs 1.02 to 1.09 high on centreline temperatures, node 11 worst at 1.09 (VM101).
- SHELL132 variant runs 1.04 on the two hottest nodes; SHELL131 variant dips to 0.95 at node 9 (VM103).
- Solidification time: target 810 s, computed crossing between 787 and 797 s; temperature at x = 0.004 m ratio 1.059 (VM104).
- Stefan-Boltzmann constant used: 0.174 x 10^-8 Btu/hr-ft^2-R^4, with 460 degree F Fahrenheit-to-Rankine offset (VM107).
- Sphere centre temperature after 6 hr: 28.96 degrees F versus graphical 28.0, ratio 1.034 (VM111); PLANE77 variant 29.0, ratio 1.035 (VM112).
- Orthotropic bar face-centre node ratio 1.05 at 3 s (VM113).
- Surface temperature after 7 hr with temperature-dependent h: 293 versus 285 degrees F, ratio 1.03 (VM116).
- Resistivity conversion for Joule heat in thermal units: divide by 3.415 (Btu/hr)/W (VM119).
- Microstrip capacitance 179.2 versus 178.1 pF/m, ratio 1.006 (VM120).

## Definitions introduced
- Mushy zone - the temperature interval $\Delta T$ (taken as 1.0 degree C) over which enthalpy varies rapidly to approximate latent heat during phase change (VM104).
- ENTH - material property carrying the enthalpy-versus-temperature curve for phase-change runs (VM104).
- Initial integration time step (ITS) - the first transient step size, bounded below by $\delta^2/4\alpha$ (VM110).

## Figures and tables to return to
- Fig. 130 - computed pendulum swing trace, the visual check on period drift (VM91).
- Fig. 136 - temperature isosurface display with annotation, the manual's example of 3D thermal postprocessing (VM96).
- Fig. 141 - chimney section temperature contours over the one-eighth symmetry model (VM100).
- Figs. 147, 148 - enthalpy versus temperature input curve, and the temperature profile at 501 s showing the slope discontinuity at the phase front (VM104).
- Fig. 151 - radial temperature variation in the heat-generating coil (VM105).
- Figs. 165, 166 - surface temperature history and through-thickness distribution for the temperature-dependent h case (VM116).
- Fig. 167 - the unbalanced bridge circuit sketch with branch labelling used by both element formulations (VM117).

## Where to find what
| VM | Title | Analysis type | Elements | Reference solution source |
|---|---|---|---|---|
| VM91 | Large Rotation of a Swinging Pendulum | Full transient dynamic (ANTYPE = 4) | LINK180, MASS21 | Thomson, Vibration Theory and Applications, 1965, p. 138, ex. 5.4-1 |
| VM92 | Insulated Wall Temperature | Thermal (ANTYPE = 0) | LINK34, LINK33 | Kreith, Principles of Heat Transfer, 1959, p. 32, ex. 2-5 |
| VM93 | Temperature Dependent Conductivity | Thermal (ANTYPE = 0) | LINK33 | Kreith, p. 25, ex. 2-2 |
| VM94 | Heat-generating Plate | Thermal (ANTYPE = 0) | LINK33, LINK34 | Kreith, p. 42, ex. 2-9 |
| VM95 | Heat Transfer from a Cooling Spine | Thermal (ANTYPE = 0) | LINK33, LINK34, SOLID70 | Kreith, p. 48, eqs. 2-44, 2-45 |
| VM96 | Temperature Distribution in a Short, Solid Cylinder | Thermal (ANTYPE = 0) | SOLID87 | Schneider, Conduction Heat Transfer, 1957, p. 134, fig. 6-7 |
| VM97 | Temperature Distribution Along a Straight Fin | Thermal (ANTYPE = 0) | SHELL131, SHELL294, LINK34 | Kreith, p. 57, ex. 2-13 |
| VM98 | Temperature Distribution Along a Tapered Fin | Thermal (ANTYPE = 0) | PLANE55 | Kreith, p. 57, ex. 2-13 |
| VM99 | Temperature Distribution in a Trapezoidal Fin | Thermal (ANTYPE = 0) | PLANE55 | Schneider, p. 164, art. 7-8 |
| VM100 | Heat Conduction Across a Chimney Section | Thermal (ANTYPE = 0) | PLANE55 | Kreith, p. 102, ex. 3-4 |
| VM101 | Temperature Distribution in a Short Solid Cylinder | Thermal (ANTYPE = 0) | SOLID70 | Schneider, p. 134, fig. 6-7 |
| VM102 | Cylinder with Temperature Dependent Conductivity | Thermal (ANTYPE = 0) | PLANE55 | Schneider, p. 166, art. 7-9 |
| VM103 | Thin Plate with Central Heat Source | Thermal (ANTYPE = 0) | SHELL131, SHELL132 | Schneider, p. 173, art. 8-1 |
| VM104 | Liquid-Solid Phase Change | Transient thermal with phase change (ANTYPE = 4) | PLANE55 | Dantzig, Int. J. Numer. Methods Eng., vol. 28, 1989, p. 1774, problem I |
| VM105 | Heat Generating Coil with Temperature Conductivity | Thermal (ANTYPE = 0) | PLANE55 | Schneider, p. 193, art. 8-8 |
| VM106 | Radiant Energy Emission | Thermal (ANTYPE = 0) | LINK31 | Kreith, p. 22, prob. 1-8(b) |
| VM107 | Thermocouple Radiation | Thermal (ANTYPE = 0) | LINK31, LINK34 | Chapman, Heat Transfer, 1960, p. 396, art. 13.5 |
| VM108 | Temperature Gradient Across a Solid Cylinder | Thermal (ANTYPE = 0) | PLANE75 | Hildebrand, Advanced Calculus for Applications, 1976, p. 447, eqs. 38-44 |
| VM109 | Temperature Response of a Suddenly Cooled Wire | Transient thermal (ANTYPE = 4) | LINK34, MASS71 | Kreith, p. 120, ex. 4-1 |
| VM110 | Transient Temperature Distribution in a Slab | Transient thermal (ANTYPE = 4) | LINK33, LINK34 | Kreith, p. 140, ex. 4-4 |
| VM111 | Cooling of a Spherical Body | Transient thermal (ANTYPE = 4) | PLANE55 | Kreith, p. 143, ex. 4-5 |
| VM112 | Cooling of a Spherical Body | Transient thermal (ANTYPE = 4) | PLANE77 | Kreith, p. 143, ex. 4-5 |
| VM113 | Transient Temperature Distribution in an Orthotropic Metal Bar | Transient thermal (ANTYPE = 4) | PLANE55 | Schneider, p. 261, ex. 10-7 |
| VM114 | Temperature Response to Increasing Temperature | Transient thermal (ANTYPE = 4) | LINK33 | Schneider, pp. 274-275, eq. 11-9 |
| VM115 | Thermal Response of a Heat-generating Slab | Transient thermal (ANTYPE = 4) | LINK33 | Schneider, p. 283, eq. 11-21 and p. 309, art. 12-8 |
| VM116 | Heat Conducting Plate with Sudden Cooling | Transient thermal (ANTYPE = 4) | LINK34, LINK33 | Kreith, p. 161, ex. 4-11 |
| VM117 | Electric Current Flowing in a Network | Thermal-electrical (ANTYPE = 0) | LINK68, CIRCU124 | Fitzgerald and Higginbotham, Basic Electrical Engineering, 1957, p. 22, ex. 1-11 |
| VM118 | Centerline Temperature of a Heat-generating Wire | Thermal (ANTYPE = 0) | PLANE55, SOLID70 | Rohsenow and Choi, Heat, Mass and Momentum Transfer, 1963, p. 106, ex. 6.5 |
| VM119 | Centerline Temperature of an Electrical Wire | Coupled thermal-electric (ANTYPE = 0) | PLANE223, SOLID226 | Rohsenow and Choi, p. 106, ex. 6.5 |
| VM120 | Microstrip Transmission Line Capacitance | Electrostatic (ANTYPE = 0) | PLANE121 | Beren and Kaires, Tektronix internal publication, 1983 |

## Links
[[Heat conduction]], [[Convection]], [[Thermal radiation]], [[Transient heat conduction]], [[Phase change]], [[Fins and extended surfaces]], [[Joule heating]], [[Electrical networks]], [[Electrostatics]], [[Pendulum dynamics]], [[Finite element verification]], [[Ansys Mechanical APDL]], [[Ansys VM 061-090]], [[Ansys VM 121-150]]

## Flags
- Every case has a companion input-listing page (Hlp_V_VM<N>TXT.html, file vm<N>.dat) with the full APDL deck; not read in this pass, per slice instructions.
- VM97 is not self-contained: it needs supplemental files vm97_1.cdb and vm97_2.cdb from the VM2024R2_MAPDL.zip download placed in the working directory (VM97).
- Suspected erratum: the VM118 overview labels the analysis type "(CIRCU124 = 0)" where every neighbouring case reads "(ANTYPE = 0)" (VM118).
- VM112 takes its test case description, properties, and loading from VM111 by reference; VM105 notes the problem can also be run with the axisymmetric option as in VM102. Both cross-references stay inside this slice.
- VM91 ratio column reads 0.000 wherever the target is zero; use the absolute deflections there, not the ratio (VM91).
- Titles of VM96 and VM101 differ only by a comma; VM96 is the SOLID87 tetrahedral version, VM101 the SOLID70 sector version.
- No case in this slice cites a case outside VM91 to VM120; nothing to stitch with the neighbouring slices beyond the shared element types.
