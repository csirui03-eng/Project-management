---
source: Finite Element Analysis: Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 223-254
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Chapter 7 treats beams, plates and shells as dimensionally reduced models of full elasticity, continuing the dimensional reduction thread the book opened in Chapter 2. Each structural theory is built by expanding the through-thickness variation of displacement in field functions times director functions, giving hierarchic families indexed by the powers retained: Timoshenko (1,0) and Bernoulli-Euler beams, Reissner-Mindlin (1,1,0) and Kirchhoff plates, Naghdi and Novozhilov-Koiter shells, all derived from minimum potential energy or virtual work. The chapter explains shear correction factors, shear locking, hard versus soft simple supports and boundary layers, proves that polynomial transverse variation is the right choice for homogeneous plates and piecewise polynomial for laminated ones, and introduces thin solid models on anisotropic polynomial spaces as an alternative to shell theory. Worked examples quantify the model form differences between Reissner-Mindlin, thin solid and fully three-dimensional solutions, and the summary states when reduced models serve and when they fail.

## Key ideas
- Beam models form a hierarchic family indexed by (m, n), the powers of y kept in the displacement expansion; the top of the hierarchy is two-dimensional elasticity (p. 223).
- Beam, plate and shell theories are semidiscretizations of the three-dimensional model, so model choice and discretization error are entangled by terminology (Remark 7.2, p. 225).
- The Timoshenko beam is the (1, 0) model; its constant cross-sectional shear strain contradicts traction-free surfaces, which the shear correction factor repairs energetically (p. 225-226).
- In the Timoshenko element the axial field u decouples from rotation and deflection when the x axis is centroidal and the surface shear tractions vanish (p. 227).
- Shear locking: as thickness d shrinks, the shear term forces the constraint beta = w', degrees of freedom collapse, and low-p convergence stalls; the Timoshenko solution tends to Bernoulli-Euler (p. 229).
- The Bernoulli-Euler energy space demands square-integrable second derivatives, so basis functions must be C1 continuous (p. 230-231).
- Bernoulli-Euler is accurate for deflections, moments and shears when the solution barely changes over distances of size d, but not for vibration with wavelengths near d; hence the need for a model hierarchy (Remark 7.4, p. 232).
- Design practice runs on sigma = -My/I capped near two thirds of yield stress; the formula fails near supports and concentrated forces (Remark 7.5, p. 232).
- Plate models carry three indices (m_x, m_y, n); analysis targets stress resultants (membrane forces, shear forces, moments) rather than stresses (p. 234).
- Bending moments transform like a Mohr circle; principal bending moments occur where M_xy = 0 (Remark 7.6, p. 236).
- Reissner-Mindlin uses a deliberately inconsistent stress-strain law (plane stress with epsilon_z and sigma_z both zero) because that choice buys asymptotic consistency with 3D elasticity as d tends to 0 (p. 237).
- Reissner-Mindlin distinguishes soft and hard simple supports; Kirchhoff admits only the hard reading (p. 238, 241).
- Boundary layer effects in plates cannot be judged a priori; mesh design and support choice must be tested by feedback from finite element solutions (Example 7.2, p. 239).
- A corner singularity in Q_x under soft simple support is an artefact of modelling assumptions and can be neglected when the quantities of interest are elsewhere (p. 239).
- Kirchhoff needs C1 continuity, which polynomial bases cannot deliver beyond C1 and vertices break; better to use C0 models (p. 241, 243).
- An infinite-strip equilibrium analysis shows the transverse displacement variation is best taken polynomial for homogeneous plates and piecewise polynomial for laminated ones (p. 243-246).
- "Shells should be viewed as fully three-dimensional solids" (Szabó and Babuška); shell assumptions fail near nozzles, attachments, stiffeners, cut-outs and abrupt curvature changes, the usual regions of strength interest (p. 247).
- Naghdi is the (1,1,0) shell analogue of Reissner-Mindlin, with a plane-stress law substituted for asymptotic consistency; Novozhilov-Koiter is the Kirchhoff analogue, C1-bound and now mainly of historical interest (p. 248-249).
- Thin solid models use Cartesian components on anisotropic trunk or product spaces; easier to implement and to join to stiffeners, but each lamina must be modelled explicitly and all components share the same field count (Remark 7.8, p. 249-250).
- The thin solid q = 1 space satisfies the hierarchy but not asymptotic consistency; Reissner-Mindlin is the reverse; q = 3 matches the 3D solution closely (p. 250-251).
- Shell eigenvalue convergence slows as thickness decreases because mode-shape regularity decreases; locking raises relative error at small thickness though asymptotic rates stay near 1.0 (p. 252-253).
- Reduced models suit stiffness, displacements, stress resultants, buckling and natural frequencies; they do not suit strength analysis near attachments, doublers and external boundaries. Differences from the 3D exact solution are model form errors (p. 254).
- As thickness shrinks, hierarchic beam, plate and shell solutions converge to Bernoulli-Euler, Kirchhoff and Novozhilov-Koiter limits lying in C1; p-convergence still occurs, entering the asymptotic range at p >= 4 (p. 254).

