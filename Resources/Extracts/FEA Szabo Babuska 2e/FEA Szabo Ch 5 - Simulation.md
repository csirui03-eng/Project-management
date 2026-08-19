---
source: Finite Element Analysis - Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 155-186
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Chapter 5 defines simulation as casting a precisely stated idea of physical reality into a mathematical model, then separates that from finite element modelling, where intuition assembles elements from a software library without any stated model. The Bernoulli-Euler beam's 188-year development serves as the template for how models are formulated, tested and bounded. The distinction is then made concrete through paired schematics, the calibration versus tuning contrast, simulation governance, and a milestone timeline from 1956 to 2017. Three worked studies carry the argument: the Girkmann shell-ring problem, where legacy codes scatter and verified codes agree; a six-fastener lug analysed by four models of rising fidelity, isolating model form error once numerical error is verified under 1%; and a coil spring solved linearly and nonlinearly with the boundary condition choice treated as a modelling decision. The punchline: finite element models can be tuned but not validated, because their conceptual and numerical errors are entangled and cancel only for some quantities of interest.

## Key ideas
- A mathematical model is every operation, deterministic or probabilistic, needed to predict the QoIs; simulation begins with a precise statement of an idea of reality (p. 155).
- Two distinct error sources: model form error from the formulation, numerical error from approximating $\mathbf{F}$; the numerical error must be small against experimental error or calibrated coefficients are polluted (p. 160).
- Calibrated models are validated only within the domain of calibration; shrink that domain enough and almost any model can be validated (p. 160).
- A model's definition must state its range of validity: plane sections hold in pure bending; shear deformation matters below length-to-depth about 10 or for transverse loads of wavelength under a few beam depths (p. 159).
- Finite element modelling substitutes intuition for a stated idea, so the error of $\mathbf{F}_{num}$ is undefined; the responsibility for the model passes tacitly to the software developer (p. 162).
- FE modelling works through near cancellation of conceptual errors (variational crimes) and discretisation errors; it is "not a scientific activity but rather an intuition-based, experience-guided artistic undertaking" (p. 163).
- Calibration estimates parameters with the functional form assumed correct; tuning adjusts the mesh to match observations, making FE models interpolators near the tuned point (pp. 163-164).
- FE models cannot be validated because model form error is not separated from discretisation error; they can match some observables and still err in other QoIs (p. 164).
- Simulation governance is a managerial function: command and control over model formulation, verification, data archival and workflow standardisation, tailored to the mission (p. 164).
- Legacy FE code infrastructure was fixed in the 5 to 7 years after the 1965 NASTRAN request for proposal, before the mathematical foundations (from about 1972) existed (p. 165).
- The p-version's convergence rate is at least twice the h-version's per degree of freedom (proven 1981); properly graded meshes give exponential convergence in $p$ (proven 1984) (p. 166).
- Girkmann round robin: 11 of 16 responses used legacy codes; only two attempted solution verification, and their QoIs failed to converge or converged to the wrong result (p. 168).
- Girkmann's classical junction moment was off by a factor near 3; his assumption that the footring resultants pass through the centroid was the cause (p. 169).
- In the lug study the numerical error of Models 2 to 4 is verified under 1%, so all differences between their answers are model form differences (p. 174).
- The minimum complexity a model needs cannot be judged without solving the more comprehensive model; footnote ties this to the law of parsimony (p. 175).
- Quality of fit (gap or interference $\delta_n$) is the dominant uncertainty in fastener forces and peak lug stress (p. 175).
- Point constraints are not admissible in two- or three-dimensional elasticity; strain energy and displacement diverge under refinement, slowly and invisibly in practice (pp. 176-177, 180).
- Nodal forces satisfy equilibrium exactly, independent of the FE solution, so equilibrium of nodal forces says nothing about accuracy (pp. 178-179).
- Whether error cancellation rescues a point-constrained model depends on the QoI: average displacement and strain at a point come out usable, peak stress does not (p. 177).
- A QoI whose exact value is infinite cannot be verified, hence the model cannot be validated, whatever the apparent agreement with experiment (p. 180).
- Hard, soft and semisoft displacement boundary conditions are alternative idealisations; the choice is a modelling decision whose sensitivity must be assessed (p. 184).
- Idealised hard boundary conditions induce edge singularities that are artefacts of the model, excluded from stress estimation (p. 184).
- Classical spring formulas overestimate stiffness by 2.5% against 3D elasticity because the curved bar model restricts the deformation modes (p. 186).
- Smart applications let untrained users explore a design parameter space inside an expert-formulated model (p. 186).

