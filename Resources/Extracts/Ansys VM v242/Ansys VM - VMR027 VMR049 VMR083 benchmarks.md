---
source: Ansys Mechanical APDL Verification Manual, Release 2024 R2, ANSYS Inc.
pages: VMR027, VMR049, VMR083 benchmarks
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Twenty-two benchmark pages from Part III (NAFEMS Benchmarks) of the manual. Ten VMR027 tests exercise power-law creep on a 100 mm square (plane stress or plane strain) and one cube: secondary, primary, stepped-load and combined primary-secondary variants, under load, displacement or shear. Ten VMR049 tests cover six creep cases (constant load, constant displacement, variable load, pressurised cylinder, twisted square shaft, thermally driven sphere slice) and four plasticity cases (plane strain, plane stress, 3D, pressurised cylinder; perfect plasticity and isotropic hardening). Two VMR083 tests verify exterior acoustic radiation (pulsating sphere, cylinder with vibrating lateral surface). Every page follows the same template: test description, geometry, material and law constants, boundary conditions, loading, then result blocks per element type giving the MAPDL value, a RATIO against the reference, and the input file name. The VMR027 pages state only that "Results are tabulated and displayed as in the NAFEMS manual" (ANSYS Inc.); the underlying reports are named in the Part III overview, which is a neighbouring slice.

## Key ideas
- One shared model for the VMR027 series: square L = 100 mm, E = 200e3 N/mm², nu = 0.3, creep law with n = 5; only the loading mode and time exponent change between tests (VMR027-3A).
- Secondary creep means m = 1, primary means m = 0.5 in the same law; the 10-series repeats the 3-series with m = 0.5 (VMR027-10A).
- Stepped-load tests change the applied stress at a stated time: 200 to 250 N/mm² at t = 100 h (VMR027-10C), 100 to 110 N/mm² at t = 10000 h (VMR027-12C).
- Combined primary-secondary law with two terms is exercised under displacement (VMR027-12B) and stepped load (VMR027-12C).
- Element coverage in 2D creep tests is SHELL181, PLANE182, PLANE183, SHELL281; the plane strain case drops the shells (VMR027-5B); the 3D case uses SOLID185, SOLID186, SOLID187 with both isotropic and anisotropic creep options returning identical values (VMR027-6B).
- VMR049-CR1 runs the same box through all three law variants in one page: inputs cr1a (secondary), cr1b (primary), cr1c (combined), in that order (VMR049-CR1).
- VMR049-CR2 pairs a 2D plane stress case (m = 0.5) with a 3D case (m = 1) under prescribed displacement only (VMR049-CR2).
- The pressurised thick cylinder compares elastic and steady-state radial and hoop stresses over 100 to 200 mm radius, quoted at r = 175 mm (VMR049-CR4).
- Torsional creep uses a soft bar (E = 10 N/mm²) with m = -0.5 and multi-point constraints tying the axial displacement of two faces (VMR049-CR5).
- Thermally induced creep prescribes a radial temperature field and an Arrhenius factor f(T) = e^(-12500/T) (VMR049-CR6).
- The plasticity trio PL1, PL2, PL3 marches one element through 8 or 12 displacement increments of R = 2.5e-5, hitting first yield, plastic flow, elastic unloading and plastic reloading in sequence; each has two input sets (a, b) matching the two listed plasticity models, with the (a) blocks returning SEFF equal to the 5.0 N/mm² yield stress (VMR049-PL1, VMR049-PL2, VMR049-PL3).
- PL5 loads the cylinder bore in 4 pressure steps with separate schedules for perfect plasticity and isotropic hardening (VMR049-PL5).
- Acoustic test CA1 checks the sound pressure level spectrum of a pulsating sphere at r = 1 m and r = 15 m against analytical values over 0 to 100 Hz and 100 to 500 Hz; ratios stay within 0.14 per cent (VMR083-CA1).
- Acoustic test CA2 checks the normalised directivity of a cylinder at r = 100 m for wave numbers k = 1 and k = 2 against NADwork 3.2 results and cites Seybert et al. 1985 as a numerical reference (VMR083-CA2).
- Agreement is single-value per element and mostly within a few per cent of unity; outliers are listed under Flags.

## Equations that matter
$$\varepsilon = A\,\sigma^{n}\,t^{m}$$
Power-law creep used throughout both creep series; m = 1 secondary, m = 0.5 primary (VMR027-3A, VMR049-CR1).

$$\varepsilon = A_{1}\,\sigma^{n_{1}}\,t + A_{2}\,\sigma^{n_{2}}\,t^{m}$$
Combined primary-secondary creep; n1 = n2 = 5, m = 0.5 (VMR027-12B, VMR049-CR1).

$$\frac{d\varepsilon}{dt} = A\,\sigma^{n}\,t^{m}$$
Rate form for torsional creep; A = 1.0e4, n = 5, m = -0.5, t in hours, sigma in N/mm² (VMR049-CR5).

$$\frac{d\varepsilon}{dt} = A\,\sigma^{n}\,e^{-12500/T}$$
Thermally activated creep, T in K; A = 3.0e-6, n = 5.5 (VMR049-CR6).

