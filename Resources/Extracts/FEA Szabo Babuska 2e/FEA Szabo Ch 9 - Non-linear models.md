---
source: Finite Element Analysis: Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 265-288
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Chapter 9 closes the main text with a short treatment of non-linear models, framed by the hierarchic view: every mathematical model is a special case of a more comprehensive model, and testing a restrictive assumption by computation is called virtual experimentation, which forces solvers to handle non-linear problems. Four non-linearities are covered with emphasis on algorithms and worked examples: radiation and temperature-dependent coefficients in heat conduction; large strain and rotation (Almansi and Green strain tensors); structural stability and stress stiffening posed as an eigenvalue problem on a fully three-dimensional body, with beam and shell results recovered as special cases; small-strain confined plasticity in both incremental and deformation theory form (von Mises criterion, Prandtl-Reuss flow rule); and frictionless mechanical contact solved with gap elements. Each solid mechanics topic ends in a verification example against a classical solution (Euler column, Hertz sphere contact) or a benchmark (the DFG plane strain plasticity challenge), all run with p-version discretisations.

## Key ideas
- Any model is a special case of a more comprehensive model; exploring the influence of a modelling assumption on the quantities of interest is virtual experimentation (p. 265).
- Radiation is a convective boundary condition whose coefficient $h_r(u)$ depends on temperature; solve the linear problem, update the coefficient, repeat; usually very few iterations (p. 266).
- Temperature-dependent coefficients: split bilinear and linear forms into linear and non-linear parts and iterate; convergence is not guaranteed, and a failing case is loaded in small increments (p. 266).
- Almansi strain uses Eulerian coordinates, Green strain uses Lagrangian; both vanish under rigid body rotation, unlike the linear strain tensor (pp. 267-269).
- When first displacement derivatives are much smaller than unity, both tensors reduce to the infinitesimal strain (p. 268).
- Stability is analysed on a three-dimensional elastic body free of beam, plate or shell restrictions; dimensionally reduced models follow as special cases (p. 270).
- With initial stress $\sigma_{ij}^0$ the strain energy gains the term $\frac{1}{2}\int_\Omega \sigma_{ij}^0 \bar u_{\alpha,i}\bar u_{\alpha,j}\,dV$; work done by $\sigma^0_{ij}$ on the linear strain terms cancels against the initial loads (p. 270).
- Tensile initial stress raises stiffness (stress stiffening), compressive lowers it; the critical multiplier $\lambda$ where stiffness vanishes is the buckling load factor (p. 271).
- In the thin-walled problems of engineering interest the lowest $\lambda$ lie in the point spectrum (p. 271).
- Natural frequency is a function of the prestress multiplier; at buckling the frequency is zero (pp. 271-272).
- Prestress changes mode shapes, not only frequencies: the strip's 20th mode switches from torsional to bending under 150 MPa tension (p. 273).
- Predicted shell buckling loads are upper bounds; imperfection sensitivity leads practice to reduction factors of 1/2 to 1/4 (p. 274).
- Plasticity here is confined plastic flow at small strain, built from yield criterion, flow rule and hardening rule; uncontained flow (metal forming) is out of scope (p. 275).
- Incremental theory algorithm: elastic predictor at each integration point, check $F(\sigma_{ij}+d\sigma_{ij})$, re-compute $d\sigma_{ij}$ with the tangent (9.38) until $F \approx 0$; the tangent stays defined for elastic-perfectly plastic materials ($H'=0$) (p. 278).
- Deformation theory: plastic strain proportional to the stress deviator through the secant modulus; iterate $[E_{ep}]$ per integration point until equivalent stress matches the uniaxial curve within tolerance, typically 1% or less (pp. 278-279).
- The DFG benchmark (1994-1999, nine institutes) dispelled the belief that high order elements cannot solve material non-linear problems; computed quantities match the reference to four significant digits (pp. 279-281).
- Contact conditions: gap $g \ge 0$, equal and opposite tractions where $g=0$, zero traction where $g>0$; lubricated surfaces justify the frictionless assumption (p. 281).
- The 1D two-bar example splits into two steps, gap-closing force $F_0$ then contact force $F_c = q(F-F_0)$; in two and three dimensions the contact surface itself depends on the contact force (pp. 281-283).
- Gap elements approximate $g$ by Lagrange polynomials at optimal collocation points; the sign of the Jacobian determinant flags partial penetration (pp. 283-284).
- The contact algorithm applies tractions proportional to the negative gap, scales them via strain-energy spring rates $k = F^2/(2U)$, updates coordinates and iterates; contact meshes need not conform (p. 285).
- Hertz contact: computed maximum pressure sits within 0.2% of the classical value; the contact radius differs because the classical solution approximates the spheres by paraboloids of revolution (pp. 286-287).
- For strength checks in contact, the maximum shear (von Mises) stress lies a small distance below the contact area; the maximum tensile stress lies on the spherical boundary outside it (p. 287).
- Summary: choose the simplest model that meets the error tolerance on the quantities of interest; non-linear models demand more input data and so carry more uncertainty (p. 287).

## Equations that matter
$$q_n = \kappa f_s f_e\,(u^4 - u_R^4) \tag{9.1}$$
Radiation flux between bodies at absolute temperatures $u$, $u_R$; $f_s$ shape factor, $f_e$ emissivity (p. 265).

$$e_{ij} = \tfrac{1}{2}(u_{i,j} + u_{j,i} - u_{k,i}u_{k,j}) \tag{9.2}$$
Almansi strain tensor, displacement as a function of Eulerian coordinates (p. 267).

$$E_{ij} = \tfrac{1}{2}(U_{i,j} + U_{j,i} + U_{k,i}U_{k,j}) \tag{9.4}$$
Green strain tensor, displacement as a function of Lagrangian coordinates (p. 268).

$$\epsilon_{ij} = \tfrac{1}{2}(u_{i,j} + u_{j,i}) \tag{9.6}$$
Infinitesimal strain, the common limit of (9.2) and (9.4) at small displacement gradients (p. 268).

$$B_\lambda(\bar u_i, v_i) \equiv B(\bar u_i, v_i) - \lambda G(\bar u_i, v_i) = F(v_i) \tag{9.16}$$
Prestressed equilibrium with $\sigma^0_{ij} = \lambda\sigma^\star_{ij}$; the $\lambda$ where (9.16) loses unique solvability form the spectrum, and buckling loads are its lowest points (p. 271).

$$B_\lambda(\bar u_i, v_i) - \omega^2 \int_\Omega \rho\,\bar u_i v_i\,dV = 0 \tag{9.17}$$
Free vibration under initial stress; natural frequency becomes a function of $\lambda$ and reaches zero at buckling (p. 271).

$$F_{cr} = \frac{\pi^2 EI}{4L^2} \tag{9.26}$$
Classical buckling load of the clamped-free column, the verification target for Example 9.3 (p. 273).

$$\bar\sigma = \sqrt{\tfrac{1}{2}\left[(\sigma_{11}-\sigma_{22})^2 + (\sigma_{22}-\sigma_{33})^2 + (\sigma_{33}-\sigma_{11})^2 + 6(\sigma_{12}+\sigma_{23}+\sigma_{31})\right]} \tag{9.28}$$
Equivalent (von Mises) stress, $\sqrt{J_2}$ scaled to equal the uniaxial stress in a uniaxial test (p. 276).

$$\bar\epsilon^{\,p} = \frac{\sqrt{2}}{3}\sqrt{(\epsilon_1^p-\epsilon_2^p)^2 + (\epsilon_2^p-\epsilon_3^p)^2 + (\epsilon_3^p-\epsilon_1^p)^2} \tag{9.30}$$
Equivalent plastic strain, obtained from the equivalent elastic strain (9.29) by setting $\nu = 1/2$ (p. 276).

$$F(\sigma_{ij}, \bar\epsilon^{\,p}) = \bar\sigma - H(\bar\epsilon^{\,p}) \tag{9.32}$$
Yield function: $F<0$ elastic, $F=0$ admits plastic flow, $F>0$ inadmissible (the consistency condition) (p. 277).

$$d\epsilon^p_{ij} = \frac{\partial F}{\partial \sigma_{ij}}\, d\bar\epsilon^{\,p} \tag{9.34}$$
Prandtl-Reuss associative flow rule (p. 277).

$$\bar\epsilon = \frac{\bar\sigma}{E} + \frac{3}{7}\frac{S_{70E}}{E}\left(\frac{\bar\sigma}{S_{70E}}\right)^n \tag{9.35}$$
Ramberg-Osgood uniaxial law; $S_{70E}$ is the stress where the 0.7E secant line meets the curve (p. 277).

$$d\sigma_{ij} = \left(C_{ijkl} - \frac{C_{ijmn}\dfrac{\partial F}{\partial\sigma_{mn}}\dfrac{\partial F}{\partial\sigma_{uv}}C_{uvkl}}{H' + C_{pqrs}\dfrac{\partial F}{\partial\sigma_{pq}}\dfrac{\partial F}{\partial\sigma_{rs}}}\right) d\epsilon_{kl} \tag{9.38}$$
Incremental elastic-plastic stress-strain relationship; bracketed tangent well defined even for $H'=0$ (p. 278).

$$\bar\epsilon^{\,p} = \left(\frac{1}{E_s} - \frac{1}{E}\right)\bar\sigma \tag{9.39}$$
Deformation theory: plastic strain from the secant modulus $E_s$, generalised to tensor form in (9.40) (p. 278).

$$g\,T_n = 0, \quad g \ge 0, \quad T_n^{(A)} = -T_n, \quad T_n^{(B)} = -T_n \tag{9.53}$$
Frictionless contact conditions in terms of the gap function and normal traction (p. 283).

$$g(\xi) = \sum_{i=1}^{n} G_i L_i(\xi), \qquad -1 \le \xi \le 1 \tag{9.61}$$
Gap function on a gap element; $G_i$ from (9.60) carries the sign of the Jacobian determinant to detect penetration (p. 284).

$$p_{\max} = 0.388\left(PE^2\,\frac{(r_1+r_2)^2}{r_1^2 r_2^2}\right)^{1/3} \tag{9.68}$$
Classical Hertz maximum contact pressure, equal materials, $\nu = 0.3$ (p. 285).

$$a_c = 1.109\left(\frac{P\,r_1 r_2}{E(r_1+r_2)}\right)^{1/3} \tag{9.69}$$
Classical Hertz contact radius, valid for $a_c \ll \min(r_1, r_2)$ (p. 285).

## Numbers worth citing
- Stefan-Boltzmann constant $\kappa = 5.699\times 10^{-8}$ W/(m$^2$ K$^4$) (p. 265).
- Surface emissivity of polished stainless steel: 0.22 at 373.15 K, 0.45 at 698.15 K (p. 266, footnote).
- Elastic strip 200 mm by 7.5 mm by 1.0 mm, $E = 2.0\times 10^5$ MPa, $\nu = 0$, 1.0 N compressive traction: buckling load factor 7.71, matching $F_{cr} = 7.71$ N from (9.26); computed with three hexahedral elements, $p$ 3 to 8 (pp. 272-273).
- Same strip with $\nu = 0.3$, $\rho = 7.86\times 10^{-9}$ Ns$^2$/mm$^4$ (7860 kg/m$^3$): 20th natural frequency 7019 Hz at zero traction, 7294 Hz at 150 MPa tension (p. 273).
- Cylindrical shell $r = 0.10$ m, $L = 0.40$ m, wall 0.001 m, $E = 2.0\times 10^{11}$ Pa, $\nu = 0.3$: $\Delta_{crit} = 2.36$ mm, $\theta_{crit} = 1.2969\times 10^{-2}$ rad (extrapolated), $F_{crit} = 1756$ kN, $M_{crit} = 15.84$ kN m, $U_{crit} = 878$ N m axial and 102.8 N m torsional (pp. 273-274).
- Shell buckling reduction factors used in practice: 1/2 to 1/4 (p. 274).
- 7075-T6 aluminium: $E = 1.05\times 10^7$ psi ($7.24\times 10^4$ MPa), $\nu = 0.30$, Ramberg-Osgood $S_{70E} = 58.5$ ksi (403.3 MPa), $n = 15.2$ (p. 277).
- DFG benchmark at $p_0 = 300$, elastic-perfectly plastic with $\sigma_{yield} = 450$, $G = 80193.8$, $K = 164206.0$ (units not stated): $W = 2044.98$, $\sigma_y^{(B)} = 517.4$, $u_y^{(D)} = 0.140327$, $u_x^{(E)} = 0.050885$, stable from 800 to 19360 degrees of freedom, matching reference [36] to four significant digits (pp. 280-281).
- Deformation theory iteration tolerance: typically 1% or less; the benchmark used 0.5% (pp. 279-280).
- Hertz spheres $r_1 = 100$ mm, $r_2 = 25$ mm, $E = 7.17\times 10^4$ MPa, $\nu = 0.3$, $P = 800$ N: computed $p_{\max} = 842$ MPa against classical 843.7 MPa; computed $r_c = 0.71$ mm against classical $a_c = 0.673$ mm; maximum von Mises stress 519 MPa at $r = 0$, $z = 99.68$ mm, below the contact area (p. 286).
- Exercise 9.8 partial answer: 50 mm square plate, 1.0 mm thick, $E = 6.96\times 10^4$ MPa, $\nu = 0.365$, $\rho = 2.71\times 10^{-9}$ Ns$^2$/mm$^4$: first natural frequency 578.6 Hz at $T_n = -50$ MPa (p. 275).

## Definitions introduced
- Virtual experimentation - exploring the influence of modelling assumptions on the quantities of interest (p. 265).
- Surface emissivity - emissive power relative to an ideal blackbody, equal to the absorption coefficient; temperature dependent (pp. 265-266).
- Lagrangian and Eulerian coordinates - material point positions in the reference state $X_i$ and deformed state $x_i$ (p. 266).
- Almansi strain tensor - strain measure from $ds^2 - dS^2 = 2e_{ij}dx_i dx_j$ in Eulerian coordinates (p. 267).
- Green strain tensor - strain measure from $ds^2 - dS^2 = 2E_{ij}dX_i dX_j$ in Lagrangian coordinates (p. 268).
- Anticlastic curvature - double curvature of the bent strip when Poisson's ratio is non-zero (p. 268, Remark 9.1).
- Stress stiffening - stiffness increase under predominantly tensile initial stress, decrease under compressive (p. 271).
- Resolvent set, spectrum, point spectrum - $\lambda$ for which (9.16) is uniquely solvable, its complement, and the eigenvalue subset (p. 271).
- Incremental theory of plasticity - relates strain increment to stress increment (p. 275).
- Deformational theory of plasticity - relates total strain tensor to stress tensor (p. 275).
- Confined plastic deformation - plastic zone surrounded by an elastic zone, strains much smaller than unity (pp. 275-276).
- Stress deviator tensor - $\tilde\sigma_{ij} = \sigma_{ij} - \frac{1}{3}\sigma_{kk}\delta_{ij}$, eq. (9.27) (p. 275).
- Equivalent stress, equivalent elastic strain - $\sqrt{J_2}$ scaled to uniaxial stress (9.28); root-mean-square of principal elastic strain differences (9.29) (p. 276).
- Consistency condition - stress states with $F > 0$ inadmissible, plastic flow only at $F = 0$ (p. 277).
- Secant modulus $E_s$ - slope of the origin-to-point line on the uniaxial curve, $0 < E_s < E$ (p. 278).
- Elastic-plastic compliance and stiffness matrices - $[C]$ relating total strain to stress and its inverse $[E_{ep}]$ (p. 279).
- Gap function - signed distance $g(s,t)$ between corresponding points on contacting surfaces; $g < 0$ not allowed (p. 281).
- Contact zone - convex subset of one contacting surface within which contact is expected (p. 281).
- Gap element - element approximating the gap function between two mapped boundary curves (p. 283).

## Figures and tables to return to
- Fig. 9.1 - notation for reference and deformed configurations, the fibre $dS \to ds$ picture behind both strain tensors (p. 267).
- Fig. 9.2 - the 200 mm strip bent into a full cylinder, the canonical small-strain large-displacement test (p. 269).
- Fig. 9.3 - 20th vibration mode with and without 150 MPa prestress, torsional against bending: prestress changes mode shape (p. 273).
- Table 9.1 - convergence of $\Delta_{crit}$ and $\theta_{crit}$ for the cylindrical shell, $p$ 5 to 8, with relative errors (p. 274).
- Fig. 9.4 - first buckling modes of the cylindrical shell under axial displacement and axial rotation (p. 274).
- Fig. 9.5 - uniaxial stress-strain curve defining $E_s$, $\bar\epsilon^{\,e}$, $\bar\epsilon^{\,p}$ and $H(\bar\epsilon^{\,p})$ (p. 276).
- Fig. 9.6 - force-displacement curve and plastic zone growth for the shear fitting at 12.0 and 15.0 kips (p. 277).
- Fig. 9.7 - DFG benchmark domain, mesh and von Mises contours at $p_0 = 450$ (p. 280).
- Table 9.2 - DFG benchmark quantities of interest against mesh refinement at $p = 8$ (p. 281).
- Fig. 9.8 - notation for the 1D two-bar contact problem (p. 281).
- Fig. 9.9 - gap element with partial penetration, showing where the Jacobian determinant changes sign (p. 284).
- Fig. 9.10 - axisymmetric Hertz model, 300-element mesh and von Mises contours near the contact area (p. 286).
- Table 9.3 - Hertz contact: computed $\bar\sigma_{\max}$, $p_{\max}$, $r_c$ against the classical solution (p. 286).
- Fig. 9.11 - contact pressure distribution with the small oscillation at the contact boundary (p. 287).

## Where to find what
| Topic | Pages |
|---|---|
| Hierarchic view of models, virtual experimentation | 265 |
| Radiation boundary condition and iteration scheme | 265-266 |
| Temperature-dependent coefficients, split-form iteration | 266 |
| Large strain: Lagrangian and Eulerian description | 266-267 |
| Almansi strain tensor | 267 |
| Green strain tensor, reduction to infinitesimal strain | 268 |
| Strip bent into a cylinder (Example 9.1) | 268-269 |
| Rigid body rotation exercises | 269 |
| Initial stress formulation, potential energy with prestress | 270 |
| Virtual work with initial stress, stress stiffening, spectrum | 271 |
| Strong form with initial stress (Remark 9.2) | 272 |
| Euler column as dimensional reduction (Example 9.2) | 272 |
| Strip buckling load factor verification (Example 9.3) | 272-273 |
| Prestress effect on frequencies and mode shapes (Example 9.4) | 273 |
| Cylindrical shell buckling, axial and torsional (Example 9.5) | 273-274 |
| Shell buckling knockdown factors (Remark 9.3) | 274 |
| Stability and stiffening exercises | 275 |
| Plasticity theories, notation, assumptions | 275-277 |
| Equivalent stress and equivalent strain definitions | 276 |
| Yield criterion, consistency condition, flow rule | 277 |
| Shear fitting by deformation theory, Ramberg-Osgood (Example 9.6) | 277 |
| Incremental theory tangent and algorithm | 277-278 |
| Deformation theory, secant modulus, $[E_{ep}]$ iteration | 278-279 |
| DFG plane strain plasticity benchmark (Example 9.7) | 279-281 |
| Contact conditions and gap function | 281 |
| Two elastic bars on springs (Example 9.8) | 281-283 |
| Gap elements in two dimensions, mapping, collocation | 283-284 |
| Partial penetration and Jacobian sign (Example 9.9) | 283-284 |
| Contact algorithm: penalty tractions, spring rates, updating | 284-285 |
| Hertz sphere contact verification (Example 9.10) | 285-287 |
| Location of critical stresses in contact (Remark 9.4) | 287 |
| Chapter summary | 287 |

## Links
[[Heat conduction]], [[Radiation heat transfer]], [[Green strain]], [[Buckling]], [[Stress stiffening]], [[Plasticity]], [[von Mises stress]], [[Ramberg-Osgood]], [[Contact mechanics]], [[Hertz contact]], [[p-version finite elements]], [[Verification and validation]]

## Flags
- Book page 288 is blank.
- Example 9.7 gives $\sigma_{yield} = 450$, $G = 80193.8$, $K = 164206.0$ and the Table 9.2 results without units (p. 280-281); treat as a consistent unit system defined by the benchmark statement.
- Suspected errata: "Az seen in Fig. 9.3" for "As seen" (p. 273); missing full stop in "were specified The investigators" (p. 280).
- Gap element collocation uses the optimal collocation points of Appendix F (p. 283); this topic continues in the appendices slice (book pages 289 onward).
- Cross-references to earlier slices: convective boundary condition eq. (2.27) (p. 266), stopping criterion eq. (5.28) (p. 268), Legendre shape functions eqs. (7.26)-(7.27) in Exercise 9.6 (p. 275), shear fitting Example 4.7 (p. 277), Exercise 7.9 in Exercise 9.9 (p. 275).
- References [81], [86] named as the further reading for non-linear formulations (p. 265); [36] is the DFG benchmark data source (p. 280).
