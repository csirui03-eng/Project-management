---
source: Finite Element Analysis. Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 91-118
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Chapter 3 turns the formulation of Chapters 1 and 2 into algorithms. It defines the standard elements in two and three dimensions, the polynomial spaces on them (trunk and product), and the two shape function families (Lagrange and hierarchic, the latter built from integrals of Legendre polynomials). It then covers the mappings that carry the standard element onto mesh elements: isoparametric, blending function, and optimal high-order interpolation, including the quarter-point trick for fracture problems. On this representation it builds the working machinery: quadrature with the Jacobian determinant, differentiation via the inverse Jacobian, element stiffness matrices and load vectors, then the post-solution operations that recover point values, derivatives, nodal forces and stress resultants. The closing message: equilibrium of nodal forces says nothing about solution quality; convergence of the data of interest under extension does, which is the bridge to Chapter 4.

## Key ideas
- Standard elements have side length 2 in one, two and three dimensions; the definition is arbitrary but chosen for convenience in mapping and assembly (p. 91).
- Trunk spaces span $\xi^i\eta^j$ with $i+j\le p$; quadrilaterals add one or two degree $p+1$ monomials; triangle dimension is $(p+1)(p+2)/2$ (p. 91).
- Product spaces span all products of the 1D monomials; dimension $(p+1)(q+1)$ (p. 92).
- Lagrange shape functions are unity at their own node and zero at the others, so coefficients are nodal values of $u$ (p. 93).
- The 4-node quad spans $S^1$, the 8-node quad $S^2$ (trunk), the 9-node quad $S^{2,2}$ (product); 3- and 6-node triangles span $S^1$ and $S^2$ via triangular coordinates (p. 93-95).
- Hierarchic quads keep the 4-node functions as nodal modes, add $4(p-1)$ side modes and $(p-2)(p-3)/2$ internal modes for the trunk space, $(p-1)(q-1)$ for the product space (p. 95-96).
- Hierarchic triangles have $3(p-1)$ side modes and $(p-1)(p-2)/2$ internal trunk modes (p. 96-97).
- Isoparametric mapping uses the same shape functions for geometry as for approximation; lower degree is subparametric, higher is superparametric (p. 97).
- Mapped shape functions, the "pull-back polynomials", are polynomials only for straight-side triangles and parallelogram quads; approximation quality is governed by their properties (p. 98).
- Quarter-point mapping makes $\rho\propto\sqrt{r}$ near vertex 1, embedding the $\sqrt{r}$ term used in fracture mechanics; a special case of singular elements (p. 99).
- The blending function method blends parametrically given curved sides linearly into the interior; analytic curves such as circles are represented exactly (p. 99-100).
- The inverse mapping $(\xi,\eta)$ from $(x,y)$ has no explicit form in general; Newton-Raphson iteration computes it (p. 100).
- High-order elements map by blending with bounding curves interpolated at points that minimise the Lebesgue constant; Lobatto abscissas are close to optimal in 1D (p. 101).
- The argument that only iso- and subparametric mappings are admissible because they represent rigid body rotation exactly is flawed: either mapping choice converges as degrees of freedom increase (p. 102).
- A 2D finite element space is characterised by the mesh $\Delta$, the degree array $\mathbf{p}$ and the mapping array $\mathbf{Q}$ (p. 103).
- Essential boundary conditions not expressible in the basis are imposed by least-squares fitting on the side, with nodal coefficients fixed at the end values (p. 103).
- 3D meshes use hexahedra, tetrahedra and pentahedra; edge and face shape functions match the 2D ones along shared entities (p. 103-104).
- In the p-version the element count is fixed, so mapping error must be controlled independently of the mesh; optimal-point blending achieves this (p. 105).
- A mapping is proper when it is single valued with continuous first derivatives and positive Jacobian determinant everywhere; a negative determinant flips the coordinate system to left handed (p. 106-107).
- Minimum quadrature gives exact stiffness coefficients only for linear mapping with constant material properties; otherwise too few points can make the stiffness matrix singular (p. 107).
- The element stiffness matrix splits into six blocks $[K_{\alpha\beta}^{(k)}]$ using logical matrices $[M_1],[M_2],[M_3]$ that place the derivative components (p. 109-110).
- Derivatives of the FE solution are discontinuous across element boundaries; the size of the jump in stress or flux indicates approximation quality, and contour smoothing masks it (p. 112).
- Nodal forces satisfy static equilibrium independently of the solution vector, so their equilibrium is not an indicator of solution quality; they remain useful for stress resultants (p. 113, 115).
- With hierarchic shape functions the first four functions sum to unity for any $p$, so the equilibrium sums run over $n=4$ (p. 115).
- Extraction of stress resultants from nodal forces is much more efficient than direct integration of stresses, which singular points degrade (p. 117).
- Verification requires showing that computed data converge to a limit as degrees of freedom increase; properly designed meshes with increasing $p$ achieve this (p. 117).