$$T = 333\,\left(1 + \frac{100}{r}\right)$$
Prescribed nodal temperature field, r measured from the sphere centre (VMR049-CR6).

The source numbers none of its equations; the two analytical acoustic formulas (pressure, SPL in dB) appear only as embedded graphics (VMR083-CA1).

## Numbers worth citing
- Creep constant A = 3.125e-14 per hour, sigma in N/mm², n = 5: the shared constant for the VMR027 squares and VMR049-CR1, CR2, CR4 (VMR027-3A).
- E = 200e3 N/mm², nu = 0.3: all VMR027 tests and VMR049-CR1 to CR4 (VMR027-3A).
- Combined law constants A1 = 1e-16, A2 = 1e-14, n1 = n2 = 5, m = 0.5, at sigma = 100 N/mm² (VMR049-CR1).
- Secondary creep target at t = 1000 h under sigma = 200 N/mm² biaxial: ECR2X = 10.0000, ECR2Y = -5.0000, ratio 1.0000, all four elements (VMR049-CR1).
- Cylinder creep: R1 = 100 mm, R2 = 200 mm, H = 25 mm, P = 200 N/mm²; steady-state hoop stress at r = 175 mm: 229.4624 (PLANE182), 229.6722 (PLANE183), ratios 0.9991 and 1.0000 (VMR049-CR4).
- Torsion: L1 = 1 mm, L2 = 2 mm, L3 = 0.2 mm, twist beta = 0.01 rad per unit length, E = 10.0 N/mm²; SYZ2 = 0.0141 to 0.0143 across SOLID185/186/187 (VMR049-CR5).
- Thermal creep sphere slice: R1 = 200 mm, R2 = 500 mm, 10 degree slice, P = 30 N/mm², E = 10e3 N/mm², nu = 0.25; effective stresses SR205 = 11.2551, SR350 = 17.5837, SR495 = 21.1643 (PLANE182, 0 to 10 h log scale) (VMR049-CR6).
- Plasticity unit square: L = 1.0 mm, E = 250e3 N/mm², nu = 0.25, yield 5.0 N/mm², tangent modulus ET = 50e3 N/mm², increment R = 2.5e-5 (VMR049-PL1).
- PL5 cylinder: R1 = 100 mm, R2 = 200 mm, H = 100 mm, E = 21.0e3 N/mm², nu = 0.3, yield 24.0 N/mm², ET = 4.2e3 N/mm²; bore pressure steps 10, 14, 16.6, 19.2 N/mm² (perfect) and 10, 14, 24, 34 N/mm² (hardening) (VMR049-PL5).
- Air: rho = 1.225 kg/m³, c = 340 m/s, both acoustic tests (VMR083-CA1).
- Sphere SPL at vn = 0.1 m/s: 122.25 dB at r = 1 m and 98.726 dB at r = 15 m, both at 100 Hz, ratios 1.0000 (VMR083-CA1).
- Reference pressure pref = 2e-5 N/m² for dB conversion (VMR083-CA1).
- Cylinder directivity at vn = 1.0 m/s, r = 100 m: normalised pressure 0.772 at theta = 0, k = 1; deep null 0.099 at theta = 30 degrees, k = 2 (VMR083-CA2).

## Definitions introduced
- pref - reference pressure for sound pressure level, 2e-5 N/m² by default (VMR083-CA1).
- Normalised sound pressure - pressure divided by the value at r = 100 m, theta = 90 degrees (VMR083-CA2).
- Prms (as used) - root mean square of peak pressure in the modal and harmonic analysis (VMR083-CA1).

## Figures and tables to return to
- Unnumbered figure (gvmr027_4c.svg) - the only load diagram in the slice; shows the equivalent edge shear force distribution tau/6, 2 tau/3, tau/6 needed to reproduce the shear case (VMR027-4C).
- Step schedule table - 8-step displacement history with the stress state named per step (first yield, plastic flow, elastic unloading, plastic reloading) (VMR049-PL1, repeated in VMR049-PL2).
- 12-step displacement schedule for the 3D case (VMR049-PL3).
- 4-step pressure schedule, separate columns for perfect plasticity and isotropic hardening (VMR049-PL5).
- Two equation graphics for analytical pressure and SPL (VMR083-CA1).
- Every page: results block listing MAPDL value, RATIO and input file per element type; these are the certification targets.

