---
source: Finite Element Analysis. Method, Verification and Validation, 2nd edition, Barna Szabo and Ivo Babuska, Wiley 2021
pages: 119-154
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
The chapter links the regularity of the exact solution to the design of the discretization (preprocessing) and to the extraction of quantities of interest with error estimates (postprocessing). The engine is the corner asymptotic expansion $u = r^{\lambda}F(\theta)$: its eigenvalues set the convergence rates of h- and p-extensions, its coefficients (flux and stress intensity factors) are extracted superconvergently by a contour integral method. Model problems on the L-shaped domain, the Fichera cube, bimaterial corners and crack tips demonstrate each case, always comparing uniform h-refinement, p-extension on a fixed mesh, and p-extension on a graded mesh. The chapter closes with Poisson ratio locking as a robustness failure of low order h-elements, a four-step solution verification procedure, and a case study where the requested quantity of interest (maximum stress at a singular arc) was infinite, so no discretization could converge to it.

## Key ideas
- Solutions of elliptic problems on polygonal and polyhedral domains are typically piecewise analytic; mesh grading plus rising p yields exponential convergence (p. 119).
- Singularities usually come from simplifications in the problem formulation, not from physics (p. 119).
- Divide the domain into regions of primary and secondary interest; secondary singularities slow convergence without being wanted quantities (p. 119).
- Regularity is counted in square integrable derivatives; in 2D and 3D it depends on vertex angles, materials, boundary conditions and sources, in 3D also on edge intersection angles (p. 120).
- Corner eigenvalues with $\lambda < 0$ solve the equation but lie outside the energy space; only $\lambda > 0$ enters the expansion (p. 121).
- For reentrant angles $\alpha > \pi$ the first derivative is infinite at the corner and $u \in H^{1+\lambda_1-\epsilon}(\Omega)$ (p. 121).
- When the exact solution is analytic, p-extension converges exponentially and beats any uniform h-sequence (p. 122).
- With a vertex singularity, the asymptotic p-rate on a uniform mesh is twice the h-rate: $\beta_p = 2\beta_h$ in 2D (p. 124).
- Radical grading overrefines the corner so the error comes from the smooth part; the aim of mesh design is to keep p-extension in its pre-asymptotic (exponential) range for the p the software supports (p. 125).
- The a posteriori estimator assumes the asymptotic algebraic rate; in the pre-asymptotic range convergence is stronger, so errors are slightly overestimated (p. 125, Remark 4.1 p. 126).
- The grading that minimises energy norm error is not the optimum for a pointwise quantity, but sits close to it (p. 127, Remark 4.2 p. 128).
- The contour integral method extracts expansion coefficients from path independence plus eigenfunction orthogonality and is superconvergent: the coefficient error falls faster than the energy norm error (p. 130).
- At bimaterial corners $F(\theta)$ is piecewise analytic; eigenvalues come from a determinant condition on continuity, flux continuity and boundary conditions (p. 132).
- The Steklov method turns the corner eigenproblem into a numerical eigenvalue problem on a circular contour (p. 133).
- In 3D, edge expansions need shadow functions; for the L-shaped section they are smoother than the eigenfunctions and do not affect the convergence rate (p. 137, Remark 4.4).
- Crack tips are the $\alpha = 2\pi$ corner: all eigenvalues are $\pm n/2$, and the leading coefficients are the stress intensity factors of LEFM (p. 139).
- In 3D the singularity where a crack front meets a free surface differs from the plane strain crack tip singularity (p. 141).
- Concentrated forces and point constraints are inadmissible in 2D and 3D elasticity: the displacement grows as $\ln r$ and leaves the energy space (p. 143).
- A step traction gives finite but not single valued stresses at the singular point (p. 143).
- Poisson ratio locking: at $\nu \to 1/2$, incompressibility plus interelement continuity collapses a p = 1 quadrilateral mesh to a five dimensional space, whatever the element count; the p-version does not lock (p. 143-145).
- The product space is more robust than the trunk space near incompressibility; the p-version is more robust than the h-version in general (p. 147).
- Solution verification: check input data, then show the quantity of interest is substantially independent of the discretization; a value still changing with N cannot be near its limit (p. 148).
- Point convergence of a maximum stress need not be monotonic under h- or p-extension (p. 150).
- Pollution errors are errors in the primary region caused by underdiscretization of the secondary region (p. 150-151).
- Proper model formulation depends on the quantity of interest: a QoI that is infinite in the exact solution (maximum stress at a singular arc) makes the question meaningless; a failure predictor must be finite and continuous in the load (p. 152-153).

