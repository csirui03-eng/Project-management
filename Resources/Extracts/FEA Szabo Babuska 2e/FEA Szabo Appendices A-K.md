---
source: Finite Element Analysis: Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 289-350
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
The eleven appendices are the book's reference annex. A collects the functional analysis vocabulary the main text leans on: normed spaces, linear and bilinear forms, Sobolev spaces of integer and fractional index, the Schwarz inequality with proof. B gives the one proof of h-convergence in the book, in the simplest 1D setting, as a template for a priori error estimates. C reports a 3D convergence experiment on the Fichera domain that supplies reference values and shows how late the asymptotic range arrives. D and E are lookup material: Legendre polynomials, the hierarchic shape functions built from them, and Gauss and Gauss-Lobatto abscissas, weights and error terms. F gives optimal interpolation points for polynomial mapping of curved boundaries. G derives corner singularity eigenvalues for 2D elasticity and tabulates them; H builds on G to give two working methods for stress intensity factors. I is a self-contained course in Bayesian data analysis worked end to end on 24S-T3 aluminium fatigue data, feeding the Chapter 6 validation examples. J is the classical rigid-body fastener group model, and K is a toolbox of solid mechanics algorithms: traction, transformation, principal stresses, von Mises stress, and rod traction formulas for boundary conditions.

## Key ideas
- Trial space, test space and the norms of linear and bilinear forms are defined axiomatically; a seminorm is a norm without positive definiteness (p. 290).
- Sobolev and energy norms are equivalent, so H1-based convergence estimates hold in the energy norm too (p. 292).
- Fractional Sobolev index measures smoothness of singular functions: $u = x^{2/3}$ lies in $H^{7/6-\epsilon}(0,1)$, and $u = r^{2/3}\cos\theta$ lies in $H^{5/3-\epsilon}(\Omega)$ (p. 292-293).
- h-convergence proof strategy: bound the interpolation error, then invoke that the FE error is no larger than the interpolant's error in energy norm (p. 295-296).
- The a priori estimate constant $C$ characterises solution smoothness and is in general not known a priori (p. 296).
- On the Fichera domain the asymptotic range starts only at high $N$: at $N = 24.5$ million, $k_h$ and $\beta_h$ still decrease monotonically (p. 299).
- In 3D, $N \propto h^{-3}$ gives $\beta_h \approx (k_h - 1)/3$; the 2D limit $\beta_p/\beta_h = 2$ is expected but unproven in 3D (p. 298-299).
- Legendre roots are the abscissas of n-point Gaussian integration (p. 302).
- Gaussian quadrature with $n$ points is exact for polynomials of degree $p$ when $n \ge (p+1)/2$; Gauss-Lobatto needs $n \ge (p+3)/2$ (p. 303, 305).
- The Lebesgue constant bounds how much worse Lagrange interpolation is than the best polynomial approximation, by the factor $(1+\lambda(T))$ (p. 307-308).
- On the standard triangle, edge interpolation points must match the 1D set so mapped surfaces stay continuous; interior points come from a mean optimality condition with three-fold symmetry (p. 309).
- Corner eigenvalues in 2D elasticity come from the Kolosov-Muskhelishvili complex potential method; unlike the Laplace case they can be complex (p. 311-312, 316).
- Symmetric (Mode I) and antisymmetric (Mode II) eigenfunctions have separate transcendental eigenvalue equations (p. 313).
- No real symmetric roots exist below the reentrant angle $\alpha_A = 146.31°$; no real antisymmetric roots below $\alpha_B = 159.11°$ (p. 314-315).
- The rate of convergence depends only on the real part of a complex eigenvalue (p. 316).
- Free-free corner eigenvalues are independent of Poisson's ratio; fixed-free and fixed-fixed values are tabulated for plane stress at $\nu = 0.3$ (p. 317).
- At a crack tip ($\alpha = 2\pi$) the eigenvalues are $\lambda_i = i/2$; the first term gives $K_I$, the second is the constant T-stress $\sigma_x = 4a_2$ (p. 319).
- The contour integral method extracts $K_I$ from a path-independent integral pairing the FE solution with an extraction function built on the negative eigenvalue $\lambda = -1/2$ (p. 320-321).
- The energy release rate follows from crack closure work; Mode I and Mode II solutions are energy orthogonal so their contributions add (p. 322-323).
- The stiffness derivative method gets $\mathcal{G}$ from finite differences of the stiffness matrix, recomputed only for elements with a vertex at the crack tip; $\partial r/\partial a$ is usually negligible (p. 324).
- Validation and ranking of models rests on Bayesian probability; data analysis reduces to the product rule, Bayes' theorem and marginalization (p. 325-326).
- "Without data, you're just another person with an opinion." (W. E. Deming, quoted p. 325).
- A statistical model states what is expected to happen; the test data tell what did happen (p. 329).
- Runouts (right-censored data) enter the likelihood through the survival term $1-\Phi$ (p. 330).
- The random fatigue limit model treats the fatigue limit as a normally distributed random variable and beats the bilinear and fixed fatigue limit models by Bayes factors near $10^{11}$ (p. 332-335).
- The RFL model is an unreliable predictor of $n$ near the mean fatigue limit: a small change in $\sigma_{eq}$ there produces a large change in predicted $n$ (p. 335).
- Confidence intervals come from the profile likelihood via Wilks' theorem (p. 336).
- The fastener model needs no discretisation, so its prediction errors are entirely model form errors (p. 339).
- Rod traction formulas (K.28), (K.30), (K.32) are exact only for straight rods of constant cross-section under special loading, but their tractions equilibrate the applied resultants, so the error decays by Saint-Venant's principle (p. 350).