## Equations that matter
$$u_x = u_{x|0}(x) + u_{x|1}(x)\,y + u_{x|2}(x)\,y^2 + \dots + u_{x|m}(x)\,y^m \tag{7.1}$$
Hierarchic beam expansion; (7.2) is the analogous $u_y$ expansion to power $n$ (p. 223).

$$U_\kappa = \frac{1}{2}\int_0^\ell \left[EA(u')^2 + EI(\beta')^2 + \kappa GA(-\beta + w')^2\right] dx + \frac{1}{2}\int_0^\ell c_s w^2\, dx \tag{7.12}$$
Timoshenko strain energy with shear correction factor $\kappa$ and elastic foundation $c_s$ (p. 226).

$$F = \int_\omega \sigma_x\, dydz, \quad M = -\int_\omega \sigma_x y\, dydz, \quad V = -\int_\omega \tau_{xy}\, dydz \tag{7.14}$$
Stress resultants of the beam: axial force, bending moment, shear force (p. 226).

$$\lim_{d \to 0} \int_0^\ell (-\beta + w')^2\, dx = 0 \tag{7.20}$$
The constraint that causes shear locking as thickness vanishes (p. 229).

$$(EIw'')'' = q(x) \tag{7.22}$$
Strong form of the Bernoulli-Euler beam, recovered from the minimizer by two integrations by parts; $M = EIw''$, $V = (EIw'')'$ (p. 230).

$$\sigma = -\frac{My}{I} \tag{7.28}$$
Normal stress from the bending moment; the working formula of beam design (p. 232).

$$M_1 = \frac{M_x + M_y}{2} + R, \quad M_2 = \frac{M_x + M_y}{2} - R, \quad R = \sqrt{\left(\frac{M_x - M_y}{2}\right)^2 + M_{xy}^2} \tag{7.37}$$
Principal bending moments via the Mohr circle of moments (p. 236).

$$\lim_{d \to 0} \frac{\|\mathbf{u}_{EX}^{(3D)} - \bar{\mathbf{u}}_{EX}^{(110)}\|_E}{\|\bar{\mathbf{u}}_{EX}^{(3D)}\|_E} = 0 \tag{7.39}$$
Asymptotic consistency of the Reissner-Mindlin plate, secured by the modified stress-strain law (p. 237).

$$D \overset{\text{def}}{=} \frac{E t_z^3}{12(1 - \nu^2)} \tag{7.41}$$
Flexural rigidity of the plate, thickness $t_z$ (p. 237).

$$\kappa = \begin{cases} \dfrac{5}{6(1-\nu)} & \text{optimal energy} \\[4pt] \dfrac{20}{3(8-3\nu)} & \text{optimal displacement} \end{cases} \tag{7.45}$$
Shear correction factors for the Reissner-Mindlin plate; (7.46) covers model (1,1,1); $\kappa = 1$ for $m_x, m_y \ge 1$, $n \ge 2$ (p. 238).

$$\frac{\partial^4 w}{\partial x^4} + 2\frac{\partial^4 w}{\partial x^2 \partial y^2} + \frac{\partial^4 w}{\partial y^4} = \frac{q}{D} \tag{7.51}$$
Biharmonic equation, the strong form of the Kirchhoff plate (p. 241).

$$u_x(x, y) = u_{x|1}(x)\,y, \qquad u_y(x, y) = u_{y|0}(x) + u_{y|2}(x)\,y^2 \tag{7.75, 7.76}$$
Transverse displacement form that satisfies strip equilibrium to first order in $\beta$ for homogeneous plates; the case for polynomial director functions (p. 245).

$$u_x = u_{x|1}(x)\,y + u_{x|2}(x)F_0(y), \qquad u_y = u_{y|0}(x) + u_{y|2}(x)F_1(y) \tag{7.88, 7.89}$$
Laminated-plate counterpart: $F_0$, $F_1$ are integrals of compliance through the laminae, hence piecewise polynomial directors (p. 246).

$$u_\alpha = \sum_{i=0}^{m_\alpha} u_{\alpha|i}(\alpha, \beta)\,\phi_i(\nu) \tag{7.91}$$
Hierarchic shell expansion (shown for one component); director functions $\phi_i$ polynomial for isotropic, piecewise polynomial for laminated shells; model indexed by $(m_\alpha, m_\beta, m_n)$ (p. 247-248).

## Numbers worth citing
- Shear correction factor $\kappa = 5/6$ derived for a rectangular cross-section by strain energy matching; used in practice regardless of cross-section (p. 227).
- Example 7.1 (two-span beam, S200 x 27 steel section): $A = 3490$ mm2, $I = 24.0 \times 10^6$ mm4, $\ell = 5.00$ m, $E = 200$ GPa, $\nu = 0.3$, $q_0 = 50.0$ kN/m; self-weight 0.265 kN/m neglected; moments $M_A = -22.5$, $M_B = -33.3$, $M_D = +24.2$ kNm (at 1.00 m from C); exact with two elements at $p \ge 4$, $\kappa = 5/6$ (p. 228-229).
- Example 7.2 (aluminium plate with hole): 250 x 200 mm, hole radius 25 mm, thickness 2.5 mm, $E = 71.3$ GPa, $\nu = 0.33$, $q = -2.0$ kPa; boundary layer element width 8.5 mm chosen by minimizing potential energy at $p = 8$ (p. 238-239).
- Example 7.2 shear resultant ranges on the region of primary interest (112 elements, p-extension, product space): hard simple support $Q_x = \pm 8.717$, $Q_y = \pm 8.458$ N/mm; soft simple support $Q_x = \pm 8.723$, $Q_y = \pm 8.465$ N/mm (Table 7.1, p. 239).
- Kirchhoff exact solution, simply supported uniformly loaded equilateral triangular plate, at centre: $wD/(q_0\ell^4) = 1/1728$, $M_x/(q_0\ell^2) = (1+\nu)/72$, $M_y = M_x$, $M_{xy} = 0$ (p. 242).
- Example 7.3 (plate of Example 7.2, hard supports, 28-element mesh, $p = 8$ product space): maximum compressive stress differs 3% between Reissner-Mindlin and thin solid $q = 1$; third principal stress range $-26.61$ to $0$ MPa (Reissner-Mindlin) versus $-27.40$ to $+4.14$ MPa (thin solid $q = 1$, top surface $z = 1.25$ mm); $q = 3$ matches the Reissner-Mindlin range; relative error verified under 1% (p. 250-251).
- Example 7.4 first natural frequency, same plate, $\rho = 2780$ kg/m3, extrapolated to $p = \infty$: thin solid $q = 1$: 97.12 Hz; $q = 3$: 90.13 Hz; fully 3D: 90.07 Hz; Reissner-Mindlin: 90.94 Hz (Table 7.2, p. 251).
- Example 7.5 cylindrical shell (radius 0.1 m, length 0.4 m, ends fixed, $E = 2.0 \times 10^{11}$ Pa, $\nu = 0.3$, $\rho = 7800$ kg/m3), mode 20 frequency extrapolated to $p = \infty$, 128 elements, anisotropic product space $q = 3$: 5002.0 Hz at $t = 0.01$; 1451.9 Hz at $t = 0.001$; 391.42 Hz at $t = 0.0001$; 100.58 Hz at $t = 0.00001$ (Table 7.3, p. 252).
- Design cap: maximum $\|\sigma\|$ from (7.28) held below an allowable value of roughly two thirds of yield stress (p. 232).
- Entry into the asymptotic range of p-convergence for the C1 limit models: $p \ge 4$ (p. 254).

## Definitions introduced
- Field functions and director functions - the $x$-dependent coefficients and their through-thickness multipliers (powers of $y$, or $\phi_i(\nu)$ for shells) in the displacement expansion (p. 223, 247).
- Semidiscretization - a beam, plate or shell theory viewed as a partial discretization of the fully three-dimensional model (p. 225).
- Stress resultants - axial force, bending moment and shear force for beams; membrane forces, transverse shear forces, bending and twisting moments for plates (p. 226, 234).
- Shear correction factor $\kappa$ - multiplier on the shear term chosen so the model's shear strain energy matches that of the equilibrium shear stress distribution (p. 226-227).
- Shear locking - loss of degrees of freedom and slow low-p convergence as the constraint $\beta = w'$ is enforced by vanishing thickness (p. 229).
- Asymptotic consistency - the property that the reduced model's exact solution converges in energy norm to the 3D exact solution as thickness tends to zero (p. 237).
- Flexural rigidity $D$ - the plate bending stiffness $Et_z^3/12(1-\nu^2)$ (p. 237).
- Soft and hard simple support - $w = 0$ with $M_n = M_{nt} = 0$ (soft), versus $w = 0$, $\beta_t = 0$, $M_n = 0$ (hard); distinct only in Reissner-Mindlin (p. 238).
- Predictors of failure - functionals correlated with failure events through physical experiments, evaluated at the fibre-matrix level for laminates (Remark 7.7, p. 246).
- Thin solid models - hierarchic models in Cartesian displacement components on anisotropic trunk or product spaces, $q$ fixed, $p > q$ increased to convergence (p. 249-250).
- Model form errors - differences between data of interest from the reduced model's exact solution and from the fully three-dimensional model (p. 254).

## Figures and tables to return to
- Fig 7.1 - beam notation and sign conventions for loads, resultants and cross-section; every beam formula in the chapter refers to it (p. 224).
- Fig 7.2 - two-span beam problem and its bending moment diagram, the reference answer for Example 7.1 (p. 228).
- Fig 7.3 - the first four C1 (Hermite) shape functions on the standard beam element, with the $\ell_k/2$ scaling of $N_2$, $N_4$ (p. 231).
- Fig 7.6 - sign convention for plate stress resultants; the source of the minus signs and of $M_{yx} = -M_{xy}$ (p. 235).
- Fig 7.7 - transformation of stress resultants to the normal-tangent system, needed for boundary conditions (p. 236).
- Fig 7.8 - Example 7.2 mesh with boundary layer elements and $Q_x$ contours showing the layers (p. 238).
- Table 7.1 - hard versus soft simple support effect on $Q_x$, $Q_y$ ranges (p. 239).
- Fig 7.11 - infinite strip notation for the transverse variation analysis (p. 243).
- Fig 7.12 - third principal stress contours, Reissner-Mindlin versus thin solid $q = 1$ (p. 250).
- Table 7.2 - first natural frequency across thin solid $q = 1, 3$, fully 3D and Reissner-Mindlin models, with $p = \infty$ extrapolation (p. 251).
- Table 7.3 - mode 20 shell frequency versus thickness over four decades; the convergence slowdown at small thickness (p. 252).
- Fig 7.13 - 20th eigenfunctions at $t = 0.01$ and $t = 0.00001$ m; the regularity loss made visible (p. 253).
- Fig 7.14 - hyperboloidal shell geometry for the locking exercise (p. 253).

## Where to find what
| Topic | Pages |
|---|---|
| Hierarchic beam models, indices (m, n), field and director functions | 223 |
| Beam loads, stress resultants, elastic foundation, strain energy | 224 |
| Minimum potential energy formulation; model choice remarks | 224-225 |
| Timoshenko beam derivation (model (1,0)) | 225-226 |
| Shear correction factor for beams, kappa = 5/6 | 226-227 |
| Timoshenko element matrices, decoupling of axial field | 227-228 |
| Two-span beam worked example (Example 7.1) | 228-229 |
| Shear locking in Timoshenko beams | 229 |
| Bernoulli-Euler beam, strong form derivation | 229-230 |
| Timoshenko strong form (Exercise 7.5) | 230 |
| C1 energy space, Hermite shape functions, higher shape functions | 230-232 |
| Bernoulli-Euler element stiffness matrix, p = 5 | 232 |
| Model accuracy remarks, stress formula, design practice | 232-233 |
| Beam exercises (7.1-7.11) | 227-234 |
| Plate models, indices (m_x, m_y, n), stress resultants | 234-235 |
| Resultant transformations, principal moments, Mohr circle | 235-236 |
| Reissner-Mindlin plate: kinematics, stress-strain law, asymptotic consistency | 236-237 |
| Reissner-Mindlin strain energy, flexural rigidity, external potential | 237 |
| Plate boundary conditions, hard versus soft simple support | 238 |
| Shear correction factors for plate models | 238 |
| Plate with hole example, boundary layers, mesh design (Example 7.2) | 238-239 |
| Rhombic plate benchmark (Exercise 7.17) | 240 |
| Kirchhoff plate: formulation, energy, biharmonic strong form | 240-242 |
| Kirchhoff exact triangular plate values (Exercise 7.20) | 242 |
| Enforcement of C1 continuity, why C0 models are preferred | 243 |
| Transverse variation of displacements: strip analysis | 243-244 |
| Homogeneous plates: polynomial directors justified | 245 |
| Laminated plates: piecewise polynomial directors, failure predictors | 245-246 |
| Shells: mid-surface, curvilinear bases, hierarchic models | 247-248 |
| Naghdi shell model | 248 |
| Novozhilov-Koiter shell model | 249 |
| Thin solid models, anisotropic trunk and product spaces | 249-250 |
| Reissner-Mindlin versus thin solid stress comparison (Example 7.3) | 250-251 |
| Natural frequency model comparison (Example 7.4) | 251 |
| Cylindrical shell eigenvalue study, thickness sweep (Example 7.5) | 252-253 |
| Hyperboloidal shell locking exercise (Exercise 7.27) | 252-253 |
| Chapter summary: scope and limits of reduced models | 254 |

## Links
[[Dimensional reduction]], [[Timoshenko beam]], [[Bernoulli-Euler beam]], [[Reissner-Mindlin plate]], [[Kirchhoff plate]], [[Shear locking]], [[Shear correction factor]], [[Hierarchic models]], [[Shells]], [[Laminated plates]], [[Thin solid models]], [[Mohr circle]], [[p-version FEM]], [[Model form error]], [[Boundary layers in plates]]

## Flags
- Suspected erratum, p. 250: the Reissner-Mindlin stress range is printed as $-26.61 < \sigma_1 < 0$ where the context (third principal stress, paired with $-27.40 < \sigma_3 < 4.14$) requires $\sigma_3$. Minor typo p. 226: "sher force" for shear force.
- Notation reuse within the chapter: $\beta$ is the beam rotation (p. 225), the wavenumber $2\pi/L$ in the strip analysis (p. 243), and the rhombus angle (p. 240). Plate thickness appears as $d$ generally, $t_z$ in eq. (7.41) (p. 237), and $t$ in Table 7.3 (p. 252).
- Continues in the next slice: Remark 7.7 (p. 246) points to failure predictors defined at the fibre-matrix level of laminates, the concern of Chapter 8 (Aspects of multiscale models, from p. 255). Backward link: dimensional reduction for planar and axisymmetric models is Chapter 2 (p. 223).
- Element matrices (7.16), (7.27) reference eqs (1.66), (1.70) and Section 1.3 of the Chapter 1 slice; shape function machinery (7.26) references eq. (3.24).
- All assigned pages read; none unreadable.