## Equations that matter
$$\lambda_m^{(s)} = \frac{(2m-1)\pi}{\alpha}, \qquad \lambda_n^{(a)} = \frac{2n\pi}{\alpha} \tag{4.6}$$
Symmetric and antisymmetric corner eigenvalues for opening angle $\alpha$ with $u = 0$ on both edges (p. 121).

$$u = \sum_{m=1}^{\infty} A_m r^{\lambda_m^{(s)}} \cos\lambda_m^{(s)}\theta + \sum_{n=1}^{\infty} B_n r^{\lambda_n^{(a)}} \sin\lambda_n^{(a)}\theta, \quad r \le r_c \tag{4.7}$$
The corner asymptotic expansion; the whole chapter either exploits its regularity or extracts its coefficients (p. 121).

$$x_i = \left(\frac{i-1}{M}\right)^{\gamma}, \quad i = 1, 2, \ldots, M+1 \tag{4.15}$$
Node placement of the radically graded mesh along an edge leaving the singular point (p. 125).

$$\begin{Bmatrix} q_x^{(FE)} \\ q_y^{(FE)} \end{Bmatrix} = -\begin{bmatrix} k_x & k_{xy} \\ k_{xy} & k_y \end{bmatrix} [J]^{-1} \begin{Bmatrix} \partial u_{FE}/\partial\xi \\ \partial u_{FE}/\partial\eta \end{Bmatrix} \tag{4.16}$$
Flux vector at a point, direct from the finite element solution through the inverse Jacobian (p. 126).

$$I_{\Gamma^\star} = -\int_{\Gamma^\star} (\nabla u \cdot \mathbf{n})\, v \, ds + \int_{\Gamma^\star} (\nabla v \cdot \mathbf{n})\, u \, ds \tag{4.19}$$
Path independent integral for two harmonic functions; the foundation of the contour integral method (p. 129).

$$A_k = -\frac{1}{2 C_{kk}^{-} \lambda_k} I_{\Gamma_\varrho}(u_{EX}, w_k) \tag{4.23}$$
Flux intensity factor via the extraction function $w_k = r^{-\lambda_k}\phi_k^{-}(\theta)$; substituting $u_{FE}$ gives the superconvergent approximation (p. 130).

$$k_h^{(i)} = 1 + \frac{1}{2}\,\frac{\log(\pi(h_i)-\pi_{\mathrm{ref}}) - \log(\pi(h_{i-1})-\pi_{\mathrm{ref}})}{\log(h_i) - \log(h_{i-1})} \tag{4.35}$$
Estimate of the Sobolev index k from a sequence of h-refined solutions; in 3D it gives $\beta_h \approx (k_h - 1)/3$ by eq. (4.38) (p. 136).

$$\sigma_x = \frac{K_I}{\sqrt{2\pi r}} \cos\frac{\theta}{2}\left(1 - \sin\frac{\theta}{2}\sin\frac{3\theta}{2}\right) + T + O(r^{3/2}) \tag{4.42}$$
Leading Mode I crack tip stress with the T-stress; (4.43) and (4.44) complete Mode I, (4.45) to (4.47) give Mode II with $K_{II}$ (p. 139).

$$I_\Gamma = \int_\Gamma (T_x^{(\mathbf{u})} w_x + T_y^{(\mathbf{u})} w_y)\, ds - \int_\Gamma (T_x^{(\mathbf{w})} u_x + T_y^{(\mathbf{w})} u_y)\, ds \tag{4.48}$$
Path independent contour integral for the Navier equations; extracts $K_I$, $K_{II}$ and $T$ (p. 140).

$$\epsilon_x^{(i)} + \epsilon_y^{(i)} \equiv \frac{\partial u_x^{(i)}}{\partial x} + \frac{\partial u_y^{(i)}}{\partial y} = 0 \tag{4.61}$$
Plane strain incompressibility constraint; with continuity it forces global linear fields at p = 1, the mechanism of locking (p. 144).

