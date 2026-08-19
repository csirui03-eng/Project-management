---
source: "Finite Element Analysis: Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021"
pages: 1-50
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Chapter 1 builds the entire finite element method in one spatial dimension so that every later chapter can generalise it. Starting from a second order ODE with no physical interpretation attached, it derives the generalised (weak) formulation, proves uniqueness and the minimum potential energy principle, then constructs approximate solutions: shape functions (Lagrange and hierarchic Legendre), mesh families, element stiffness, Gram and load matrices, assembly, condensation, and Dirichlet enforcement. It then treats what happens after the solve: direct and extraction-based computation of quantities of interest, a priori convergence rates tied to solution regularity, a posteriori error estimation by extrapolation of potential energy, and discretisation choice for smooth, boundary layer and singular solutions. It closes with eigenvalue problems via the Rayleigh quotient, and with other formulations (mixed method, Nitsche's method) unified under the Babuška-Brezzi stability condition. The framing argument of the book is set here: separating model formulation from numerical solution is what makes error control, and hence verification, possible.

## Key ideas
- Simulation is representing one system by the functioning of another; Prandtl's 1903 membrane analogy for shear stress in twisted bars is the opening example (p. 1).
- Design certification needs a bound on the relative numerical error $\tau$; without it, numerical error penalises design by forcing lower allowables (p. 2).
- Finite element modelling (element libraries, intuition) is distinguished from numerical simulation; the former is "a practice of art, guided by intuition and experience" (Szabó and Babuška, p. 2).
- Separating model formulation from numerical solution splits error into model form errors and discretisation errors; early FE literature made no such distinction (p. 3).
- The approximation process is independent of why the mathematical problem was formulated; legacy codes mix the two (p. 3).
- An approximation to $u$ can be found by minimising a quadratic integral without knowing $u$ (p. 4, 6).
- The weak form requires only finite energy, a weaker condition than the strong form; when the strong solution exists the two coincide for smooth data (p. 6, 10).
- The error $e = u - u_n$ depends on the span of the basis, not on the choice of basis functions (p. 5, 6).
- Essential (Dirichlet) conditions are enforced by restricting the trial space; natural (Neumann, Robin) conditions enter through the linear form and cannot be enforced by restriction (pp. 8-10).
- The weak solution exists and is unique in the energy space even for discontinuous $\kappa$, $c$, $f$ (Theorem 1.1, pp. 9-10).
- The weak solution minimises the potential energy; strain energy is always positive, potential energy can have either sign (Theorem 1.2, Remark 1.3, pp. 11-12).
- The finite element solution is the projection of the exact solution: Galerkin orthogonality and best approximation in energy norm (Theorems 1.3, 1.4, p. 13).
- Hierarchic Legendre shape functions make the set for degree $p$ a subset of that for $p+1$, and give near-diagonal element matrices for constant coefficients (pp. 15, 18-19).
- Four mesh families: uniform, quasiuniform, geometric, radical; the choice follows from a priori knowledge of solution regularity (p. 16).
- h-, p- and hp-extension name the three ways of increasing degrees of freedom; the separate names reflect history, not theory (p. 17, Remark 1.4).
- Condensation eliminates internal basis function coefficients at element level before assembly (p. 24).
- QoIs can be computed directly from the solution or indirectly by extraction functions; extraction can beat direct computation by orders of magnitude in accuracy (pp. 27-29).
- Nodal forces are in equilibrium independently of the polynomial degree, so equilibrium of nodal forces says nothing about solution quality (p. 30).
- Regularity is measured by $\alpha$ in $u_{EX} = x^\alpha \varphi(x)$; the smaller $\alpha - 1/2$, the harder the approximation; this form models singularities at vertices of polygonal and polyhedral domains (p. 30).
- The rate of p-convergence is twice the rate of h-convergence when the singular point is a nodal point (p. 31, confirmed numerically in Examples 1.11, 1.12, p. 36).
- A posteriori error estimation: extrapolate potential energy from three hierarchic solutions; tested widely but not guaranteed for all conceivable problems (p. 33).
- Extraction error is bounded by a product of two energy norms, which is why extracted QoIs converge faster than the energy norm error; with a Green function as extraction function the error is zero (pp. 37-38).
- Boundary layer problems: the optimal boundary element size is proportional to $p\epsilon$; an analytic solution can still demand unrealistically high $p$ on a bad mesh (pp. 38-39).
- For singular solutions the maximum element error sits in the element containing the singularity, for every $\alpha$ tested (p. 41, Table 1.4).
- In 1D the hierarchic basis is energy-orthogonal so round-off is not a concern; this does not carry to 2D and 3D, and integration errors can be damaging (p. 42).
- Computed eigenvalues converge monotonically from above because eigenfunctions minimise the Rayleigh quotient; only the lower part of the computed spectrum is accurate (pp. 44-46).
- Every finite element method must satisfy the Babuška-Brezzi condition or it will fail for some input data while appearing to work for others (p. 47, Remark 1.15).
- In the mixed method the convergence of the pair $(u_{FE}, F_{FE})$ hinges on the choice of the space $V(I)$; one natural-looking choice fails the BB condition (p. 48).
- Nitsche's method treats essential boundary conditions as natural ones and stabilises the penalty formulation so it works for the full range including $\epsilon = 0$ (pp. 48-49).

## Equations that matter
$$-(\kappa u')' + cu = f \quad \text{on } \bar I = [0 \le x \le \ell] \tag{1.5}$$
The model problem's strong form; the whole chapter hangs off it (p. 3).

$$B(u,v) \stackrel{\text{def}}{=} \int_0^\ell (\kappa u'v' + cuv)\,dx \tag{1.19}$$
The bilinear form of the model problem; $F(v)$ in eq. (1.20) carries load and natural boundary terms (p. 7).

$$\lVert u \rVert_{E(I)} \stackrel{\text{def}}{=} \sqrt{\tfrac{1}{2} B(u,u)} \tag{1.22}$$
Energy norm, the yardstick for every error statement in the book (p. 7).

$$\pi(u) \stackrel{\text{def}}{=} \tfrac{1}{2} B(u,u) - F(u) \tag{1.36}$$
Potential energy; the weak solution is its unique minimiser on the trial space (p. 11).

$$B(u - u_n, v) = 0 \quad \text{for all } v \in S^0(I) \tag{1.47}$$
Galerkin orthogonality: the error is energy-orthogonal to the test space (p. 13).

$$\lVert u_{EX} - u_n \rVert_{E(I)} = \min_{u \in \tilde S} \lVert u_{EX} - u \rVert_{E(I)} \tag{1.48}$$
The finite element solution is the best approximation in energy norm (p. 13).

$$N_i(\xi) = \prod_{\substack{k=1 \\ k \ne i}}^{p+1} \frac{\xi - \xi_k}{\xi_i - \xi_k}, \quad i = 1, \ldots, p+1 \tag{1.50}$$
Lagrange shape functions: unity at the own node, zero at the others (p. 14).

$$N_i(\xi) = \sqrt{\frac{2i-3}{2}} \int_{-1}^{\xi} P_{i-2}(t)\,dt, \quad i = 3, 4, \ldots, p+1 \tag{1.53}$$
Hierarchic Legendre shape functions; derivative-orthogonal, vanish at the element ends (p. 14).

$$S = S(I, \Delta, \mathbf{p}, \mathbf{Q}) = \{u \mid u \in E(I),\ u(Q_k(\xi)) \in S^{p_k}(I_{st}),\ k = 1, \ldots, M(\Delta)\} \tag{1.61}$$
Definition of a finite element space by mesh, degree distribution and mapping (p. 17).

$$k_{ij}^{(k)} = \frac{2}{\ell_k} \int_{-1}^{+1} \kappa(Q_k(\xi)) \frac{dN_i}{d\xi} \frac{dN_j}{d\xi}\,d\xi \tag{1.64}$$
Element stiffness matrix on the standard element (p. 18).

$$m_{ij}^{(k)} = \frac{\ell_k}{2} \int_{-1}^{1} c(Q_k(\xi))\, N_i N_j\,d\xi \tag{1.68}$$
Element-level Gram (mass) matrix (p. 19).

$$r_i^{(k)} \stackrel{\text{def}}{=} \frac{\ell_k}{2} \int_{-1}^{+1} f(Q_k(\xi))\, N_i(\xi)\,d\xi \tag{1.75}$$
Element-level load vector (p. 21).

$$(e_r)_E \le \begin{cases} C(k) \dfrac{h^{k-1}}{p^{k-1}} \lVert u_{EX} \rVert_{H^k(\Omega)} & \text{for } k-1 \le p \\[2ex] C(k) \dfrac{h^{p}}{p^{k-1}} \lVert u_{EX} \rVert_{H^{p+1}(\Omega)} & \text{for } k-1 > p \end{cases} \tag{1.91}$$
The a priori bound on relative error in energy norm for $u_{EX} \in H^k(\Omega)$, quasiuniform meshes; holds in one, two and three dimensions (p. 31).

$$(e_r)_E \le \frac{C}{N^\beta} \tag{1.92}$$
Algebraic convergence in degrees of freedom $N$; $\beta$ is the algebraic rate, doubled for the p-version when the singularity is a nodal point (p. 31).

$$(e_r)_E \le \frac{C}{\exp(\gamma N^\theta)} \tag{1.93}$$
Exponential convergence when the exact solution is analytic (p. 32).

$$\lVert e \rVert_E^2 = \lVert u_{EX} - u_{FE} \rVert^2_{E(I)} = \pi(u_{FE}) - \pi(u_{EX}) \tag{1.94}$$
Theorem 1.5: error in energy norm from potential energies; the foundation of the extrapolation estimator (p. 32).

$$\frac{\pi_i - \pi_\infty}{\pi_{i-1} - \pi_\infty} \approx \left(\frac{\pi_{i-1} - \pi_\infty}{\pi_{i-2} - \pi_\infty}\right)^Q \tag{1.99}$$
A posteriori estimator: solved for $\pi_\infty$ from three solutions in a hierarchic sequence; relative error then from eq. (1.100) (p. 33).

$$\Phi(u_{FE}) = F(w) - B(u_{FE}, w) \tag{1.109}$$
Extraction of a quantity of interest via an extraction function $w$ (p. 36).

$$|\Phi(u_{EX}) - \Phi(u_{FE})| \le 2 \lVert u_{EX} - u_{FE} \rVert_{E(I)} \lVert z_{EX} - z_{FE} \rVert_{E(I)} \tag{1.117}$$
Why extracted QoIs superconverge: the error is a product of two small norms (p. 37).

$$B(U, v) - \omega^2 D(U, v) = 0 \quad \text{for all } v \in E^0(I) \tag{1.140}$$
The generalised eigenvalue problem; eigenpairs $(\omega_i, U_i)$, orthogonal eigenfunctions, complete in $E^0(I)$ (p. 43).

$$R(u) = \frac{B(u,u)}{D(u,u)} \tag{1.144}$$
Rayleigh quotient; the $k$th eigenvalue is its minimum on the space orthogonal to the first $k-1$ eigenfunctions (p. 44).

$$|B(u,v)| \ge C\, \lVert u \rVert_X \lVert v \rVert_Y \tag{1.155}$$
The Babuška-Brezzi condition, necessary and sufficient for stability of any finite element method (p. 47).

## Numbers worth citing
- Digits lost in solving a linear system: roughly $\log_{10} C$, with $C$ the condition number of the symmetric positive definite coefficient matrix (p. 13).
- Optimal grading factor for geometric meshes at a singularity: $q = (\sqrt{2}-1)^2 \approx 0.17$, independent of $\alpha$; polynomial degrees should rise at a rate of about 0.4 across the layers (p. 17).
- Direct versus extracted derivative, Example 1.8 (five elements, $p=1$, exact $u'_{EX}(1) = 3.5978$): direct 2.9028 (19.32 % error), indirect 3.6254 (0.77 % error) (pp. 27-28).
- Example 1.9 (one element, discontinuity inside): direct computation of $u'(0)$ has not converged to 0.75 by $p = 100$; extraction with the Green function $v = 1-x$ is exact for all $p$; extraction with $v = 1-x^2$ gives 0.5156 (31.25 % error) frozen for all $p \ge 2$ (pp. 28-29).
- Rates for the model singular solution $u_{EX} = x^\alpha(\ell - x)$: $\beta = \alpha - 1/2$ for the h-version on uniform meshes, $\beta = 2\alpha - 1$ for the p-version on a fixed mesh (pp. 34, 36).
- Extrapolation estimator accuracy, Example 1.10 ($M = 10$, $\alpha = 0.8$, $p = 2$): estimated relative error 0.0522 versus exact 0.0522, agreement to three digits (p. 36).
- Exponential convergence exponent: $\theta \ge 1/2$ in 1D, $\ge 1/3$ in 2D, $\ge 1/5$ in 3D (p. 32).
- Element error distribution, uniform mesh $M = 5$, $p = 2$, $\alpha = 0.75$: 60.39 % in the first (singular) element against 22.37 % total; at $\alpha = 1$ the error is exactly zero because the solution lies in the FE space (pp. 41-42, Tables 1.4, 1.5).
- Fraction of computed eigenvalues that are accurate: somewhat more than 20 % for the h-version at $p = 2$ (with a jump artefact at $n/N = 0.5$), about 40 % for the p-version on a 5-element mesh, error there independent of $p$ (pp. 44-45).
- 24th eigenvalue of the piecewise constant $\mu$ problem (Example 1.16): converges to 98.312 by $p = 15$ under uniform p-increase (p. 46, Table 1.6).
- Nitsche's stabilised method, one element, $p = 3$, $\hat u_\ell = 0.25$: computed $u(\ell)$ correct to 12 zeros as $\gamma$ spans $10^{-3}$ to $10^{-15}$ (p. 50, Table 1.7).

## Definitions introduced
- Simulation - imitative representation of one system by the functioning of another (p. 1).
- Quantities of interest (QoI) - the engineering outputs extracted from the approximate solution (p. 2).
- Discretisation - the process by which approximating functions are defined (p. 2, footnote 3).
- Model form error / discretisation error - error of formulating the model versus error of its numerical solution (p. 3).
- Forcing function - the right hand side $f$ of the differential equation (p. 3).
- Basis functions and span - fixed functions whose linear combinations form the trial set; the approximation depends on the span only (pp. 3, 5).
- Strong form / generalised (weak) form - the differential equation versus its integral statement over a larger admissible set (p. 6).
- Bilinear form, linear form - the two sides of the generalised formulation (p. 7).
- Energy norm - $\sqrt{B(u,u)/2}$ (p. 7).
- Energy space $E(I)$ - all functions of finite energy norm; infinite-dimensional (p. 7).
- Trial space $\tilde E(I)$, test space $E^0(I)$ - functions satisfying, respectively zeroing, the essential boundary conditions (pp. 7-8).
- Essential (Dirichlet), Neumann, Robin boundary conditions - prescribed $u$; prescribed $\kappa u'$; prescribed $\kappa u'$ as a spring-like combination (pp. 8-9).
- Natural boundary conditions - Neumann and Robin conditions, enforced through the linear form, not by restriction (p. 9).
- Generalised (weak) solution $u_{EX}$ - the unique solution of the generalised formulation (p. 10).
- Potential energy $\pi(u)$ - quadratic functional minimised by the weak solution (p. 11).
- Galerkin orthogonality - $B(e, v) = 0$ for all test functions (p. 13).
- Condition number - largest over smallest eigenvalue of the coefficient matrix (p. 13).
- Shape functions - basis functions of the standard polynomial space; Lagrange or hierarchic (pp. 13-14).
- Hierarchic shape functions - degree $p$ set contained in the degree $p+1$ set (p. 15).
- Finite element mesh $\Delta$, node points - partition of the domain into $M(\Delta)$ non-overlapping elements (p. 16).
- Uniform, quasiuniform, geometric, radical meshes - the four mesh design families; grading factor $q$ (p. 16).
- h-, p-, hp-extension - increasing degrees of freedom by refinement, by degree, or both (p. 17).
- Degrees of freedom $N$ - maximum number of linearly independent functions in $S^0(I)$ (p. 25).
- Element stiffness matrix, element-level Gram (mass) matrix - eq. (1.64) and eq. (1.68); both symmetric (pp. 18-19).
- Assembly - summing element matrices into the global system while reconciling local and global numbering (p. 21).
- Condensation - element-level elimination of internal basis function coefficients (p. 24).
- Extraction function - test function used post-solution to compute a functional (p. 27).
- Nodal forces - $\{f^{(k)}\} = [K^{(k)}]\{a^{(k)}\} - \{\bar r^{(k)}\}$; sign convention differs from bar force (p. 29).
- A priori / a posteriori estimators - asymptotic rate from regularity versus error estimate for a particular solution (p. 30).
- Regularity - for fractional $\alpha$, the maximum number of square integrable (fractional) derivatives; $u_{EX} \in H^{\alpha + 1/2 - \epsilon}(I)$ (p. 30).
- Hierarchic sequence of FE spaces - $S_1 \subset S_2 \subset \cdots$, the prerequisite for extrapolation (p. 33).
- Eigenpairs, spectrum - solutions $(\omega_i, U_i)$ of eq. (1.140); the set of eigenvalues (p. 43).
- Rayleigh quotient - $B(u,u)/D(u,u)$ (p. 44).
- Stability, Babuška-Brezzi (BB) condition - boundedness of the FE solution by the best approximation; eq. (1.155); Babuška 1971, Brezzi 1974 (p. 47).
- Mixed method - simultaneous approximation of $u$ and the flux $F = \kappa u'$ in separate spaces (p. 47).
- Nitsche's method, penalty parameter - essential conditions imposed weakly through a stabilised penalty term $1/\epsilon$ (pp. 48-49).

## Figures and tables to return to
- Fig. 1.1 - exact against two-coefficient approximate solution; the first picture of energy minimisation at work (p. 5).
- Fig. 1.3 - Lagrange shape functions for $p = 2$ (p. 14).
- Fig. 1.4 - Legendre (hierarchic) shape functions to $p = 4$, with explicit formulae on the plot (p. 15).
- Fig. 1.5 - the standard picture of 1D basis functions assembled from mapped shape functions on a three-element mesh (p. 22).
- Table 1.1 - local-to-global numbering for the three-element example; the assembly bookkeeping in one table (p. 22).
- Fig. 1.6 - recommended choice of the Dirichlet lift $u^\star$ (p. 25).
- Fig. 1.7 - slow oscillatory convergence of the directly computed $u'(0)$ up to $p = 100$; the case for extraction (p. 29).
- Fig. 1.9 and Fig. 1.10 - relative error against $N$ on log-log axes for h- and p-versions; the doubling of the rate read straight off the slopes (pp. 36-37).
- Fig. 1.11 - boundary layer profiles as $\epsilon$ shrinks; why uniform refinement fails there (p. 38).
- Table 1.2 and Table 1.3 - exact against extrapolated potential energies; the estimator validated (p. 35).
- Table 1.4 and Table 1.5 - element-by-element error distribution for fractional and integer $\alpha$; the singular element dominates (pp. 41-42).
- Fig. 1.13 and Fig. 1.14 - $(\omega_{FE}/\omega_{EX})_n$ across the spectrum for h- and p-versions; which computed eigenvalues to trust (p. 45).
- Table 1.7 - Nitsche's method: $u(\ell)$ across twelve decades of $\gamma$ (p. 50).

## Where to find what
| Topic | Pages |
|---|---|
| Simulation defined, membrane analogy | 1 |
| Design certification, numerical error tolerance $\tau$ | 2 |
| Finite element modelling versus numerical simulation | 2-3 |
| Model form versus discretisation errors | 3 |
| Introductory problem, minimisation of integral $I$ | 3-5 |
| Choice of basis functions, span, linear independence | 5-6 |
| Strong versus weak form, summary of main points | 6 |
| Generalised formulation, bilinear and linear forms | 6-9 |
| Energy norm, energy space, trial and test spaces | 7-8 |
| Essential, Neumann, Robin boundary conditions | 8-9 |
| Uniqueness of the weak solution (Theorem 1.1) | 9-10 |
| Principle of minimum potential energy (Theorem 1.2) | 11 |
| Euler-Lagrange equation, recovering the strong form | 11-12 |
| Approximate solutions, Galerkin orthogonality, best approximation | 12-13 |
| Standard polynomial space, condition number | 13 |
| Lagrange shape functions | 14 |
| Legendre (hierarchic) shape functions | 14-16 |
| Finite element spaces in 1D, four mesh types | 16-17 |
| Optimal grading factor and radical mesh exponent | 17 |
| h-, p-, hp-extension definitions | 17 |
| Element stiffness matrix | 18 |
| Element Gram (mass) matrix, Lobatto point variant | 19-20 |
| Right hand side vector | 20-21 |
| Assembly, local and global numbering | 21-23 |
| Condensation | 24 |
| Enforcement of Dirichlet boundary conditions | 24-26 |
| Solvers, form of the finite element solution | 26 |
| QoI computation, direct and indirect (extraction) | 26-29 |
| Nodal forces and their equilibrium | 29-30 |
| Regularity of the exact solution | 30-31 |
| A priori rate of convergence, algebraic and exponential | 31-32 |
| Error and potential energy (Theorem 1.5), shift theorem | 32 |
| A posteriori estimation by extrapolation | 32-36 |
| Model singular problem, exact potential energies | 34-35 |
| h- and p-convergence rates verified numerically | 36 |
| Error in the extracted QoI, superconvergence | 36-38 |
| Choice of discretisation, boundary layers | 38-39 |
| Discretisation for singular solutions, element error distribution | 39-42 |
| Round-off and integration errors | 41-42 |
| Eigenvalue problems, separation of variables | 42-44 |
| Rayleigh quotient, accuracy of computed spectra | 44-46 |
| Attributes shared by all FE methods, stability, BB condition | 46-47 |
| Mixed method | 47-48 |
| Nitsche's method, stabilisation, numerical example | 48-50 |

## Links
[[Finite element method]], [[Weak form]], [[Energy norm]], [[Galerkin orthogonality]], [[Minimum potential energy]], [[Shape functions]], [[Legendre polynomials]], [[Mesh design]], [[p-version FEM]], [[Convergence rates]], [[A posteriori error estimation]], [[Quantities of interest]], [[Boundary layers]], [[Eigenvalue problems]], [[Rayleigh quotient]], [[Babuska-Brezzi condition]], [[Nitsche's method]], [[Verification and validation]]

## Flags
- Symmetric, antisymmetric and periodic boundary conditions are deferred to Chapter 2, the next slice (p. 9).
- Generalisation of all concepts to 2D and 3D is deferred to subsequent chapters (p. 3); the Kronecker delta used on p. 20 is defined in eq. (2.1) of the next slice.
- History of finite element modelling and of the h/p/hp naming is deferred to Chapter 5 (pp. 2, 17); minimum potential energy is reused as the starting point for beams, plates and shells in Chapter 7 (p. 11).
- Heavy forward references to Appendices A (norms, linear and bilinear forms), B (a priori estimates), D (Legendre polynomials, shape functions to $p = 8$), E (numerical integration, Lobatto points).
- All assigned pages read cleanly; no errata suspected.
