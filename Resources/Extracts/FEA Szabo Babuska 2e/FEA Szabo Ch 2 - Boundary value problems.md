---
source: Finite Element Analysis. Method, Verification and Validation, 2nd edition, Barna Szabo and Ivo Babuska, Wiley 2021
pages: 51-90
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
The chapter builds the mathematical problems that the rest of the book discretises. It derives strong forms from first principles for two physical settings, heat conduction and linear elasticity, then converts each to its generalised (weak) formulation via test functions and the divergence theorem, ending in the same pattern both times: bilinear form, linear functional, energy space, minimum potential energy. Around this spine sit the boundary condition taxonomy (essential, natural, spring, plus "conditions of convenience": symmetry, antisymmetry, periodicity), dimensional reduction (planar, axisymmetric, bar; plane strain and plane stress), incompressible materials with the Stokes flow analogy, the RMS stress measure and its energy-norm bounds, virtual work, uniqueness and rigid body constraints, and residual stresses. Index notation is introduced here and used from now on. Numerical solutions in the book come from StressCheck (p. 51).

## Key ideas
- Index notation rules: repeated indices sum, a comma prefix means differentiation, $u_{i,i}$ is the divergence (p. 52).
- The scalar elliptic problem $-\mathrm{div}([\kappa]\,\mathrm{grad}\,u)+cu=f$ generalises the 1D model problem of Chapter 1 to two and three dimensions (p. 53).
- Dirichlet is the essential condition; Neumann and Robin are natural conditions; the boundary segments $\partial\Omega_u$, $\partial\Omega_q$, $\partial\Omega_R$, $\partial\Omega_p$ are non-overlapping, cover $\partial\Omega$, and any may be empty (p. 53).
- Generalised formulation: find $u\in\tilde E(\Omega)$ with $B(u,v)=F(v)$ for all $v\in E^0(\Omega)$; the exact solution minimises the potential energy on the admissible space (p. 55).
- Two potential energy definitions, $\pi$ and $\Pi$, differ by a constant, so share a minimiser; $\Pi$ vanishes in the special cases (free thermal expansion, rigid spring displacement) where $\pi$ does not (p. 55, p. 80).
- In 2D and 3D, functions in $E(\Omega)$ need not be continuous or bounded ($u=\log|\log r|$ is the counterexample); therefore concentrated fluxes and point constraints are inadmissible data (p. 55).
- Heat conduction rests on two relationships: the conservation law and Fourier's law; the conductivity matrix $[K]$ is symmetric positive-definite and the model is linear only while $[K]$ is taken independent of $u$ (p. 56-57).
- Pure flux (Neumann) stationary problems need the compatibility condition (2.28) and the solution is unique only up to a constant (p. 58).
- Radiation is a non-linear boundary condition (flux proportional to the difference of fourth powers of absolute temperature); deferred to Section 9.1.1 (p. 58).
- On a plane of symmetry $q_n=0$; on a plane of antisymmetry $u=0$; periodic pairs carry $u(P^+)=u(P^-)$, $q_n^+=-q_n^-$ (p. 59-60).
- Any loading splits into even plus odd parts, so periodic problems on symmetric periodic subdomains reduce to symmetry and antisymmetry conditions, which are far simpler to implement than coupled periodic constraints (p. 60-61).
- The 2D plate model is either exact (thickness large, data z-independent, faces insulated) or the first term of an expansion in $z$, with face flux or convection folded into a modified source $\bar Q$ (p. 62).
- On the $z$ axis of an axisymmetric model the implied condition is zero flux; prescribing an essential condition there is not meaningful (p. 65).
- Elasticity strong form rests on three relationships: strain-displacement, stress-strain (Hooke), equilibrium; moment equilibrium without body moments makes the stress tensor symmetric (p. 67-69).
- Elastic boundary conditions: prescribed displacement (kinematic), prescribed traction, and the linear spring (Winkler) condition; any combination may appear on a segment, most conveniently in the normal-tangent frame (p. 71-72).
- Plane strain is exact by periodic extension under its stated conditions; plane stress is an approximation whose error depends on $\nu$ and the length $\ell$, exact only as $\ell\to 0$ (p. 74).
- First fundamental problem: homogeneous isotropic body, tractions only, zero body force; the stress field is independent of $E$ and $\nu$, hence identical for plane stress and plane strain (Remark 2.4, p. 74).
- At $\nu=1/2$ the mean stress $\sigma_0$ cannot be computed from strains; the incompressible formulation carries the constraint $u_{i,i}=3\alpha\mathcal{T}_\Delta$ and a compatibility condition on prescribed boundary displacements (p. 76-77).
- Stokes flow ($Re<1$) is formally incompressible elasticity with velocity for displacement, pressure for mean stress, and dynamic viscosity $\mu$ for $E/3$ (p. 78).
- Material properties are empirical data valid in narrow ranges; temperature-dependent conductivity makes the problem non-linear (Section 9.1.2) (Remark 2.5, p. 78).
- The RMS stress error is bounded above and below by the energy-norm error through the extreme eigenvalues of $[E]$; as $\nu\to 1/2$, $\Lambda_{\max}\to\infty$ and $\sigma_{kk}$ computed from strains magnifies the error, while shear stresses and normal stress differences stay well behaved (p. 82-83).
- Principle of virtual work: virtual work of external forces equals virtual work of internal stresses; it derives from equilibrium alone, so it holds for any continuum (p. 83).
- With no displacement or spring conditions, six test functions (three translations, three rotations) annihilate $B$, so the data must satisfy six equilibrium conditions and rigid body constraints must be imposed: six displacement components at three non-collinear points, coefficient matrix non-singular (p. 84-85).
- Symmetry, antisymmetry and periodicity cannot be used for general anisotropic materials; the exception is orthotropy with material axes aligned to the geometric symmetry (Remark 2.8, p. 87).
- Residual stresses (bulk from forming, surface layers from machining) enter Hooke's law as an additive $\sigma^{(0)}_{ij}$; a superposition argument shows the displacement field after a cut depends on the residual field and the current domain, not on the order of previous cuts (p. 87-88).
- "A mathematical model must never be confused with the physical reality" (Szabo and Babuska, p. 89).