## Equations that matter
$$(\mathbf{D},\ \mathbf{I})\ \rightarrow\ \mathbf{F} \tag{5.1}$$
A mathematical model transforms input data $\mathbf{D}$ into the QoIs $\mathbf{F}$ on the basis of a stated idea of reality $\mathbf{I}$ (p. 156).

$$(EIu'')'' = q \tag{5.6}$$
The Bernoulli-Euler beam model; boundary conditions: simply supported $u = M = 0$, built-in $u = u' = 0$, free $M = V = 0$ (p. 157).

$$(\mathbf{D},\ \mathbf{i})\ \rightarrow\ \mathbf{F}_{num} \tag{5.8}$$
Finite element modelling: intuition $\mathbf{i}$ replaces a stated idea, so no exact solution exists and the error of $\mathbf{F}_{num}$ is undefined (p. 162).

$$k_n = \frac{2E}{d(1+\nu)(1-2\nu)} \tag{5.12}$$
Fastener spring rate for the propping effect of the shank, plane strain assumed (p. 172).

$$T_n = \begin{cases} -k_n(u_n+\delta_n) & \text{for } u_n+\delta_n > 0 \\ 0 & \text{for } u_n+\delta_n \le 0 \end{cases} \tag{5.17}$$
Compression-only fastener traction with gap or interference $\delta_n = (d_f - d_h)/2$; the uncertainty carrier of the lug problem (p. 175).

$$\Delta_W = \frac{4Fr_c^3 n}{Gr_w^4}\left(1 - \frac{3}{16}\left(\frac{r_w}{r_c}\right)^2 + \frac{3+\nu}{2(1+\nu)}\left(\frac{d}{2\pi r_c}\right)^2\right) \tag{5.29}$$
Wahl's classical displacement of a coil spring with $n$ active turns (p. 185).

$$\tau_{max} = \tau_{nom}\left(1 + \frac{5}{4}\frac{r_w}{r_c} + \frac{7}{8}\left(\frac{r_w}{r_c}\right)^2\right), \qquad \tau_{nom} \equiv \frac{2Fr_c}{\pi r_w^3} \tag{5.30, 5.31}$$
Classical peak shear stress in a coil spring; compares with the 3D solution to 2.6% (p. 186).

## Numbers worth citing
- Galileo (1638) overestimated beam strength by a factor of 3, yet got the $h/b$ strong-axis ratio right (p. 158); Navier completed the beam model in 1826; first large engineering use, Eiffel Tower, 1889 (p. 158).
- Girkmann data: shell thickness 0.06 m, crown radius 15.00 m, ring at meridional angle 40 degrees, ring 0.60 m by 0.50 m, $E = 20.59$ GPa, $\nu = 0$, homogenised unit weight 32.69 kN/m^3, gravity load only (p. 167).
- Girkmann verified answers: $Q_\alpha \approx 943$ N/m and $M_\alpha \approx -36.8$ Nm/m at the shell-ring junction; maximum moment about 254.9 Nm/m at meridional angle 38.15 degrees (Table 5.2, p. 169).
- Legacy code spread for $M_\alpha$: $-205$ to $17{,}977$ Nm/m on the same problem (p. 169); Girkmann's classical value $-110.5$ Nm/m, Pitkäranta's M-B-RE model $-36.67$ Nm/m (Table 5.3, p. 170).
- Lug data: 2014-T6 aluminium, $E = 7.52\times10^4$ MPa, $\nu = 0.397$, thickness 6.4 mm, load 12.0 kN at 35 degrees (p. 170).
- Surrogate estimate of peak lug stress 111.6 MPa versus 206.7 MPa with statically equivalent tractions applied at the holes: the surrogate assumption alone is a large model error (p. 172).
- Peak lug stress: Model 3 (nonlinear springs) 254.9 MPa, Model 4 (3D contact) 287.4 MPa, an 11% difference, both at fastener 6, numerical error verified under 1% (pp. 173-175).
- Model 3 sensitivity: a 10% cut in spring rate moves peak stress 0.04% and peak fastener force 27 N (0.4%) (p. 173).
- A 0.025 mm gap at fastener 6 alone redistributes the fastener forces and moves peak stress to 189.2 MPa (Example 5.1, Table 5.8, p. 175).
- Point-constrained lug: exact average hole displacement is infinite; computed value 0.105 mm at $p = 2$, so relative error 100% while looking plausible (p. 177); peak stress swings from 184.0 ($p=1$) to 468.6 ($p=2$) against Model 3's 254.7 (Table 5.10, p. 178).
- Coil spring: coil radius 50.0 mm, pitch 25.0 mm, wire radius 5.0 mm, AISI 5160, $E = 200$ GPa, $\nu = 0.285$, yield 285 MPa (p. 181).
- Spring rate: linear model $k = 2U/\Delta^2 = 20.83$ N/mm, relative error under 0.05% (p. 181); nonlinear model at $\Delta = -25$ mm, $k = 20.8$ N/mm (p. 183); two independent methods agree to four significant digits (p. 183).
- Peak von Mises stress in the spring 278.8 MPa over $-25 < \Delta < 0$ mm, below the 285 MPa yield point, end faces excluded (p. 184).
- Segment model spring rate 18.86 N/mm, 9.45% off the full-spring value, the difference being end constraint modelling (p. 185); Wahl formula gives 19.33 N/mm, 2.5% above 3D elasticity (p. 186).
- $\tau_{max}/\tau_{nom}$: classical 1.134, 3D finite element 1.164, difference 2.6% (p. 186).