## Numbers worth citing
- $\pi_{\mathrm{exact}} = -0.90364617$, L-shaped domain with circular cut-out, $r_0 = 0.05$, Laplace, mixed boundary conditions (p. 122).
- $\pi_{\mathrm{exact}} = -0.9181133309$, L-shaped domain, $u_{EX} = r^{2/3}\cos(2\theta/3)$, Neumann on $\Gamma_q$ (p. 124).
- $\pi_{EX} = 0.91803479$, Dirichlet variant with cut-out $r_0 = 0.001$ (p. 127, footnote).
- Contour integral extraction: at p = 5 the error in $A_1$ is 0.13% against 1.95% in energy norm; uniform 27 element mesh, extraction radius $\varrho = 0.2$ (p. 130, Table 4.3).
- Bimaterial corner, aluminium $k_{al} = 202$ W/(m K) on chrome-nickel steel $k_{cn} = 16.3$ W/(m K), insulated axes: $\lambda_1 = 0.5238$ (p. 133); $\lambda_2 = 1.4762$ (p. 133); zero temperature on the axes instead: $\lambda_1 = 0.8762$ (p. 133).
- Fichera domain reference energy $\pi_{\mathrm{ref}} = -4.44688294$, extrapolated from p-extension on a 189 element radical mesh, $\gamma = 6.2$ (p. 134-135).
- Fichera rates: $k_h \to 1.337$, $\beta_h \approx 0.113$ (uniform meshes, p = 2); $\beta_p \approx 0.209$ and rising on the uniform 189 element mesh (p. 136-137).
- L-shaped planar elasticity, stress-free reentrant edges, plane strain $\nu = 0.3$: $\lambda_1 = 0.54448374$, so $\beta_h = \lambda_1/2$, $\beta_p = \lambda_1$; $\pi(\mathbf{u}_{EX}) = -4.15454423\, a_1^2 \ell^{2\lambda_1} t_z / E$ (p. 137).
- Compact tension specimen, aluminium alloy $E = 71.7$ GPa, $\nu = 0.333$, $a = 25$ mm, 1 kN load: plane strain $K_I = 54.45$ MPa mm$^{1/2}$ (p. 141); 3D maximum 59.4 MPa mm$^{1/2}$ at the symmetry plane, 8.4% above plane strain (p. 141); ASTM E1820-01 formula gives 54.64 MPa mm$^{1/2}$ (p. 142).
- Standard fracture tests reject the result if the initial crack length varies by more than 5% along the front (p. 142).
- Rigid circular inclusion, plane strain, $b/a = 5$: exact strain energy $U = 7.31883865\, \sigma_\infty^2 a^2 t_z / E$ (p. 146).
- Locking benchmark, four element mesh, p = 8, $\nu = 0.49999$: maximum norm error in $\sigma_x + \sigma_y$ is 32.84% (product space) against 233.1% (trunk space) (p. 147).
- Shear fitting verification: 26 element mesh, trunk space, estimated energy norm error 0.97% at p = 8, N = 8769 (p. 149).
- Composite ring, $\Delta T = 100$ C: plane stress model reported 22.1 MPa (improper model), axisymmetric model 52.8 MPa (divergent quantity); maximum radial displacement 0.121 mm and 0.122 mm from the two models, both proper for that QoI (p. 151-152).

## Definitions introduced
- Regularity - the number of square integrable derivatives of the exact solution (p. 120).
- Region of primary (secondary) interest - subdomain from which QoIs are (are not) extracted (p. 119).
- Effectivity index $\theta$ - ratio of estimated to exact relative error (p. 125).
- Flux intensity factors - coefficients $A_k$ of the corner asymptotic expansion for the Laplace problem (p. 128).
- Contour integral method - coefficient extraction from a path independent integral and eigenfunction orthogonality (p. 130).
- Superconvergence - the extracted coefficient error falls faster than the energy norm error (p. 130).
- Steklov method - numerical eigenpair computation on a circular contour around the singular point (p. 133).
- Fichera cube - $(-1,1)^3 \setminus [0,1]^3$, standard 3D singularity benchmark (p. 133).
- Shadow functions - terms augmenting 3D edge expansions when the coefficients vary along the edge (p. 137).
- T-stress - the constant term in the Mode I crack tip expansion (p. 139).
- Plane strain fracture toughness $K_{Ic}$ - stress intensity factor at which crack propagation becomes rapid and unbounded; a material property (p. 140).
- Robust scheme - uniformly convergent over all admissible values of a parameter (p. 143).
- Poisson ratio (volumetric) locking - convergence failure of low order h-elements as $\nu \to 1/2$ (p. 143).
- Solution verification - showing correct input data and QoIs substantially independent of the discretization (p. 148).
- Hierarchic spaces - each finite element space contains its predecessor; p-extensions are hierarchic, generated mesh sequences generally are not (p. 150).
- Pollution errors - errors from insufficient discretization of the region of secondary interest (p. 151).

