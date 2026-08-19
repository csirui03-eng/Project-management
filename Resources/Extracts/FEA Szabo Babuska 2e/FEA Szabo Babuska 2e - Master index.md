---
source: "Finite Element Analysis: Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021"
type: master-index
updated: 2026-08-19
tags: [extract, index]
---

## What this source is
A graduate text and working reference on the finite element method built around one argument: separate the mathematical model from its numerical solution, so that model form error and discretisation error can be estimated and controlled independently.
It carries the authority of Szabó and Babuška, whose names attach to the stability condition every finite element method must satisfy.
The worked material runs from 1D fundamentals through p-version implementation, mesh design against singularities, reduced and non-linear models, to a full validation life cycle on high cycle fatigue; numerical solutions in the book come from StressCheck.
Go to it when the question is whether a computed quantity can be trusted, how to design a discretisation for a known solution character, or how calibration and validation are done properly.

## Chapter map
- [[FEA Szabo Ch 1 - Introduction to the finite element method]] - the full method in one dimension: weak form, shape functions, assembly, error estimation, extraction of quantities of interest, eigenvalue problems, the Babuška-Brezzi condition (pp. 1-50).
- [[FEA Szabo Ch 2 - Boundary value problems]] - strong and weak forms for heat conduction and linear elasticity, boundary condition taxonomy, dimensional reduction, incompressibility, residual stresses (pp. 51-89).
- [[FEA Szabo Ch 3 - Implementation]] - standard elements, shape functions, mappings, quadrature, stiffness and load matrices, post-solution operations (pp. 91-117).
- [[FEA Szabo Ch 4 - Pre- and postprocessing procedures and verification]] - corner singularities and regularity, mesh design, superconvergent extraction of intensity factors, locking, the four-step solution verification procedure (pp. 119-153).
- [[FEA Szabo Ch 5 - Simulation]] - numerical simulation against finite element modelling, Girkmann, fastened connection and coil spring case studies, calibration versus tuning, simulation governance (pp. 155-186).
- [[FEA Szabo Ch 6 - Calibration, validation and ranking]] - the validation life cycle worked on high cycle fatigue of aluminium: notch predictors, likelihood ranking, Bayesian confidence in predictive performance (pp. 187-221).
- [[FEA Szabo Ch 7 - Beams, plates and shells]] - hierarchic dimensionally reduced models: Timoshenko, Bernoulli-Euler, Reissner-Mindlin, Kirchhoff, shell models, thin solid alternatives, frequency comparisons (pp. 223-254).
- [[FEA Szabo Ch 8 - Aspects of multiscale models]] - RVE homogenisation of fibre-matrix laminae, localisation, divergence of pointwise failure measures (pp. 255-264).
- [[FEA Szabo Ch 9 - Non-linear models]] - radiation, large strain, stability and stress stiffening, plasticity, frictionless contact, each verified against classical solutions or benchmarks (pp. 265-287).
- [[FEA Szabo Appendices A-K]] - reference annex: Sobolev spaces, h-convergence proof, 3D convergence data, Legendre polynomials, quadrature tables, mapping points, corner eigenvalues, stress intensity factors, Bayesian data analysis, fastener model, solid mechanics formulas (pp. 289-350).