## Equations that matter
$$n(p)=\begin{cases}4p & \text{for } p\le 3\\ 4p+(p-2)(p-3)/2 & \text{for } p\ge 4\end{cases}\tag{3.1}$$
Dimension of the trunk space $S^p(\Omega_{st}^{(q)})$ on the standard quadrilateral (p. 92).

$$\phi_k(s)=\sqrt{\frac{2k-1}{2}}\int_{-1}^{s}P_{k-1}(t)\,dt,\qquad k=2,3,\dots\tag{3.24}$$
Integrated Legendre polynomial that generates every hierarchic side and internal mode; the index $k$ is the polynomial degree (p. 95).

$$\tilde{\phi}_k(s)=4\,\frac{\phi_k(s)}{1-s^2},\qquad k=2,3,\dots\tag{3.31}$$
Modified function used to build hierarchic side modes on triangles via $N_k^{(1)}=L_1L_2\tilde{\phi}_k(L_2-L_1)$ and cyclic (p. 96).

$$x=Q_x^{(k)}(\xi,\eta)=\sum_{i=1}^{4}N_i(\xi,\eta)X_i\tag{3.37}$$
Linear isoparametric mapping of the quadrilateral; (3.38) is the same for $y$, (3.39)-(3.40) the quadratic version with 8 nodes (p. 97).

$$S \stackrel{\text{def}}{=} S(\Omega,\Delta,\mathbf{p},\mathbf{Q})=\{\mathbf{u}\mid \mathbf{u}\in E(\Omega),\ \mathbf{u}(Q_x^{(k)},Q_y^{(k)})\in S^{p_k}(\Omega_{st}),\ k=1,\dots,M(\Delta)\}\tag{3.50}$$
Definition of the 2D finite element space: mesh, degree array and mapping array together (p. 103).

$$\sigma_1=\sigma_2=\frac{1}{2}\frac{qr_s}{t_s}\tag{3.52}$$
Membrane-theory principal stress in a pressurised spherical shell; the benchmark for mapping accuracy in Example 3.2 (p. 106).

$$\int_{\Omega_k}F(x,y,z)\,dxdydz=\int_{\Omega_{st}}\mathcal{F}(\xi,\eta,\zeta)\,|J|\,d\xi d\eta d\zeta\tag{3.54}$$
Volume integral pulled back to the standard element via the Jacobian determinant (p. 106).

$$\begin{Bmatrix}\partial/\partial x\\ \partial/\partial y\\ \partial/\partial z\end{Bmatrix}=[J]^{-1}\begin{Bmatrix}\partial/\partial\xi\\ \partial/\partial\eta\\ \partial/\partial\zeta\end{Bmatrix}\tag{3.61}$$
Derivatives with respect to physical coordinates from standard-element derivatives; the book writes $[J]$ out in full (p. 108).

$$\int_{\Omega_k}([D]\{v\})^T[E][D]\{u\}\,dV=\int_{\Omega_k}\{v\}^T\{F\}\,dV+\int_{\partial\Omega_k\cap\partial\Omega_T}\{v\}^T\{T\}\,dS+\int_{\Omega_k}([D]\{v\})^T[E]\{\alpha\}\mathcal{T}_\Delta\,dV\tag{3.62}$$
Element-level weak form for 3D elasticity; every stiffness and load term in the chapter comes from it (p. 109).

$$k_{ij}^{(k)}=\int_{\Omega_{st}}\left([M_\alpha][J_k]^{-1}\{D\}N_i\right)^T[E]\,[M_\beta][J_k]^{-1}\{D\}N_j\,|J_k|\,d\xi d\eta d\zeta\tag{3.65}$$
Stiffness coefficient in quadrature-ready form, with $\{D\}=\{\partial/\partial\xi\ \ \partial/\partial\eta\ \ \partial/\partial\zeta\}^T$ and logical matrices $[M_\alpha]$ (p. 110).