## Figures and tables to return to
- Fig 4.1 - reentrant corner notation ($\alpha$, r, $\theta$) used throughout the chapter (p. 120).
- Fig 4.3 - h against p convergence when the exact solution is analytic; p-extension wins (p. 123).
- Fig 4.5 - three schemes against a vertex singularity; radical mesh plus p-extension is the efficient one (p. 124).
- Table 4.1 - estimated and exact energy norm errors with effectivity index, radical mesh $\gamma = 4.9$ (p. 125).
- Table 4.2 - same mesh under Dirichlet conditions on all segments (p. 126).
- Fig 4.6 - grading exponent m against energy norm and flux errors; optima at m near 4 and 5 (p. 127).
- Table 4.3 - superconvergence of the contour integral method (p. 130).
- Fig 4.10 - determinant against $\lambda$ for the bimaterial corner; eigenvalues read off as roots (p. 132).
- Tables 4.4 to 4.6 with Fig 4.12 - Fichera domain convergence data for the three schemes (p. 135-136).
- Table 4.7 with Fig 4.13 - L-shaped elasticity rates against theoretical estimates (p. 138).
- Fig 4.15 - $K_I$ along a 3D crack front against the plane strain value (p. 141).
- Table 4.9 with Fig 4.19 - product against trunk space near incompressibility (p. 147).
- Fig 4.21 - non-monotonic point convergence of von Mises stress under h- and p-extension (p. 150).
- Table 4.11 - composite ring geometry and material data (p. 151).
- Fig 4.23 - divergence of the maximum principal stress at a singular arc (p. 152).

## Where to find what
| Topic | Pages |
|---|---|
| Chapter aims, pre- and postprocessing defined | 119 |
| Regularity, primary and secondary interest | 119-120 |
| Laplace corner expansion in 2D, eigenvalues | 120-121 |
| Model problem with analytic solution (cut-out) | 121-123 |
| Model problem with vertex singularity, three schemes | 123-125 |
| Radical mesh grading, effectivity index | 124-125 |
| Dirichlet boundary condition approximation | 126 |
| Flux vector at a point, grading study | 126-128 |
| Flux intensity factors, contour integral method | 128-131 |
| Normalised eigenfunctions, extraction example | 131 |
| Material interfaces, bimaterial corner eigenvalues | 131-133 |
| Steklov method | 133 |
| Laplace in 3D, Fichera domain, rates | 133-137 |
| Shadow functions (Remark 4.4) | 137 |
| Planar elasticity on the L-shaped domain | 137-139 |
| Crack tip fields, Mode I and II, T-stress | 139 |
| Stress intensity factor computation, CT specimen 2D and 3D | 140-142 |
| Concentrated force, step traction, admissibility | 142-143 |
| Robustness, Poisson ratio locking mechanism | 143-145 |
| Rigid inclusion benchmark, product against trunk space | 145-147 |
| Solution verification, four steps | 148-149 |
| Shear fitting example, point convergence | 149-150 |
| Hierarchic spaces, pollution errors | 150-151 |
| Composite ring case study, improper QoI | 151-153 |

## Links
[[Finite element method]], [[Verification and validation]], [[Stress singularities]], [[Laplace equation]], [[Fracture mechanics]], [[Stress intensity factor]], [[Mesh grading]], [[p-version finite elements]], [[Superconvergence]], [[Poisson ratio locking]], [[Convergence rates]]

## Flags
- Book page 154 (PDF 174) is blank; the chapter text ends on p. 153.
- Table 4.2 (p. 126) carries a caption identical to Table 4.1 without stating the Dirichlet condition that distinguishes it; the positive $\pi$ values are the clue (Exercise 4.5 addresses the sign).
- Continuations into later slices: concentrated forces and point constraints are taken up in Section 5.2.8 (p. 143), mechanical contact in Section 9.2.4 (p. 150), calibration of failure predictors in Chapter 6 (p. 153).
- Supporting theory sits in appendices, not this slice: elasticity corner eigenproblems in Appendix G (p. 137), stress intensity factor extraction and energy release rate in Appendix H (p. 140), empirical Fichera elasticity data in Appendix C (p. 137).
- Remark 4.5 attributes the CT specimen $K_I$ formula to ASTM E1820-01, while footnote 6 (p. 140) lists ASTM E399 as the plane strain toughness standard; noted in case of erratum.