## Equations that matter
$$C_1\|u\|_{H^1(\Omega)} \le \|u\|_{E(\Omega)} \le C_2\|u\|_{H^1(\Omega)} \tag{A.11}$$
Equivalence of Sobolev and energy norms; lets H1 convergence estimates carry over (p. 292).

$$\|e\|_{E(\Omega)} \overset{\text{def}}{=} \sqrt{U(e)} \le kCh \tag{B.10}$$
The a priori h-convergence estimate, 1D, $p=1$, exact solution with bounded second derivative (p. 296).

$$(n+1)P_{n+1}(\xi) = (2n+1)\xi P_n(\xi) - nP_{n-1}(\xi) \tag{D.11}$$
Recursion generating all Legendre polynomials (p. 301).

$$\int_{-1}^{+1} P_i P_j \, d\xi = \frac{2}{2i+1}\,\delta_{ij} \tag{D.13}$$
Orthogonality; the property that makes the hierarchic basis nearly diagonal (p. 301).

$$N_i(\xi) = \frac{1}{\sqrt{2(2i-3)}}\left(P_{i-1}(\xi) - P_{i-3}(\xi)\right) \tag{D.19}$$
General hierarchic shape function from Legendre polynomials (p. 302).

$$w_i = \frac{2}{(1-x_i^2)[P_n'(x_i)]^2} \tag{E.2}$$
Gaussian quadrature weights at the zeros of $P_n$ (p. 303).

$$\kappa \overset{\text{def}}{=} \begin{cases} \dfrac{3-\nu}{1+\nu} & \text{plane stress} \\ 3-4\nu & \text{plane strain} \end{cases} \tag{G.11}$$
The Kolosov constant used throughout G and H (p. 312).

$$\sin\lambda\alpha + \lambda\sin\alpha = 0, \quad \lambda \ne 0, \pm 1 \tag{G.18}$$
Eigenvalue equation for symmetric (Mode I) corner eigenfunctions, stress-free edges (p. 313).

$$\sin\lambda\alpha - \lambda\sin\alpha = 0, \quad \lambda \ne 0, \pm 1 \tag{G.19}$$
Eigenvalue equation for antisymmetric (Mode II) corner eigenfunctions (p. 313).

$$K_I = \frac{\sqrt{2\pi}\,G}{F(\kappa)}\, I_\Gamma(\mathbf{u}, \mathbf{w}/C) \tag{H.19}$$
Mode I stress intensity factor from the path-independent contour integral; $F(\kappa)$ tabulated in Table H.1 (p. 321).

$$(K_I^2 + K_{II}^2) = \begin{cases} \dfrac{E\mathcal{G}}{t_z} & \text{plane stress} \\ \dfrac{E\mathcal{G}}{(1-\nu^2)t_z} & \text{plane strain} \end{cases} \tag{H.31}$$
Stress intensity factors from the energy release rate under combined loading (p. 323).

$$\mathcal{G} = -\frac{1}{2}x^T\frac{\partial K}{\partial a}x + x^T\frac{\partial r}{\partial a} \tag{H.32}$$
Stiffness derivative method; the derivatives are approximated by central differences in $a$ (p. 324).

$$\Pr(M \mid D) = \frac{\Pr(D \mid M)\Pr(M)}{\Pr(D)} \tag{I.3}$$
Bayes' theorem in model-and-data form: posterior from likelihood, prior and evidence (p. 326).

$$\frac{\Pr(M_i \mid D)}{\Pr(M_j \mid D)} = \exp\!\left(LL(D \mid \theta_i) - LL(D \mid \theta_j)\right) \tag{I.25}$$
Bayes factor from log likelihood difference, priors taken equal; the model ranking tool (p. 335).

$$-2\ln R(\theta_k) \le \chi^2_{1;1-\alpha} \tag{I.27}$$
Confidence interval from the profile likelihood by Wilks' theorem (p. 336).

$$f_x^{(j)} = \frac{\kappa_j}{\sum \kappa_k}F_x - \frac{\kappa_j y_j}{\sum \kappa_k(x_k^2+y_k^2)}M, \qquad f_y^{(j)} = \frac{\kappa_j}{\sum \kappa_k}F_y + \frac{\kappa_j x_j}{\sum \kappa_k(x_k^2+y_k^2)}M \tag{J.12, J.13}$$
Fastener forces in a rigid plate on elastic springs; coordinates measured from the centre of rotation (p. 338).

$$[\sigma'] = [g][\sigma][g]^T \tag{K.9}$$
Stress transformation under coordinate rotation, $g_{ij} = \cos\alpha_{ij}$ (p. 344).

$$\bar\sigma = \sqrt{\frac{(\sigma_1-\sigma_2)^2 + (\sigma_2-\sigma_3)^2 + (\sigma_3-\sigma_1)^2}{2}} \tag{K.16}$$
Von Mises stress; equals $\sigma_{yld}$ at the onset of yielding (p. 345).

$$T_x = \frac{F_x}{A} - \frac{M_zI_y + I_{yz}M_y}{I_yI_z - I_{yz}^2}\,y + \frac{M_yI_z + I_{yz}M_z}{I_yI_z - I_{yz}^2}\,z \tag{K.28}$$
Normal traction on a rod cross-section from axial force and bending moments, centroidal axes (p. 349).

$$\tau_\theta = \frac{M_x r}{J} \tag{K.31}$$
Torsion shear traction for a straight circular rod, $J = r_w^4\pi/2$ (p. 350).

## Numbers worth citing
- Fichera domain reference potential energy, elasticity, $E = 1.0\times10^3$, $\nu = 0.3$: extrapolated $\pi = -7.1045906487\times10^{2}$ (p-extension, trunk space, geometric mesh $q = 1/7$, $m = 8$, $M(\Delta) = 3584$) (p. 298); Table C.2 quotes $-7.10459065\times10^{2}$ as reference (p. 299).
- h-extension on the Fichera domain, uniform mesh, $p = 2$ trunk space, at $N = 24{,}503{,}292$: $k_h = 1.5514$, $\beta_h = 0.1847$, relative error 1.4342 percent, both still decreasing (p. 299).
- Round-off perturbations affect not fewer than the twelfth digit of the computed potential energies (direct solver) (p. 299).
- Lebesgue constant of the optimal 1D nodal set for $p = 5$: $\lambda(T) = 1.6722$ (p. 308).
- Symmetric corner roots: none real for $\alpha < \alpha_A = 2.553591$ rad (146.31°); antisymmetric: none real for $\alpha < \alpha_B = 2.777068$ rad (159.11°); $\alpha = \tan\alpha$ root at 4.493409 rad (257.45°) (p. 314-315).
- L-shaped domain ($\alpha = 3\pi/2$, stress-free edges): $\lambda_1 = 0.544483737$, $Q_1 = 0.543075579$ (p. 313, 315).
- Crack geometry ($\alpha = 360°$): lowest eigenvalues 0.5 for free-free and fixed-fixed, 0.25 for fixed-free (plane stress, $\nu = 0.3$ where $\nu$ enters) (p. 316).
- $F(\kappa)$ for the $K_I$ extraction function: $-4\pi$ at $\nu = 0$; at $\nu = 0.3$: $-9.66644$ plane stress, $-8.79646$ plane strain (p. 321).
- 24S-T3 (2024-T3) aluminium, average static properties: modulus in compression 10,650 ksi grain (L), 10,450 ksi cross (T); tensile yield (0.2 percent offset) 54.0 ksi (L), 50.0 ksi (T); ultimate tension 73.0 ksi (L), 71.0 ksi (T) (p. 327).
- Fatigue tests at 1100 cycles per minute (18.3 Hz); load precision about $\pm 3$ percent tension-tension, $\pm 5$ percent tension-compression; specimens electropolished (p. 326).
- Actual stress concentration factors of the ten specimen groups span 1.00 to 5.83; errors in the highly stressed area $A$ verified under 1 percent (p. 327-328).
- Bilinear S-N model: $S_0 = 31.305$ ksi, $\log_{10}N_0 = 5.26352$, $m_1 = 0.0596$, $m_2 = 0.1779$ ksi$^{-1}$, $s = 0.4583$, $LL = -601.931$ (p. 331).
- Fatigue limit model: $A_3 = 17.856$ ksi, $LL = -602.112$ (p. 331).
- Random fatigue limit model: $\mu_f = 1.3438$, $s_f = 0.0488$, $s = 0.1255$, $LL = -576.734$ (p. 333); mean fatigue limit $10^{\mu_f} = 22.07$ ksi (p. 334); 95 percent confidence interval for $\mu_f$: (1.241, 1.388) (p. 336).
- Bayes factors: $BF_{31} \approx 8.8\times10^{10}$, $BF_{32} \approx 1.1\times10^{11}$ in favour of the RFL model (p. 335).
- Nine runouts recorded in the S-N data set of 53 points; four predicted by the RFL model (p. 328, 333).
- Conversions used: 1 inch = 25.40 mm, 1 psi = 6.895 kPa (p. 327), 1 ksi = 6.895 MPa (p. 329).

## Definitions introduced
- Supremum, infimum, essential supremum - bounds replacing max and min; ess sup excludes sets of measure zero (p. 289).
- Seminorm - has the norm's properties except positive definiteness (p. 290).
- Linear form, bilinear form, and their norms - the smallest bounding constants $C$ (p. 290).
- Trial space, test space - the spaces $X$ and $Y$ of a bilinear form $B(u,v)$ (p. 290).
- Sobolev space $H^1(\Omega)$ - functions square integrable together with first derivatives (p. 291).
- Fractional Sobolev index $k = m + \mu$ - characterises smoothness of singular solutions; governs a priori convergence rates (p. 292).
- Lebesgue constant $\lambda(T)$ - maximum of the summed absolute Lagrange shape functions on a nodal set (p. 307, spelled "Lebesque" in the book).
- Optimal nodal set $T_1^p$, mean optimal set $T_2^p$ - point sets minimising $\lambda(T)$, respectively the integral criterion $\eta^2$ (p. 308).
- Mode I, Mode II eigenfunctions - symmetric, respectively antisymmetric corner eigenfunctions (p. 313).
- T-stress - the constant stress $\sigma_x = 4a_2$ from the second term of the crack tip expansion (p. 319).
- Energy release rate $\mathcal{G} = -\partial\Pi/\partial a$ (p. 321).
- Griffith's surface energy - the energy expended in crack growth (p. 322).
- Posterior probability, likelihood function, prior probability, marginal likelihood (evidence) - the four terms of Bayes' theorem in model form (p. 326).
- Runout - test stopped before failure; statistically, right-censored data (p. 328).
- Statistical model - a precise statement of the assumed distribution of $N$ given $\sigma_{eq}$ (p. 329).
- Fatigue limit, fatigue strength - stress amplitude at full reversal causing no failure at any $n$; $\sigma_{eq}$ read from the S-N curve at fixed $n$ (usually $5\times10^8$ cycles) (p. 331).
- Bayes factor $BF_{ij}$ - ratio of the probabilities of the data under two models (p. 335).
- Profile likelihood - likelihood maximised over all parameters but one (p. 336).
- Traction (stress) vector $T_i = \sigma_{ij}n_j$ (p. 341-342).
- Principal stresses, stress invariants $I_1, I_2, I_3$ - eigenvalues of the stress tensor and the rotation-invariant coefficients of its characteristic equation (p. 344).
- Von Mises yield criterion (distortion energy criterion) - yielding when $J_2$ of the stress deviator reaches $\sigma_{yld}^2/3$ (p. 345).

## Figures and tables to return to
- Table C.1 - p-convergence on the Fichera domain; source of the extrapolated reference energy (p. 298).
- Table C.2 - h-convergence to $N = 24.5$ million; evidence for late entry into the asymptotic range (p. 299).
- Fig. C.1 - convergence paths of $\beta$ for h- and p-extensions, trunk and product spaces (p. 298).
- Fig. D.1 - the first eight Legendre-based shape functions (p. 302).
- Table E.1 - Gaussian abscissas and weights to $n = 8$, 15 digits (p. 304).
- Table E.2 - Gauss-Lobatto abscissas and weights to $n = 8$ (p. 305).
- Table F.1 - optimal and mean optimal 1D interpolation sets, $p = 3$ to 8 (p. 309).
- Table F.2 - triangular coordinates of interior interpolation points, $p = 5$ (p. 310).
- Fig. G.1 - $Q(\lambda\alpha)$ plot from which the existence of real corner eigenvalues is read (p. 314).
- Table G.1 - lowest positive $\Re(\lambda)$ for free-free, fixed-free, fixed-fixed edges, $\alpha = 45°$ to 360°; the singularity strength lookup for reentrant corners (p. 316).
- Table H.1 - $F(\kappa)$ values for the contour integral extraction of $K_I$ (p. 321).
- Table I.1 - static properties of 24S-T3 aluminium, grain and cross directions (p. 327).
- Table I.2 - the ten fatigue specimen groups with $(K_t)_{act}$, highly stressed area and counts (p. 328).
- Tables I.3, I.4, I.5 - fitted parameters and log likelihoods of the bilinear, fatigue limit and RFL models (p. 331, 333).
- Fig. I.6 - empirical CDF of the S-N data against the RFL median and quantiles (p. 334).
- Fig. I.7 - marginal CDFs of the RFL model at several stress levels; shows the non-zero no-failure probability (p. 334).
- Fig. I.8 - profile likelihood and confidence interval for $\mu_f$ (p. 336).
- Fig. J.1 - fastener group notation (p. 338).
- Fig. K.5 - cross-section notation for the rod traction formulas (p. 348).

## Where to find what
| Topic | Pages |
|---|---|
| A: analytic function, Euclidean norm, sup/inf, Dirac delta | 289 |
| A: normed linear spaces, linear and bilinear forms, trial and test spaces | 290 |
| A: convergence in a normed space, $C^k$ and $L^p$ spaces | 291 |
| A: Sobolev space $H^1$, norm, seminorm, energy norm equivalence | 291-292 |
| A: fractional index Sobolev spaces, singular function examples | 292-293 |
| A: Schwarz inequality for integrals, with proof | 293 |
| B: h-convergence proof, 1D, $p=1$; a priori estimate | 295-296 |
| C: Fichera domain problem statement, STRIPE software | 297 |
| C: p-convergence reference solution | 298 |
| C: h-convergence data, $\beta_h \approx (k_h-1)/3$, asymptotic range remark | 298-299 |
| D: Legendre polynomials, recursion, orthogonality, Gauss abscissas | 301-302 |
| D: hierarchic shape functions $N_6$ to $N_9$ and general $N_i$ | 302 |
| E: Gaussian quadrature, weights, error term, exactness rule | 303-304 |
| E: quadrature on quadrilateral and hexahedral elements | 304 |
| E: Gauss-Lobatto quadrature, weights, error term | 304-305 |
| F: Lebesgue constant, interpolation error bound | 307-308 |
| F: optimal and mean optimal nodal sets | 308-309 |
| F: interpolation points on quadrilateral and triangle surfaces | 309-310 |
| G: Airy stress function, complex potentials, Kolosov-Muskhelishvili | 311-312 |
| G: stress-free edge eigenvalue equations | 312-313 |
| G: symmetric eigenvalues, special angles, complex roots | 313-315 |
| G: antisymmetric eigenvalues | 315 |
| G: L-shaped domain singular stress and displacement fields | 315-316 |
| G: complex eigenvalues, convergence rate remark | 316 |
| G: corner eigenvalue table, three boundary condition types | 316-317 |
| H: crack tip asymptotic expansion, T-stress | 319-320 |
| H: contour integral method for $K_I$, extraction function, $F(\kappa)$ | 320-321 |
| H: energy release rate, crack closure, Mode I and II, combined loading | 321-323 |
| H: stiffness derivative method | 323-324 |
| I: product rule, Bayes' theorem, marginalization | 325-326 |
| I: 24S-T3 fatigue test data and specimen geometry | 326-328 |
| I: bilinear, fatigue limit and random fatigue limit models, likelihood with runouts | 328-334 |
| I: model ranking by Bayes factor | 335 |
| I: confidence intervals from profile likelihood | 335-336 |
| J: fastener force model, centre of rotation, force formulas | 337-339 |
| K: traction vector, Cauchy tetrahedron | 341-342 |
| K: transformation of vectors and stresses | 342-344 |
| K: principal stresses and invariants | 344 |
| K: von Mises stress, yield in pure shear | 344-345 |
| K: statically equivalent forces and moments, coil spring example | 345-348 |
| K: rod traction formulas: normal, shear, torsion | 348-350 |

## Links
[[Sobolev spaces]], [[Energy norm]], [[A priori error estimates]], [[p-version FEM]], [[Legendre polynomials]], [[Gaussian quadrature]], [[Isoparametric mapping]], [[Corner singularities]], [[Stress intensity factors]], [[Fracture mechanics]], [[Energy release rate]], [[Bayesian inference]], [[Maximum likelihood]], [[S-N curves]], [[Fatigue]], [[Model validation]], [[Von Mises stress]], [[Saint-Venant's principle]]

## Flags
- Blank separator pages at 294, 300, 306, 318 and 340; no content lost.
- The book consistently spells the Lebesgue constant "Lebesque" in Appendix F (p. 307-309); suspected typo, retained as printed nowhere else in this note.
- Cross-chapter dependencies for the indexer: C uses eqs (1.91), (1.92), (1.102) and (4.35) from Chapters 1 and 4; F uses eqs (1.50), (1.60), (3.46), (3.47); G mirrors Section 4.2.2 and reuses Fig. 4.1; H rests on G, Section 4.2.4 and eq. (4.42); I supplies the data and models behind the Chapter 6 examples; K Example K.2 refers to Fig. 5.13 (Chapter 5); B cites Theorem 1.4.
- Page 335 cites "tables I3, I4 and I5" without dots; trivial typesetting slip.
- Bibliography begins at book page 351, outside this slice; not read.