## Equations that matter
$$-\mathrm{div}\left([\kappa]\,\mathrm{grad}\,u\right)+cu=f(x,y,z)\tag{2.3}$$
Strong form of the scalar elliptic boundary value problem (p. 53).

$$B(u,v)=\int_\Omega \kappa_{ij}u_{,j}v_{,i}\,dV+\int_\Omega cuv\,dV+\int_{\partial\Omega_R}h_R uv\,dS\tag{2.10}$$
Bilinear form of the scalar problem, Robin term included (p. 54).

$$F(v)=\int_\Omega fv\,dV-\int_{\partial\Omega_q}q_n v\,dS+\int_{\partial\Omega_R}h_R u_R v\,dS\tag{2.11}$$
The matching linear functional; together they state the generalised formulation (p. 54).

$$\mathbf{q}=-[K]\,\mathrm{grad}\,u\tag{2.21}$$
Fourier's law; the sign sends heat from high to low temperature (p. 57).

$$\mathrm{div}\left([K]\,\mathrm{grad}\,u\right)+Q=c\rho\frac{\partial u}{\partial t}\tag{2.24}$$
Heat equation, conservation law combined with Fourier's law (p. 57).

$$q_n=h_c(u-u_c)\tag{2.27}$$
Convective (Robin) boundary condition on $\partial\Omega_c$ (p. 58).

$$\int_\Omega Q\,dV=\int_{\partial\Omega}q_n\,dS\tag{2.28}$$
Compatibility condition when flux is prescribed on the whole boundary; the scalar-problem analogue is eq. (2.12) (p. 58, p. 54).