$$u_{FE}(x_0,y_0)=\sum_{i=1}^{n}a_i^{(k)}N_i(\xi_0,\eta_0)\tag{3.71}$$
Solution value at a point after inverse mapping; (3.72) gives the first derivatives via the inverse Jacobian (p. 112).

$$\{f^{(k)}\}=[K^{(k)}]\{a^{(k)}\}-\{\bar{r}^{(k)}\},\qquad k=1,2,\dots,M(\Delta)\tag{3.73}$$
Definition of nodal forces: stiffness times solution minus volume-force and thermal load vector (p. 113).

$$V_{2,3}=\int_{\text{node }2}^{\text{node }3}T_y^{(FE)}\,b\,dy=\sum_{j=1}^{2n}\left(k_{n+2,j}+k_{n+3,j}\right)a_j=f_y^{(2)}+f_y^{(3)}\tag{3.86}$$
Shear resultant on a side extracted from nodal forces; the link between nodal forces and extraction functions (p. 117).

## Numbers worth citing
- Unit semicircle interpolated by degree 5 polynomials, maximum relative error in radius: 0.058% with nodal set $T_1^5$, 0.061% with $T_2^5$, 1.50% with six uniformly spaced points (p. 102).
- Unit sphere meshed with 202 triangular elements, mapped with optimal interpolation points for $p=5$: maximum norm error in radius $4.838\times10^{-7}$; quadratic isoparametric mapping on the same mesh: $2.875\times10^{-4}$, three orders of magnitude larger (p. 105).
- Spherical shell, $r_s=1$, $t_s=r_s/100$, internal pressure, $p=2$, $\nu=0$, same 202-element mesh: $\sigma_1=100.0$ (four significant digits) with optimal mapping points, 102.4 (two significant digits) with quadratic isoparametric mapping (p. 106).
- Curved elements: two extra quadrature points per coordinate direction over the minimum is sufficient in most cases (p. 107).
- StressCheck defaults (footnote): boundary curves approximated by degree 5 polynomials; mapping is superparametric for $p\le4$, isoparametric at $p=5$, subparametric for $p\ge6$ (p. 102).
- Example 3.3 (plane stress, one element, $\ell=1000$ mm, $d=50$ mm, $b=20$ mm, $E=200$ GPa, $\nu=0.295$, imposed $\delta=5$ mm): nodal force $f_x^{(1)}$ moves from $-1971.3$ kN at $p=1$ to $-49.802$ kN at $p=8$, equilibrium satisfied at every $p$ (p. 115-116).

## Definitions introduced
- Trunk space - span of $\xi^i\eta^j$, $i+j\le p$, plus one or two degree $p+1$ monomials on quadrilaterals (p. 91).
- Product space - span of all products of $1,\xi,\dots,\xi^p$ and $1,\eta,\dots,\eta^q$; dimension $(p+1)(q+1)$ (p. 92).
- Triangular coordinates $L_1,L_2,L_3$ - linear functions, unity at one node, zero on the opposite side, summing to 1 (p. 94).
- Hierarchic shape functions - nodal, side and internal modes built from integrals of Legendre polynomials via $\phi_k$ (p. 95).
- Isoparametric, subparametric, superparametric mapping - mapping degree equal to, lower than, or higher than the approximation degree (p. 97).
- Pull-back polynomials - the mapped shape functions, in general not polynomials in $x,y$ (p. 98).
- Quarter-point element - mid-side nodes at the quarter position, embedding $\sqrt{r}$; a kind of singular element (p. 99).
- Singular element - element whose space is enlarged by singular functions to reduce errors from singular points (p. 99).
- Proper mapping - single valued, continuous first derivatives, positive Jacobian determinant at every point of $\Omega_{st}$ (p. 106).
- Display grid - uniform grid on the standard element for p-version plotting; inverse mapping not needed (p. 112).
- Nodal forces - $\{f^{(k)}\}=[K^{(k)}]\{a^{(k)}\}-\{\bar{r}^{(k)}\}$ per element (p. 113).