## Definitions introduced
- Mathematical model - all mathematical operations, deterministic or probabilistic, needed to predict the QoIs (p. 155).
- Numerical simulation - solution of a precisely formulated mathematical problem with the error $|\mathbf{F}-\mathbf{F}_{num}|$ estimated and controlled (p. 159).
- Finite element modelling - intuitive construction of a numerical problem by assembling elements from a software library, no stated mathematical model (p. 162).
- Consistency - quantitative measure of how far the exact solution satisfies the discrete problem (footnote, p. 160).
- Stability - well-posedness of the discretised problem: small data changes give small QoI changes (footnote, p. 160).
- Variational crimes - modifying element properties without regard to the underlying variational principle (p. 162).
- Hourglassing - spurious deformation modes with zero strain energy caused by reduced integration (p. 162).
- Calibration - estimating parameters by matching observed data, the functional form assumed correct (p. 163).
- Domain of calibration - the intervals of validity of the calibrated coefficients plus the model's assumption set (p. 163).
- Tuning - adjusting the finite element mesh to match observations; tuned models interpolate near the tuned parameters (p. 164).
- Simulation governance - managerial command and control over all aspects of numerical simulation (p. 164).
- Principal structural element - aircraft element carrying flight, ground or pressurisation loads whose integrity is essential (footnote, p. 164).
- h-version / p-version - error control by mesh refinement at fixed low $p$, versus raising $p$ on a fixed mesh (p. 166).
- Propping effect - resistance of the fastener shank to ovalisation of the hole (footnote, p. 172).
- Shear joint / tension joint - load carried by fastener shear versus by friction between clamped plates (p. 174).
- Extraction function - a function in the finite element space used to compute a nodal force component (p. 179).
- Hard / soft / semisoft boundary condition - pointwise prescribed displacement, integral-average prescribed, or higher moments set to zero (p. 184).
- Smart application - expert-designed software letting non-analysts explore design options within a parameter space (p. 186).

## Figures and tables to return to
- Fig 5.2 and Fig 5.4 - the paired schematics of numerical simulation and finite element modelling; the chapter's whole contrast in two diagrams (pp. 160, 162).
- Fig 5.5 - FEA timeline, eight milestones from 1956 to 2012 (p. 165).
- Fig 5.6 - Girkmann problem notation, shell and ring geometry (p. 167).
- Table 5.1 - legacy code Girkmann answers, the dispersion exhibit (p. 168).
- Table 5.2 - numerical simulation code answers, mutual agreement to cite against Table 5.1 (p. 169).
- Table 5.3 - classical solutions, Girkmann versus Pitkäranta (p. 170).
- Fig 5.7 - lug problem dimensions and notation, needed to reread any lug result (p. 170).
- Tables 5.4 to 5.7 - fastener forces under Models 1 to 4; read as a set to see model form error move the answers (pp. 171-174).
- Table 5.8 - force redistribution from a 0.025 mm gap at one fastener (p. 175).
- Fig 5.11 - average displacement versus degrees of freedom; how logarithmic divergence hides between two converged models (p. 177).
- Table 5.10 - peak stress versus strain at a point under point constraints; error cancellation is QoI dependent (p. 178).
- Table 5.12 - spring stress resultants at the $\theta = 5\pi$ cut converging with $p$; twisting moment and shear dominate (p. 183).
- Table 5.13 - nonlinear spring resultants with mesh and $p$ convergence (p. 184).
- Fig 5.15 and Table 5.14 - segment von Mises contours with Saint-Venant decay, and strain energy converged to seven digits (p. 185).