$$\frac{1}{r}\frac{\partial}{\partial r}\left(rk_r\frac{\partial u}{\partial r}\right)+\frac{\partial}{\partial z}\left(k_z\frac{\partial u}{\partial z}\right)+Q=c\rho\frac{\partial u}{\partial t}\tag{2.40}$$
Axisymmetric heat conduction in cylindrical coordinates (p. 65).

$$\epsilon_{ij}\overset{\text{def}}{=}\frac{1}{2}\left(u_{i,j}+u_{j,i}\right)\tag{2.46}$$
Infinitesimal strain tensor (p. 68).

$$\sigma_{ij}=\lambda\epsilon_{kk}\delta_{ij}+2G\epsilon_{ij}-(3\lambda+2G)\alpha\mathcal{T}_\Delta\delta_{ij}\tag{2.54}$$
Hooke's law inverted to stress, thermal strain included; the strain form is eq. (2.53) (p. 69).

$$\lambda\overset{\text{def}}{=}\frac{E\nu}{(1+\nu)(1-2\nu)},\qquad G\overset{\text{def}}{=}\frac{E}{2(1+\nu)}\tag{2.55}$$
Lame constants from engineering constants (p. 69).

$$\sigma_{ij}=C_{ijkl}(\epsilon_{kl}-\alpha_{kl}\mathcal{T}_\Delta)\tag{2.56}$$
Generalised Hooke's law; 21 independent elastic constants, 6 thermal expansion coefficients at most (p. 69).

$$\sigma_{ij,j}+F_i=\varrho\frac{\partial^2 u_i}{\partial t^2}\tag{2.60}$$
Equations of motion; static equilibrium (2.61) drops the inertia term (p. 70).

$$Gu_{i,jj}+(\lambda+G)u_{j,ji}+F_i=\varrho\frac{\partial^2 u_i}{\partial t^2}\tag{2.62}$$
Navier equations; the elastostatic thermal form is eq. (2.63) (p. 70).

$$T_i=c_{ij}(d_j-u_j)\tag{2.64}$$
Linear spring (Winkler) boundary condition, $c_{ij}$ positive-definite in N/m^3 (p. 71).

$$\mu u_{i,jj}=p_{,i}-F_i,\qquad u_{i,i}=0\tag{2.89, 2.90}$$
Stokes equations; incompressible elasticity with $\mu$ in place of $E/3$ (p. 78).

$$\int_\Omega \sigma_{ij}\epsilon^{(v)}_{ij}\,dV=\int_\Omega F_i v_i\,dV+\int_{\partial\Omega}T_i v_i\,dS\tag{2.94}$$
Generic principle of virtual work, the seed of the elasticity weak form (p. 79, p. 83).

$$\pi(\mathbf{u})\overset{\text{def}}{=}\frac{1}{2}B(\mathbf{u},\mathbf{u})-F(\mathbf{u}),\qquad \pi(\mathbf{u}_{EX})=\min_{\mathbf{u}\in\tilde E(\Omega)}\pi(\mathbf{u})\tag{2.100, 2.101}$$
Principle of minimum potential energy for elasticity; with hierarchic FE spaces the potential energy converges monotonically (p. 80).

$$S(\boldsymbol{\sigma})\overset{\text{def}}{=}\left(\frac{1}{V}\int_\Omega\{\sigma\}^T\{\sigma\}\,dV\right)^{1/2}\tag{2.110}$$
RMS measure of stress (p. 82).

$$\sqrt{\frac{2\Lambda_{\min}}{V}}\,\lVert\mathbf{u}_{FE}-\mathbf{u}_{EX}\rVert_{E(\Omega)}\le S(\boldsymbol{\sigma}_{FE}-\boldsymbol{\sigma}_{EX})\le\sqrt{\frac{2\Lambda_{\max}}{V}}\,\lVert\mathbf{u}_{FE}-\mathbf{u}_{EX}\rVert_{E(\Omega)}\tag{2.114}$$
Two-sided bound on RMS stress error by energy-norm error via the eigenvalues of $[E]$ (p. 82).