## Where to find what
| Test | Title | Analysis type | Elements | Reference |
|---|---|---|---|---|
| VMR027-3A | 2D Plane Stress - Biaxial (negative) Load Secondary Creep | Creep (secondary) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR027-3B | 2D Plane Stress - Biaxial (negative) Displacement Secondary Creep | Creep (secondary) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR027-4C | 2D Plane Stress - Shear Loading Secondary Creep | Creep (secondary) | SHELL181, PLANE182, PLANE183, 281 (labelled PLANE281) | NAFEMS manual (not named in file) |
| VMR027-5B | 2D Plane Strain - Biaxial Displacement Secondary Creep | Creep (secondary) | PLANE182, PLANE183 | NAFEMS manual (not named in file) |
| VMR027-6B | 3D - Triaxial Displacement Secondary Creep | Creep (secondary) | SOLID185, SOLID186, SOLID187 | NAFEMS manual (not named in file) |
| VMR027-10A | 2D Plane Stress - Biaxial (negative) Load Primary Creep | Creep (primary) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR027-10B | 2D Plane Stress - Biaxial (negative) Displacement Primary Creep | Creep (primary) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR027-10C | 2D Plane Stress - Biaxial (negative) Stepped Load - Primary Creep | Creep (primary, stepped load) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR027-12B | 2D Plane Stress - Uniaxial Displacement Primary-Secondary Creep | Creep (combined) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR027-12C | 2D Plane Stress - Stepped Load Primary - Secondary Creep | Creep (combined, stepped load) | SHELL181, PLANE182, PLANE183, SHELL281 | NAFEMS manual (not named in file) |
| VMR049-CR1 | Constant-Load Creep Benchmark | Creep (secondary, primary, combined) | SHELL181, PLANE182, PLANE183, SHELL281 | not stated |
| VMR049-CR2 | Constant-Displacement Creep Benchmark | Creep (2D primary, 3D secondary) | SHELL181, PLANE182, PLANE183, SOLID185, SOLID187, SHELL281 | not stated |
| VMR049-CR3 | Variable-Load Uniaxial Creep Benchmark | Creep (primary, stepped load) | SHELL181, PLANE182, PLANE183, SHELL281 | not stated |
| VMR049-CR4 | Pressurised Cylinder Creep Benchmark | Creep (axisymmetric, secondary) | PLANE182, PLANE183 | not stated |
| VMR049-CR5 | Torsional Creep of Square Shaft | Creep (3D torsion, m = -0.5) | SOLID185, SOLID186, SOLID187 | not stated |
| VMR049-CR6 | Thermally Induced Creep Benchmark | Creep (axisymmetric, thermal) | PLANE182, PLANE183 | not stated |
| VMR049-PL1 | 2D Plane Strain Plasticity Benchmark | Plasticity (incremental) | PLANE182, PLANE183 | not stated |
| VMR049-PL2 | 2D Plane Stress Plasticity Benchmark | Plasticity (incremental) | SHELL181, PLANE182, PLANE183, SHELL281 | not stated |
| VMR049-PL3 | 3D Plasticity Benchmark | Plasticity (incremental) | SOLID185, SOLID186, SOLID187, SOLSH190 | not stated |
| VMR049-PL5 | Pressurised Cylinder Plasticity Benchmark | Plasticity (axisymmetric, stepped pressure) | PLANE182, PLANE183 | not stated |
| VMR083-CA1 | Sound Radiation of a Vibrating Sphere | Acoustic radiation (modal and harmonic) | 221 (per input listing name) | analytical solution (formulas as graphics) |
| VMR083-CA2 | Sound Radiation of a Cylinder with Vibrating Lateral Surface | Acoustic radiation | 221 (per input listing name) | NAFEMS article, NADwork 3.2; Seybert et al., J. Acous. Soc. Am. 77(2), 1985 |

## Links
[[NAFEMS]], [[Creep]], [[Plasticity]], [[Acoustic radiation]], [[Waves]], [[Ansys Mechanical APDL]]

## Flags
- Input listings exist as separate *txt.html pages (one per .dat file, linked from every test); not read per slice instructions.
- VMR027-4C: the fourth results block is labelled PLANE281 while its input is vmr027-cr4c-281 and every sibling test uses SHELL281; suspected erratum. Its ratio 0.8176 is also the largest deviation in the VMR027 set.
- VMR049-CR1: result blocks (b) and (c) are labelled PLANE181 where block (a) uses SHELL181; suspected erratum. The combined-law line also prints without an equals sign and sets n1, n2 as subscripts on sigma.
- VMR049-PL5: SAXI ratios 0.8671 (PLANE182) and 1.1327 (PLANE183) in the (b) case sit well off unity; the page offers no comment.
- The creep constant A is not stated in several VMR027 tables (3B, 4C, 10A, 10B, 10C, 12B, 12C give n and m only).
- VMR049-CR6 result labels SR205, SR350, SR495 are not defined in the file.
- No VMR049-PL4 in this build: navigation runs PL3 directly to PL5. VMR049-CR1 follows VMR031-T3, so no CR0 either.
- VMR083-CA1: the analytical pressure and SPL formulas are embedded SVG graphics; contents not extracted.
- Neither VMR083 page names its element type in text; 221 comes from the input listing names (vmr083-CA1-221.dat, vmr083-CA2-221.dat).
- Cross-slice stitching: VMR027-3A follows VMR020-T8B; VMR027-12C precedes VMR029-T1; VMR049-CR1 follows VMR031-T3; VMR083-CA2 precedes Part IV (NRC Piping Benchmarks). The Part III overview naming the NAFEMS source reports is a neighbouring slice.
- Source has no page numbers; benchmark IDs serve as locators throughout this note.
- Cosmetic: VMR027-6B results header reads ANSYS where siblings read Mechanical APDL; VMR027 tables misspell Geometric as "Geometic".