## Where to find what
| Topic | Chapter | Pages |
|---|---|---|
| Simulation defined, membrane analogy | Ch 1 | 1 |
| Design certification, numerical error tolerance $\tau$ | Ch 1 | 2 |
| Finite element modelling versus numerical simulation | Ch 1 | 2-3 |
| Model form versus discretisation errors | Ch 1 | 3 |
| Introductory problem, minimisation of integral $I$ | Ch 1 | 3-5 |
| Choice of basis functions, span, linear independence | Ch 1 | 5-6 |
| Strong versus weak form, summary of main points | Ch 1 | 6 |
| Generalised formulation, bilinear and linear forms | Ch 1 | 6-9 |
| Energy norm, energy space, trial and test spaces | Ch 1 | 7-8 |
| Essential, Neumann, Robin boundary conditions | Ch 1 | 8-9 |
| Uniqueness of the weak solution (Theorem 1.1) | Ch 1 | 9-10 |
| Principle of minimum potential energy (Theorem 1.2) | Ch 1 | 11 |
| Euler-Lagrange equation, recovering the strong form | Ch 1 | 11-12 |
| Approximate solutions, Galerkin orthogonality, best approximation | Ch 1 | 12-13 |
| Standard polynomial space, condition number | Ch 1 | 13 |
| Analytic function, Euclidean norm, sup/inf, Dirac delta | App A | 289 |
| Normed linear spaces, linear and bilinear forms, trial and test spaces | App A | 290 |
| Convergence in a normed space, $C^k$ and $L^p$ spaces | App A | 291 |
| Sobolev space $H^1$, norm, seminorm, energy norm equivalence | App A | 291-292 |
| Fractional index Sobolev spaces, singular function examples | App A | 292-293 |
| Schwarz inequality for integrals, with proof | App A | 293 |
| Lagrange shape functions | Ch 1 | 14 |
| Legendre (hierarchic) shape functions | Ch 1 | 14-16 |
| Finite element spaces in 1D, four mesh types | Ch 1 | 16-17 |
| Optimal grading factor and radical mesh exponent | Ch 1 | 17 |
| h-, p-, hp-extension definitions | Ch 1 | 17 |
| Element stiffness matrix | Ch 1 | 18 |
| Element Gram (mass) matrix, Lobatto point variant | Ch 1 | 19-20 |
| Right hand side vector | Ch 1 | 20-21 |
| Assembly, local and global numbering | Ch 1 | 21-23 |
| Condensation | Ch 1 | 24 |
| Enforcement of Dirichlet boundary conditions | Ch 1 | 24-26 |
| Solvers, form of the finite element solution | Ch 1 | 26 |
| QoI computation, direct and indirect (extraction) | Ch 1 | 26-29 |
| Nodal forces and their equilibrium | Ch 1 | 29-30 |
| Regularity of the exact solution | Ch 1 | 30-31 |
| A priori rate of convergence, algebraic and exponential | Ch 1 | 31-32 |
| Error and potential energy (Theorem 1.5), shift theorem | Ch 1 | 32 |
| A posteriori estimation by extrapolation | Ch 1 | 32-36 |
| Model singular problem, exact potential energies | Ch 1 | 34-35 |
| h- and p-convergence rates verified numerically | Ch 1 | 36 |
| Error in the extracted QoI, superconvergence | Ch 1 | 36-38 |
| Choice of discretisation, boundary layers | Ch 1 | 38-39 |
| Discretisation for singular solutions, element error distribution | Ch 1 | 39-42 |
| Round-off and integration errors | Ch 1 | 41-42 |
| h-convergence proof, 1D, $p=1$; a priori estimate | App B | 295-296 |
| Eigenvalue problems, separation of variables | Ch 1 | 42-44 |
| Rayleigh quotient, accuracy of computed spectra | Ch 1 | 44-46 |
| Attributes shared by all FE methods, stability, BB condition | Ch 1 | 46-47 |
| Mixed method | Ch 1 | 47-48 |
| Nitsche's method, stabilisation, numerical example | Ch 1 | 48-50 |
| Index notation rules, permutation symbol, divergence theorem (2.2) | Ch 2 | 51-52 |
| Scalar elliptic BVP, Dirichlet/Neumann/Robin conditions | Ch 2 | 53 |
| Generalised formulation of the scalar problem, $B$, $F$, energy space | Ch 2 | 53-55 |
| Potential energy $\pi$ vs $\Pi$, minimisation | Ch 2 | 55 |
| Continuity of $E(\Omega)$ functions, inadmissible point data | Ch 2 | 55 |
| Conservation law and Fourier's law | Ch 2 | 56-57 |
| Heat equation, subdomains with different materials | Ch 2 | 57 |
| Heat conduction boundary and initial conditions, compatibility, radiation | Ch 2 | 58 |
| Symmetry, antisymmetry, periodicity (scalar case) | Ch 2 | 59-60 |
| Even/odd decomposition, numerical treatment of periodic conditions | Ch 2 | 60-61 |
| Planar (2D) heat conduction, modified source $\bar Q$ | Ch 2 | 61-63 |
| Cooling fin example with converged heat loss | Ch 2 | 63 |
| Variable thickness 2D conservation law | Ch 2 | 63-64 |
| Rectangular plate, classical series solution (Example 2.5) | Ch 2 | 64 |
| Axisymmetric heat conduction, condition on the $z$ axis | Ch 2 | 65-66 |
| Heat conduction in a bar, fin equation | Ch 2 | 66-67 |
| Radiation boundary condition and iteration scheme | Ch 9 | 265-266 |
| Temperature-dependent coefficients, split-form iteration | Ch 9 | 266 |
| Strain-displacement relations, strain tensor | Ch 2 | 67-68 |
| Stress notation and sign convention | Ch 2 | 68 |
| Hooke's law, Lame constants, generalised Hooke's law | Ch 2 | 69 |
| Equilibrium, equations of motion | Ch 2 | 69-70 |
| Navier equations (3D) | Ch 2 | 70 |
| Elastic boundary conditions: displacement, traction, spring; initial conditions | Ch 2 | 71-72 |
| Symmetry, antisymmetry, periodicity for vector problems | Ch 2 | 72-73 |
| Planar elasticity notation, plane strain, plane stress | Ch 2 | 73-74 |
| First fundamental problem (Remark 2.4), pipe exercise, Table 2.1 | Ch 2 | 74-75 |
| Navier equations in 2D | Ch 2 | 75 |
| Axisymmetric elastostatic model | Ch 2 | 76 |
| Incompressible elastic materials | Ch 2 | 76-77 |
| Stokes flow | Ch 2 | 78 |
| Empirical limits of material data (Remark 2.5) | Ch 2 | 78 |
| Generalised formulation of elasticity, energy space | Ch 2 | 78-80 |
| Minimum potential energy, hierarchic spaces | Ch 2 | 80-81 |
| Isotropic case, $[D]$ and $[E]$ matrices | Ch 2 | 81 |
| RMS measure of stress, error bounds, near-incompressibility trouble | Ch 2 | 82-83 |
| Principle of virtual work | Ch 2 | 83-84 |
| Uniqueness, rigid body modes, rigid body constraints | Ch 2 | 84-87 |
| Residual stresses, modified Hooke's law, cutting argument | Ch 2 | 87-89 |
| Chapter summary | Ch 2 | 89 |
| Traction vector, Cauchy tetrahedron | App K | 341-342 |
| Transformation of vectors and stresses | App K | 342-344 |
| Principal stresses and invariants | App K | 344 |
| Von Mises stress, yield in pure shear | App K | 344-345 |
| Statically equivalent forces and moments, coil spring example | App K | 345-348 |
| Rod traction formulas: normal, shear, torsion | App K | 348-350 |
| Standard elements in two dimensions | Ch 3 | 91-92 |
| Trunk spaces | Ch 3 | 91-92 |
| Product spaces | Ch 3 | 92-93 |
| Lagrange shape functions, quadrilaterals (4-, 8-, 9-node) | Ch 3 | 93-94 |
| Lagrange shape functions, triangles; triangular coordinates | Ch 3 | 94-95 |
| Hierarchic shape functions, quadrilaterals | Ch 3 | 95-96 |
| Hierarchic shape functions, triangles | Ch 3 | 96-97 |
| Legendre polynomials, recursion, orthogonality, Gauss abscissas | App D | 301-302 |
| Hierarchic shape functions $N_6$ to $N_9$ and general $N_i$ | App D | 302 |
| Isoparametric mapping, quadrilaterals and triangles | Ch 3 | 97-98 |
| Pull-back polynomials | Ch 3 | 98 |
| Quarter-point and singular elements | Ch 3 | 98-99 |
| Blending function mapping | Ch 3 | 99-101 |
| High-order mapping, optimal interpolation points, Lebesgue constant | Ch 3 | 101 |
| Rigid body rotations and choice of mapping | Ch 3 | 102 |
| Finite element spaces in two dimensions | Ch 3 | 102-103 |
| Essential boundary conditions by least squares | Ch 3 | 103 |
| Elements in three dimensions | Ch 3 | 103-104 |
| Mapping in three dimensions, surface approximation, sphere and shell examples | Ch 3 | 105-106 |
| Volume and area integrals, Jacobian determinant, proper mapping | Ch 3 | 106-107 |
| Quadrature point requirements | Ch 3 | 107 |
| Gaussian quadrature, weights, error term, exactness rule | App E | 303-304 |
| Quadrature on quadrilateral and hexahedral elements | App E | 304 |
| Gauss-Lobatto quadrature, weights, error term | App E | 304-305 |
| Surface and contour integrals | Ch 3 | 107-108 |
| Differentiation via inverse Jacobian | Ch 3 | 108 |
| Stiffness matrices | Ch 3 | 109-110 |
| Load vectors: volume forces, surface tractions, thermal loading | Ch 3 | 110-111 |
| Summary of the main points | Ch 3 | 111 |
| Post-solution operations, direct and indirect methods | Ch 3 | 111 |
| Solution and first derivatives at a point, inverse mapping | Ch 3 | 111-112 |
| Display grids, contour plots, min/max search | Ch 3 | 112 |
| Nodal forces, definition and h-version use | Ch 3 | 113-115 |
| Nodal forces in the p-version, Example 3.3 | Ch 3 | 115-117 |
| Nodal forces and stress resultants, extraction | Ch 3 | 117 |
| Chapter summary, convergence as necessary condition | Ch 3 | 117 |
| Chapter aims, pre- and postprocessing defined | Ch 4 | 119 |
| Regularity, primary and secondary interest | Ch 4 | 119-120 |
| Laplace corner expansion in 2D, eigenvalues | Ch 4 | 120-121 |
| Model problem with analytic solution (cut-out) | Ch 4 | 121-123 |
| Model problem with vertex singularity, three schemes | Ch 4 | 123-125 |
| Radical mesh grading, effectivity index | Ch 4 | 124-125 |
| Dirichlet boundary condition approximation | Ch 4 | 126 |
| Flux vector at a point, grading study | Ch 4 | 126-128 |
| Flux intensity factors, contour integral method | Ch 4 | 128-131 |
| Normalised eigenfunctions, extraction example | Ch 4 | 131 |
| Material interfaces, bimaterial corner eigenvalues | Ch 4 | 131-133 |
| Steklov method | Ch 4 | 133 |
| Laplace in 3D, Fichera domain, rates | Ch 4 | 133-137 |
| Shadow functions (Remark 4.4) | Ch 4 | 137 |
| Planar elasticity on the L-shaped domain | Ch 4 | 137-139 |
| Crack tip fields, Mode I and II, T-stress | Ch 4 | 139 |
| Stress intensity factor computation, CT specimen 2D and 3D | Ch 4 | 140-142 |
| Concentrated force, step traction, admissibility | Ch 4 | 142-143 |
| Robustness, Poisson ratio locking mechanism | Ch 4 | 143-145 |
| Rigid inclusion benchmark, product against trunk space | Ch 4 | 145-147 |
| Solution verification, four steps | Ch 4 | 148-149 |
| Shear fitting example, point convergence | Ch 4 | 149-150 |
| Hierarchic spaces, pollution errors | Ch 4 | 150-151 |
| Composite ring case study, improper QoI | Ch 4 | 151-153 |
| Fichera domain problem statement, STRIPE software | App C | 297 |
| p-convergence reference solution | App C | 298 |
| h-convergence data, $\beta_h \approx (k_h-1)/3$, asymptotic range remark | App C | 298-299 |
| Airy stress function, complex potentials, Kolosov-Muskhelishvili | App G | 311-312 |
| Stress-free edge eigenvalue equations | App G | 312-313 |
| Symmetric eigenvalues, special angles, complex roots | App G | 313-315 |
| Antisymmetric eigenvalues | App G | 315 |
| L-shaped domain singular stress and displacement fields | App G | 315-316 |
| Complex eigenvalues, convergence rate remark | App G | 316 |
| Corner eigenvalue table, three boundary condition types | App G | 316-317 |
| Crack tip asymptotic expansion, T-stress | App H | 319-320 |
| Contour integral method for $K_I$, extraction function, $F(\kappa)$ | App H | 320-321 |
| Energy release rate, crack closure, Mode I and II, combined loading | App H | 321-323 |
| Stiffness derivative method | App H | 323-324 |
| Simulation defined, Pauli on ideas of reality | Ch 5 | 155 |
| Model as transformation $(\mathbf{D},\mathbf{I})\to\mathbf{F}$; "physics-based model" ill defined | Ch 5 | 156 |
| Bernoulli-Euler beam formulation, three steps | Ch 5 | 156-157 |
| Beam model history, Galileo to Eiffel | Ch 5 | 158-159 |
| Range of validity of the beam model | Ch 5 | 159 |
| Numerical simulation defined, error sources, calibration domain | Ch 5 | 159-160 |
| Consistency and stability; randomness of experimental outcomes | Ch 5 | 160 |
| Finite element modelling origins, truss and continuum elements | Ch 5 | 160-162 |
| Element libraries, reduced integration, hourglassing, variational crimes | Ch 5 | 162 |
| Error cancellation in FE modelling practice | Ch 5 | 162-163 |
| Truss element stiffness matrix (Exercises 5.1, 5.2) | Ch 5 | 163 |
| Milestones in numerical simulation, timeline | Ch 5 | 165-167 |
| h-version, p-version, hierarchic models, ASME V&V guideline | Ch 5 | 166-167 |
| Girkmann problem statement and data | Ch 5 | 167-168 |
| Girkmann results: legacy, verified, classical | Ch 5 | 168-170 |
| Structural versus strength analysis idealisation (Remark 5.4) | Ch 5 | 170 |
| Lug problem statement and data | Ch 5 | 170 |
| Model 1: rigid lug, surrogate problem for peak stress | Ch 5 | 171-172 |
| Model 2: linear fastener springs | Ch 5 | 172 |
| Model 3: compression-only springs, iteration | Ch 5 | 173 |
| Model 4: 3D frictionless contact | Ch 5 | 173-174 |
| Model comparison, minimum complexity, parsimony | Ch 5 | 174-175 |
| Gaps and interference, quality of fit (Example 5.1) | Ch 5 | 175 |
| Fastener force model, centre of rotation, force formulas | App J | 337-339 |
| Point-constrained FE model, divergence of displacement | Ch 5 | 176-177 |
| Spring rate definitions doomed under point constraints (Remark 5.8) | Ch 5 | 177 |
| Equilibrium of nodal forces, proof and remarks | Ch 5 | 178-179 |
| Why FE modelling predictions can still match experiment | Ch 5 | 179-180 |
| Coil spring problem, linear solution, spring rate | Ch 5 | 180-182 |
| Stress resultants by cutting the coil; extraction | Ch 5 | 182-183 |
| Nonlinear spring solution, stopping criterion | Ch 5 | 183-184 |
| Hard, soft, semisoft boundary conditions | Ch 5 | 184 |
| Coil spring segment, Wahl formulas, smart apps | Ch 5 | 184-186 |
| Calibration versus tuning | Ch 5 | 163-164 |
| Simulation governance | Ch 5 | 164, 167 |
| Chapter scope, three sub-models, verification stance | Ch 6 | 187 |
| Fatigue data, cycle ratio, sinusoidal stress field, test records | Ch 6 | 187-188 |
| Equivalent stress family, S-N data | Ch 6 | 188-189 |
| Random fatigue limit statistical model | Ch 6 | 189-190 |
| Effect of notches, $K_t$, RVE argument | Ch 6 | 190-191 |
| Predictor formulation philosophy | Ch 6 | 190-191 |
| Peterson and Neuber notch sensitivity, stress averaging remark | Ch 6 | 191-192 |
| Calibration of Peterson's $a$, qualified records, rejection of material constant | Ch 6 | 193-194 |
| Revised formula $q_{\mathrm{rev}}$, least squares as maximum likelihood | Ch 6 | 194-195 |
| Validation against notched data, CDF comparisons | Ch 6 | 195-197 |
| Updated calibration $q_{\mathrm{upd}}$, likelihood ratios vs Peterson and Neuber | Ch 6 | 197-199 |
| Fatigue limit comparison, AA fatigue strength example | Ch 6 | 199-201 |
| Discussion: no tolerance, reject or no-reason-to-reject, Hume | Ch 6 | 201-202 |
| Predictor $G_\alpha$, highly stressed volume | Ch 6 | 202-203 |
| Calibration of $\beta(V, \alpha)$ | Ch 6 | 203-204 |
| Ranking over $\alpha$, comparison with Peterson updated | Ch 6 | 204-205 |
| Biaxial specimens and test programme | Ch 6 | 205-206 |
| In-phase axial, torsion, combined validation; survival function | Ch 6 | 206-208 |
| Domain of calibration, $\eta$ restriction, qualified records | Ch 6 | 208-210 |
| Out-of-phase loading, Extensions A and B, ranking | Ch 6 | 210-214 |
| Bayesian predictive performance, priors, credible intervals | Ch 6 | 214-217 |
| Updated domain of calibration, number of experiments | Ch 6 | 217-218 |
| Management of model development, simulation governance | Ch 6 | 218-220 |
| Obstacles: fuzzy terminology, empty notions, Hawking and Popper | Ch 6 | 220-221 |
| Product rule, Bayes' theorem, marginalization | App I | 325-326 |
| 24S-T3 fatigue test data and specimen geometry | App I | 326-328 |
| Bilinear, fatigue limit and random fatigue limit models, likelihood with runouts | App I | 328-334 |
| Model ranking by Bayes factor | App I | 335 |
| Confidence intervals from profile likelihood | App I | 335-336 |
| Hierarchic beam models, indices (m, n), field and director functions | Ch 7 | 223 |
| Beam loads, stress resultants, elastic foundation, strain energy | Ch 7 | 224 |
| Minimum potential energy formulation; model choice remarks | Ch 7 | 224-225 |
| Timoshenko beam derivation (model (1,0)) | Ch 7 | 225-226 |
| Shear correction factor for beams, kappa = 5/6 | Ch 7 | 226-227 |
| Timoshenko element matrices, decoupling of axial field | Ch 7 | 227-228 |
| Two-span beam worked example (Example 7.1) | Ch 7 | 228-229 |
| Shear locking in Timoshenko beams | Ch 7 | 229 |
| Bernoulli-Euler beam, strong form derivation | Ch 7 | 229-230 |
| Timoshenko strong form (Exercise 7.5) | Ch 7 | 230 |
| C1 energy space, Hermite shape functions, higher shape functions | Ch 7 | 230-232 |
| Bernoulli-Euler element stiffness matrix, p = 5 | Ch 7 | 232 |
| Model accuracy remarks, stress formula, design practice | Ch 7 | 232-233 |
| Beam exercises (7.1-7.11) | Ch 7 | 227-234 |
| Plate models, indices (m_x, m_y, n), stress resultants | Ch 7 | 234-235 |
| Resultant transformations, principal moments, Mohr circle | Ch 7 | 235-236 |
| Reissner-Mindlin plate: kinematics, stress-strain law, asymptotic consistency | Ch 7 | 236-237 |
| Reissner-Mindlin strain energy, flexural rigidity, external potential | Ch 7 | 237 |
| Plate boundary conditions, hard versus soft simple support | Ch 7 | 238 |
| Shear correction factors for plate models | Ch 7 | 238 |
| Plate with hole example, boundary layers, mesh design (Example 7.2) | Ch 7 | 238-239 |
| Rhombic plate benchmark (Exercise 7.17) | Ch 7 | 240 |
| Kirchhoff plate: formulation, energy, biharmonic strong form | Ch 7 | 240-242 |
| Kirchhoff exact triangular plate values (Exercise 7.20) | Ch 7 | 242 |
| Enforcement of C1 continuity, why C0 models are preferred | Ch 7 | 243 |
| Shells: mid-surface, curvilinear bases, hierarchic models | Ch 7 | 247-248 |
| Naghdi shell model | Ch 7 | 248 |
| Novozhilov-Koiter shell model | Ch 7 | 249 |
| Thin solid models, anisotropic trunk and product spaces | Ch 7 | 249-250 |
| Reissner-Mindlin versus thin solid stress comparison (Example 7.3) | Ch 7 | 250-251 |
| Natural frequency model comparison (Example 7.4) | Ch 7 | 251 |
| Cylindrical shell eigenvalue study, thickness sweep (Example 7.5) | Ch 7 | 252-253 |
| Hyperboloidal shell locking exercise (Exercise 7.27) | Ch 7 | 252-253 |
| Chapter summary: scope and limits of reduced models | Ch 7 | 254 |
| Transverse variation of displacements: strip analysis | Ch 7 | 243-244 |
| Homogeneous plates: polynomial directors justified | Ch 7 | 245 |
| Laminated plates: piecewise polynomial directors, failure predictors | Ch 7 | 245-246 |
| RVE definition, homogenisation goal | Ch 8 | 255 |
| $[E_{\text{RVE}}]$ by energy equivalence | Ch 8 | 255-256 |
| Symmetry, six constants, boundary condition problems | Ch 8 | 256-257 |
| Constants from strain energies | Ch 8 | 257 |
| Compliance matrix, engineering constants | Ch 8 | 257-258 |
| Transverse isotropy condition and caveat | Ch 8 | 258-259 |
| Thermal expansion coefficients | Ch 8 | 258 |
| Example constituent properties | Ch 8 | 258 |
| Hexagonal pattern results, size independence | Ch 8 | 259-260 |
| Square pattern results | Ch 8 | 260 |
| Error of assuming transverse isotropy | Ch 8 | 260 |
| Comparison with rule of mixtures | Ch 8 | 261 |
| Localisation | Ch 8 | 261-262 |
| Failure prediction, predictor requirements | Ch 8 | 262-263 |
| Divergence of maximum equivalent strain | Ch 8 | 262-263 |
| Uncertainties in volume fraction and waviness | Ch 8 | 263 |
| Discussion, simulation governance | Ch 8 | 264 |
| Hierarchic view of models, virtual experimentation | Ch 9 | 265 |
| Large strain: Lagrangian and Eulerian description | Ch 9 | 266-267 |
| Almansi strain tensor | Ch 9 | 267 |
| Green strain tensor, reduction to infinitesimal strain | Ch 9 | 268 |
| Strip bent into a cylinder (Example 9.1) | Ch 9 | 268-269 |
| Rigid body rotation exercises | Ch 9 | 269 |
| Initial stress formulation, potential energy with prestress | Ch 9 | 270 |
| Virtual work with initial stress, stress stiffening, spectrum | Ch 9 | 271 |
| Strong form with initial stress (Remark 9.2) | Ch 9 | 272 |
| Euler column as dimensional reduction (Example 9.2) | Ch 9 | 272 |
| Strip buckling load factor verification (Example 9.3) | Ch 9 | 272-273 |
| Prestress effect on frequencies and mode shapes (Example 9.4) | Ch 9 | 273 |
| Cylindrical shell buckling, axial and torsional (Example 9.5) | Ch 9 | 273-274 |
| Shell buckling knockdown factors (Remark 9.3) | Ch 9 | 274 |
| Stability and stiffening exercises | Ch 9 | 275 |
| Plasticity theories, notation, assumptions | Ch 9 | 275-277 |
| Equivalent stress and equivalent strain definitions | Ch 9 | 276 |
| Yield criterion, consistency condition, flow rule | Ch 9 | 277 |
| Shear fitting by deformation theory, Ramberg-Osgood (Example 9.6) | Ch 9 | 277 |
| Incremental theory tangent and algorithm | Ch 9 | 277-278 |
| Deformation theory, secant modulus, $[E_{ep}]$ iteration | Ch 9 | 278-279 |
| DFG plane strain plasticity benchmark (Example 9.7) | Ch 9 | 279-281 |
| Contact conditions and gap function | Ch 9 | 281 |
| Two elastic bars on springs (Example 9.8) | Ch 9 | 281-283 |
| Gap elements in two dimensions, mapping, collocation | Ch 9 | 283-284 |
| Partial penetration and Jacobian sign (Example 9.9) | Ch 9 | 283-284 |
| Lebesgue constant, interpolation error bound | App F | 307-308 |
| Optimal and mean optimal nodal sets | App F | 308-309 |
| Interpolation points on quadrilateral and triangle surfaces | App F | 309-310 |
| Contact algorithm: penalty tractions, spring rates, updating | Ch 9 | 284-285 |
| Hertz sphere contact verification (Example 9.10) | Ch 9 | 285-287 |
| Location of critical stresses in contact (Remark 9.4) | Ch 9 | 287 |
| Chapter summary | Ch 9 | 287 |

## Start here
- [[FEA Szabo Ch 4 - Pre- and postprocessing procedures and verification]] - mesh design against singularities, superconvergent extraction and the four-step solution verification procedure transfer directly to Ansys and MAPDL workflows.
- [[FEA Szabo Ch 7 - Beams, plates and shells]] - reduced against 3D models for plates and shells, natural frequency comparisons and the limits of shell theory for strength; the vibration analyst's chapter.
- [[FEA Szabo Ch 1 - Introduction to the finite element method]] - error control fundamentals plus eigenvalue problems, including which fraction of a computed spectrum is accurate; the ground for both FEA and modal work.

## Not yet extracted
- Front matter: prefaces and companion website note, book pages xi to xvii.
- Bibliography, book pages 351 to 356.
- The book's own subject index, from book page 357.
- All nine chapters and appendices A to K carry extract notes; the main text (book pages 1 to 350) is fully covered.