$$F(\mathbf{v})=0:\quad\int_\Omega F_i v_i^{(k)}\,dV+\int_{\partial\Omega}T_i v_i^{(k)}\,dS=0,\qquad k=1,2,\dots,6\tag{2.117}$$
Equilibrium of forces and moments, required when no displacement or spring conditions constrain the body (p. 84).

$$\sigma_{ij}=\sigma^{(0)}_{ij}+C_{ijkl}(\epsilon_{kl}-\alpha_{kl}\mathcal{T}_\Delta)\tag{2.122}$$
Hooke's law with a residual stress field; $\sigma^{(0)}_{ij}$ satisfies equilibrium and stress-free boundary conditions (2.121) in the reference configuration (p. 87).

## Numbers worth citing
- Admissible Poisson's ratio: $-1<\nu<1/2$, typically $0\le\nu<1/2$ (p. 69).
- Anisotropy: at most 21 independent elastic constants in $C_{ijkl}$, 6 independent thermal expansion coefficients (p. 69).
- Cooling fin pipe (Example 2.4): inner radius 30.0 mm, outer 32.0 mm, seven fins, $k=0.0236$ W/(mm K), $h_c=1.8\times10^{-4}$ W/(mm^2 K), inner surface 800 K, convective medium 300 K; heat loss converges to 1816 W/m for the one-fourteenth sector, 14 times that for the pipe (p. 63).
- Cylindrical pipe under external pressure 20 MPa, $r_o=200$ mm, $r_i=175$ mm, $E=70.0$ GPa, $\nu=0.3$ (Exercise 2.30, Case 1): plane stress equals the 3D solution exactly in energy norm and in maximum von Mises stress; the maximum von Mises stress is 170.7 MPa (p. 74-75).
- AISI 304 stainless steel: $k$ rises from about 15 to about 20 W/(m C) between 0 and 400 C; over 100 to 200 C the data uncertainty is about the same size as the change in mean value (Remark 2.5, p. 78).
- Published thermal conductivity of pure iron spans 71.8 to 80.4 W/(m K) across handbooks (p. 78).
- Machining-induced residual stress layer: typically 0.2 to 1 mm deep (p. 87); some aluminium plates are stretched 1.5 to 3.0 percent strain in rolling to relieve bulk residual stress (footnote, p. 87).
- Aluminium (Exercise 2.43 data): $E=72.0\times10^3$ MPa, $G=28.0\times10^3$ MPa, $\varrho=2800$ kg/m^3, $\alpha=23.6\times10^{-6}$/K. Stainless steel: $E=190\times10^3$ MPa, $G=75.0\times10^3$ MPa, $\varrho=7920$ kg/m^3, $\alpha=17.3\times10^{-6}$/K (p. 88).
- Stokes flow regime: $Re<1$ (p. 78).