## Figures and tables to return to
- Fig. 3.1 - standard quadrilateral and triangle with side numbering and dimensions; the conventions used everywhere afterwards (p. 92).
- Fig. 3.2 - Pascal-triangle picture of trunk space spanning sets $S^1, S^4$ (quad) and $S^6$ (triangle) (p. 92).
- Fig. 3.3 - spanning set of the product space $S^{4,2}$ on the quadrilateral (p. 93).
- Fig. 3.4 - hierarchic shape functions for quadrilaterals, trunk space $p=1$ to 8, with the unique sequential mode numbering (p. 96).
- Fig. 3.5 - node numbering for isoparametric quadrilateral and triangular elements (p. 98).
- Fig. 3.6 - notation for quarter-point mapping on the standard triangle (p. 99).
- Fig. 3.8 - quadrilateral elements bounded by circular segments; geometry for the blending-function exercises (p. 101).
- Fig. 3.9 - standard tetrahedral and pentahedral elements with dimensions (p. 104).
- Fig. 3.11 - nodal force notation on the 8-node quadrilateral (p. 114).
- Table 3.1 - Example 3.3 nodal forces versus $p$, showing equilibrium at every level while values still converge (p. 116).
- Table 3.2 - Example 3.3 nodal forces on the smallest solution domain, $p=8$ (p. 117).

## Where to find what
| Topic | Pages |
|---|---|
| Standard elements in two dimensions | 91-92 |
| Trunk spaces | 91-92 |
| Product spaces | 92-93 |
| Lagrange shape functions, quadrilaterals (4-, 8-, 9-node) | 93-94 |
| Lagrange shape functions, triangles; triangular coordinates | 94-95 |
| Hierarchic shape functions, quadrilaterals | 95-96 |
| Hierarchic shape functions, triangles | 96-97 |
| Isoparametric mapping, quadrilaterals and triangles | 97-98 |
| Pull-back polynomials | 98 |
| Quarter-point and singular elements | 98-99 |
| Blending function mapping | 99-101 |
| High-order mapping, optimal interpolation points, Lebesgue constant | 101 |
| Rigid body rotations and choice of mapping | 102 |
| Finite element spaces in two dimensions | 102-103 |
| Essential boundary conditions by least squares | 103 |
| Elements in three dimensions | 103-104 |
| Mapping in three dimensions, surface approximation, sphere and shell examples | 105-106 |
| Volume and area integrals, Jacobian determinant, proper mapping | 106-107 |
| Quadrature point requirements | 107 |
| Surface and contour integrals | 107-108 |
| Differentiation via inverse Jacobian | 108 |
| Stiffness matrices | 109-110 |
| Load vectors: volume forces, surface tractions, thermal loading | 110-111 |
| Summary of the main points | 111 |
| Post-solution operations, direct and indirect methods | 111 |
| Solution and first derivatives at a point, inverse mapping | 111-112 |
| Display grids, contour plots, min/max search | 112 |
| Nodal forces, definition and h-version use | 113-115 |
| Nodal forces in the p-version, Example 3.3 | 115-117 |
| Nodal forces and stress resultants, extraction | 117 |
| Chapter summary, convergence as necessary condition | 117 |

## Links
[[Finite element method]], [[Shape functions]], [[Legendre polynomials]], [[Isoparametric mapping]], [[Blending function method]], [[Numerical quadrature]], [[Jacobian matrix]], [[Stiffness matrix]], [[Fracture mechanics]], [[p-version FEM]], [[Solution verification]]

## Flags
- Book page 118 is blank; chapter text ends on p. 117. No unreadable pages.
- The chapter-level "Summary of the main points" sits on p. 111 inside Section 3.9, before Sections 3.10-3.13; easy to miss when scanning headings.
- Sections 3.10-3.12 (post-solution operations, point evaluation, nodal forces) continue thematically into Chapter 4 (pre- and postprocessing procedures and verification, next slice from p. 119); the chapter summary defers error estimation to Chapter 4 explicitly (p. 117).
- The book spells "Lebesque constant" on p. 101 and p. 105; the standard spelling is Lebesgue. Suspected erratum, carried over into Appendix F references.
- Backward dependencies: stiffness and load algorithms rest on eqs. (2.105) and (2.107) of Chapter 2 (p. 109) and on Sections 1.3.3, 1.3.5 and 1.4.1 of Chapter 1; quadrature detail is in Appendix E, interpolation points in Appendix F, tensor transformation in Appendix K, all outside this slice.