## Where to find what
| Topic | Pages |
| --- | --- |
| Simulation defined, Pauli on ideas of reality | 155 |
| Model as transformation $(\mathbf{D},\mathbf{I})\to\mathbf{F}$; "physics-based model" ill defined | 156 |
| Bernoulli-Euler beam formulation, three steps | 156-157 |
| Beam model history, Galileo to Eiffel | 158-159 |
| Range of validity of the beam model | 159 |
| Numerical simulation defined, error sources, calibration domain | 159-160 |
| Consistency and stability; randomness of experimental outcomes | 160 |
| Finite element modelling origins, truss and continuum elements | 160-162 |
| Element libraries, reduced integration, hourglassing, variational crimes | 162 |
| Error cancellation in FE modelling practice | 162-163 |
| Truss element stiffness matrix (Exercises 5.1, 5.2) | 163 |
| Calibration versus tuning | 163-164 |
| Simulation governance | 164, 167 |
| Milestones in numerical simulation, timeline | 165-167 |
| h-version, p-version, hierarchic models, ASME V&V guideline | 166-167 |
| Girkmann problem statement and data | 167-168 |
| Girkmann results: legacy, verified, classical | 168-170 |
| Structural versus strength analysis idealisation (Remark 5.4) | 170 |
| Lug problem statement and data | 170 |
| Model 1: rigid lug, surrogate problem for peak stress | 171-172 |
| Model 2: linear fastener springs | 172 |
| Model 3: compression-only springs, iteration | 173 |
| Model 4: 3D frictionless contact | 173-174 |
| Model comparison, minimum complexity, parsimony | 174-175 |
| Gaps and interference, quality of fit (Example 5.1) | 175 |
| Point-constrained FE model, divergence of displacement | 176-177 |
| Spring rate definitions doomed under point constraints (Remark 5.8) | 177 |
| Equilibrium of nodal forces, proof and remarks | 178-179 |
| Why FE modelling predictions can still match experiment | 179-180 |
| Coil spring problem, linear solution, spring rate | 180-182 |
| Stress resultants by cutting the coil; extraction | 182-183 |
| Nonlinear spring solution, stopping criterion | 183-184 |
| Hard, soft, semisoft boundary conditions | 184 |
| Coil spring segment, Wahl formulas, smart apps | 184-186 |

## Links
[[Verification and validation]], [[Model form error]], [[Calibration]], [[Finite element method]], [[p-version FEM]], [[Girkmann problem]], [[Bernoulli-Euler beam]], [[Saint-Venant's principle]], [[Contact mechanics]], [[Simulation governance]], [[Coil spring]]

## Flags
- Suspected erratum, p. 173: peak principal stress change under a 10% spring rate cut is quoted as "0.1 N (0.04%)"; the unit should read MPa.
- Inconsistency: Model 4 peak stress is 287.4 MPa on p. 174 but 288.9 MPa on p. 175.
- Table 5.10 (p. 178) is headed "(ksi)" yet its Model 3 entry (254.7) matches the MPa value on p. 173; read the table in MPa.
- Element count for the spring mesh: 9,691 on p. 181, 9,695 on p. 183.
- Table 5.11 (p. 181): the $p = 2$ entry for $N$ prints as "58,67", digits missing; Table 5.12 has $N = 58{,}785$ at $p = 2$.
- p. 183 refers to "Table 2" where Table 5.13 is meant.
- Continues in the next slice (Chapter 6, from p. 187): calibration, validation and ranking of models; the statistical sub-model for high cycle fatigue failure probability is promised there (pp. 156, 160, 163).
- The lug hand calculation rests on Appendix J (eqs J.14, J.15) and the spring segment on Appendix K (Fig K.4), both outside this slice.