## Definitions introduced
- Dummy (repeated) indices - summation indices whose designation is immaterial (p. 52).
- Permutation symbol $e_{ijk}$ - 0, 1 or -1 by permutation parity; carries the cross product in index notation (p. 52).
- Essential vs natural boundary conditions - Dirichlet vs Neumann and Robin (p. 53).
- Flux vector - $\mathbf{q}=-[\kappa]\,\mathrm{grad}\,u$; normal flux $q_n=\mathbf{q}\cdot\mathbf{n}$ (p. 53).
- Boundary conditions of convenience - symmetry, antisymmetry, periodicity used to shrink the domain (p. 53, p. 59).
- Energy space $E(\Omega)$, energy norm $\lVert u\rVert_E=\sqrt{B(u,u)/2}$, admissible space $\tilde E(\Omega)$, test space $E^0(\Omega)$ (p. 54-55; elasticity p. 79-80).
- Generalised solution - a function satisfying $B(u,v)=F(v)$ for all test functions (p. 55).
- Stationary (steady state) problem - time-independent solution, viewable as a time-dependent problem at $t=\infty$ (p. 57).
- Symmetric and antisymmetric function - equal values, or equal magnitude and opposite sign, at symmetrically located points (p. 59).
- Even and odd parts - $f_e=(f(x)+f(-x))/2$, $f_o=(f(x)-f(-x))/2$ (p. 60-61).
- Engineering shear strain $\gamma_{xy}=2\epsilon_{xy}$ (p. 67-68).
- Thermal vs mechanical strain - total strain minus $\alpha\mathcal{T}_\Delta$ (p. 69).
- Lame constants $\lambda$, $G$; $G$ also shear modulus or modulus of rigidity (p. 69).
- Traction - force per unit area acting on the boundary (p. 71).
- Winkler spring - distributed spring with coefficients independent of displacement (p. 71).
- First fundamental boundary value problem of elasticity - homogeneous isotropic body, tractions only, zero body force (p. 74).
- Volumetric strain $\epsilon_{vol}=\epsilon_{kk}$; mean stress $\sigma_0=\sigma_{kk}/3$ (p. 76).
- RMS measure of stress - volume-averaged root mean square of the stress vector (p. 82).
- Virtual displacement - arbitrary displacement field imposed independently of the applied loads (p. 83).
- Rigid body constraints - six displacement components fixed at three non-collinear points to remove rigid body modes (p. 85).
- Bulk residual stresses - residual stresses present in metal stock from forming (p. 87).

## Figures and tables to return to
- Fig. 2.1 - control volume and flux notation used to derive the heat conservation law (p. 56).
- Fig. 2.2 - the periodic five-hole disc that anchors Examples 2.2 and 2.3 and Exercise 2.29 (p. 59).
- Fig. 2.3 - periodic solution split into symmetric and antisymmetric parts, the picture behind the even/odd trick (p. 61).
- Fig. 2.4 - notation for 2D domains (mid-surface, $\Gamma$, normal-tangent frame) reused across planar formulations (p. 62).
- Fig. 2.5 - solution domain and mesh for the cooling fin problem, dimensions in mm (p. 63).
- Fig. 2.7 - stress component sign convention on the volume element; the indexing rules live here (p. 68).
- Fig. 2.8 - spring boundary condition schematic, the meaning of $c_i\Delta A$ (p. 71).
- Fig. 2.9 - symmetry vs antisymmetry of vectors in 2D; the rule for which components vanish on each plane (p. 72).
- Fig. 2.10 - prismatic body notation ($\Omega_\ell$, $\Gamma_\ell$, $\gamma_\pm$) for planar elasticity, plus the annular cross-section of Exercise 2.30 (p. 73).
- Table 2.1 - three boundary condition cases for the pipe segment: symmetry, antisymmetry, and direct prescription (p. 75).
- Fig. 2.11 - virtual work of $\sigma_{11}$ and $\sigma_{13}$ on the hexahedral element (p. 84).
- Fig. 2.12 - the three-point $ABC$ construction for rigid body constraints behind eq. (2.120) (p. 85).
- Fig. 2.14 - half-domain and quarter-domain reductions of the plate with a hole, with the residual rigid body modes each leaves (p. 86).
- Fig. 2.15 - successive cuts $\Gamma_1$, $\Gamma_2$ for the residual stress superposition argument (p. 88).
- Fig. 2.16 - shrink-fitted plate and shaft geometry for Exercise 2.43 (p. 89).

## Where to find what
| Topic | Pages |
|---|---|
| Index notation rules, permutation symbol, divergence theorem (2.2) | 51-52 |
| Scalar elliptic BVP, Dirichlet/Neumann/Robin conditions | 53 |
| Generalised formulation of the scalar problem, $B$, $F$, energy space | 53-55 |
| Potential energy $\pi$ vs $\Pi$, minimisation | 55 |
| Continuity of $E(\Omega)$ functions, inadmissible point data | 55 |
| Conservation law and Fourier's law | 56-57 |
| Heat equation, subdomains with different materials | 57 |
| Heat conduction boundary and initial conditions, compatibility, radiation | 58 |
| Symmetry, antisymmetry, periodicity (scalar case) | 59-60 |
| Even/odd decomposition, numerical treatment of periodic conditions | 60-61 |
| Planar (2D) heat conduction, modified source $\bar Q$ | 61-63 |
| Cooling fin example with converged heat loss | 63 |
| Variable thickness 2D conservation law | 63-64 |
| Rectangular plate, classical series solution (Example 2.5) | 64 |
| Axisymmetric heat conduction, condition on the $z$ axis | 65-66 |
| Heat conduction in a bar, fin equation | 66-67 |
| Strain-displacement relations, strain tensor | 67-68 |
| Stress notation and sign convention | 68 |
| Hooke's law, Lame constants, generalised Hooke's law | 69 |
| Equilibrium, equations of motion | 69-70 |
| Navier equations (3D) | 70 |
| Elastic boundary conditions: displacement, traction, spring; initial conditions | 71-72 |
| Symmetry, antisymmetry, periodicity for vector problems | 72-73 |
| Planar elasticity notation, plane strain, plane stress | 73-74 |
| First fundamental problem (Remark 2.4), pipe exercise, Table 2.1 | 74-75 |
| Navier equations in 2D | 75 |
| Axisymmetric elastostatic model | 76 |
| Incompressible elastic materials | 76-77 |
| Stokes flow | 78 |
| Empirical limits of material data (Remark 2.5) | 78 |
| Generalised formulation of elasticity, energy space | 78-80 |
| Minimum potential energy, hierarchic spaces | 80-81 |
| Isotropic case, $[D]$ and $[E]$ matrices | 81 |
| RMS measure of stress, error bounds, near-incompressibility trouble | 82-83 |
| Principle of virtual work | 83-84 |
| Uniqueness, rigid body modes, rigid body constraints | 84-87 |
| Residual stresses, modified Hooke's law, cutting argument | 87-89 |
| Chapter summary | 89 |

## Links
[[Boundary value problems]], [[Weak form]], [[Heat conduction]], [[Fourier's law]], [[Linear elasticity]], [[Hooke's law]], [[Navier equations]], [[Plane stress]], [[Plane strain]], [[Axisymmetric models]], [[Incompressible elasticity]], [[Stokes flow]], [[Principle of virtual work]], [[Minimum potential energy]], [[Energy norm]], [[Index notation]], [[Symmetry boundary conditions]], [[Residual stress]], [[FEA Szabo Ch 1 - Introduction]], [[FEA Szabo Ch 3 - Implementation]]

## Flags
- Book page 90 (PDF page 110) is blank; chapter content ends at page 89. No unreadable pages.
- Suspected erratum: Example 2.3 states the coefficient of thermal conduction as 0.161 W/(mm^2 K) (p. 61); conductivity units are W/(mm K), the printed units belong to a convection coefficient. Example 2.4 uses W/(mm K) correctly (p. 63).
- Suspected erratum: Fig. 2.16 caption reads "Notation for Exercise 2.7" but the figure serves Exercise 2.43 (p. 89).
- Continues in Chapter 3 (book p. 91): implementation of these generalised formulations in finite element software.
- Deferred forward within the book: radiation boundary condition to Section 9.1.1 (p. 58); temperature-dependent conductivity and non-linear iteration to Section 9.1.2 (p. 78); derivation of strain-displacement relations to Section 9.2.1 (p. 67); beam, plate and shell models treated separately (p. 73); traction vector definition and coordinate transformations in Appendix K (p. 71-72).
- Notation note: $\varrho$ (specific density, Ns^2/m^4) in the elasticity sections plays the role $\rho$ (kg/m^3) plays in the heat conduction sections (p. 56, p. 70).
