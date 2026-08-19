---
source: Finite Element Analysis: Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 255-264
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
Chapter 8 shows how to get the macromechanical properties of a unidirectional fibre-matrix lamina from the properties of fibre and matrix alone. The tool is the representative volume element (RVE) with an idealised hexagonal or square fibre pattern: solve six displacement boundary value problems on the RVE, read off the stiffness constants from strain energies, and a seventh problem with a temperature change gives the thermal expansion coefficients. Worked examples verify that the results barely change when one RVE is replaced by 8 or 27, quantify the error of assuming transverse isotropy, and compare against rule of mixtures values. The chapter then reverses direction: localisation recovers the microscale solution from the macroscopic strain, and a failure prediction example demonstrates that the pointwise maximum equivalent strain diverges under p-extension while its integral average over the matrix phase converges, so only averaged quantities qualify as failure predictors. A closing section grounds the idealisation: real volume fractions scatter widely, and predictors must be calibrated against that uncertainty.

## Key ideas
- An RVE is a sample of a heterogeneous material carrying its average physical properties (p. 255).
- The macroscopic stiffness $[E_{\text{RVE}}]$ is defined by equating the strain energy of the heterogeneous RVE with that of the homogenised RVE (p. 255).
- The algorithm rests on strain energy and boundary-averaged displacements, both superconvergent (faster than the energy norm) (p. 255).
- Five planes of symmetry reduce $[E_{\text{RVE}}]$ to six constants $A, B, C, D, e, f$ (p. 256).
- Six problems with "sym" and "float" boundary conditions determine the constants; these are periodic boundary conditions with the minimum number of constraints per deformation mode (p. 256).
- Elements of $[E_{\text{RVE}}]$ must be substantially independent of the number of RVEs used; the examples confirm this (pp. 255, 259-260).
- Transverse isotropy is justified only for the regular hexagonal arrangement, $b/a = \sqrt{3}$; the usual assumption is not automatic (Remark 8.1, pp. 258-259).
- Assuming transverse isotropy underestimates $G_T$ by 18.7 % for the $b/a=1$ hexagonal pattern and misses by 23 % for the square pattern (p. 260).
- Rule of mixtures and modified rule of mixtures give a reasonable approximation to the computed properties (p. 261).
- Localisation: the macroscopic strain is nearly constant over one RVE, so average strains define displacement boundary conditions for the microscale problem; use at least 8 RVEs to keep boundary perturbations away from the region of interest (p. 261).
- If the exact macroscopic solution has points of infinite strain, the maximum norm error of the computed strain is infinite; maximum strain cannot be the goal of computation (Remark 8.2, p. 261).
- Detectable failure events in fibre-reinforced composites occur on the scale of one or more RVEs; predictors are integral averages on solution-dependent domains, analogous to the fatigue predictors of Section 6.3, and require VVUQ (p. 262).
- Elastic strains are unbounded at fibre terminations; $\max(\epsilon_{\text{eq}})$ diverges under p-extension, visible only past $p=6$, while the average over the matrix phase of one RVE converges strongly (pp. 262-263).
- Low $N$ data sit in the pre-asymptotic range; extrapolation to $N \to \infty$ is justified only for high $N$, and what counts as high is problem-dependent (p. 263).
- The integral average meets the predictor requirements: finite, insensitive to small perturbations in the domain, and calibratable from coupon experiments (p. 263).
- The perfectly regular fibre arrangement is an idealisation; dominant uncertainties are volume fraction variation and fibre waviness (p. 263).
- Predictor evaluation and ranking follow the model development process of Section 6.5; simulation governance frames their improvement over time (p. 264).

## Equations that matter
$$\{\bar{\sigma}\} = [E_{\text{RVE}}]\{\bar{\epsilon}\} \tag{8.3}$$
Macroscopic stress-strain law between integral averages over the RVE (p. 255).

$$U = \frac{1}{2}\int_V \{\epsilon\}^T [E] \{\epsilon\}\, dV = \frac{1}{2}\{\bar{\epsilon}\}^T [E_{\text{RVE}}] \{\bar{\epsilon}\}\, V \tag{8.4}$$
Energy equivalence that defines the homogenised stiffness matrix (p. 255).

$$\left(\bar{\epsilon}_x^2 + \bar{\epsilon}_y^2\right)_k A + \left(\bar{\epsilon}_z^2\right)_k B + 2\left(\bar{\epsilon}_x \bar{\epsilon}_y\right)_k e + 2\left(\bar{\epsilon}_y \bar{\epsilon}_z + \bar{\epsilon}_z \bar{\epsilon}_x\right)_k f = 2U_k/V \tag{8.7}$$
Four equations ($k = 1,\dots,4$, the problems of Table 8.1) for the constants $A, B, e, f$ from computed strain energies (p. 257).

$$C = 2U_5/(\bar{\gamma}_{xy}^2 V), \qquad D = 2U_6/(\bar{\gamma}_{yz}^2 V) \tag{8.8}$$
Shear constants from the two shear problems (p. 257).

$$\frac{\nu_{TL}}{E_T} = \frac{\nu_{LT}}{E_L} \tag{8.10}$$
Symmetry condition on $[C_{\text{RVE}}]$; the two Poisson ratios are not independent (p. 258).

$$G_T = \frac{E_T}{2(1+\nu_T)} \tag{8.11}$$
Holds only if the material is transversely isotropic; used to size the error of assuming it (p. 258).

$$\alpha_X = \bar{u}_x^{+}/(a\mathcal{T}), \quad \alpha_Y = \bar{u}_y^{+}/(b\mathcal{T}), \quad \alpha_Z \equiv \alpha_L = \bar{u}_z^{+}/(c\mathcal{T}) \tag{8.12}$$
Thermal expansion coefficients from average boundary displacements under a constant temperature change $\mathcal{T}$ (p. 258).

$$\bar{u}_x = \bar{\epsilon}_x x + \bar{\gamma}_{xy} y/2 + \bar{\gamma}_{zx} z/2, \quad \bar{u}_y = \bar{\gamma}_{xy} x/2 + \bar{\epsilon}_y y + \bar{\gamma}_{yz} z/2, \quad \bar{u}_z = \bar{\gamma}_{zx} x/2 + \bar{\gamma}_{yz} y/2 + \bar{\epsilon}_z z \tag{8.13}$$
Displacement field built from average strains; supplies the boundary conditions for localisation (p. 261).

$$\epsilon_{\text{eq}} = \sqrt{\frac{1}{2(1+\nu)^2}\left[(\epsilon_1-\epsilon_2)^2 + (\epsilon_2-\epsilon_3)^2 + (\epsilon_3-\epsilon_1)^2\right]} \tag{8.14}$$
Equivalent strain in the matrix; under uniaxial loading $\sigma_{\text{eq}} = E\,\epsilon_{\text{eq}}$ with $\sigma_{\text{eq}}$ the von Mises stress (p. 262).

## Numbers worth citing
- Example fibres: diameter 7 $\mu$m, volume fraction $V_f = 60$ %, transversely isotropic with $E_L = 2.52 \times 10^5$ MPa, $E_T = 1.65 \times 10^4$ MPa, $\nu_{LT} = 0.3$, $\nu_T = 0.2$, $G_{LT} = 4.14 \times 10^4$ MPa, $\alpha_L = -1.08 \times 10^{-6}$ /°C, $\alpha_T = 7.2 \times 10^{-6}$ /°C (p. 258).
- Example matrix: isotropic, $E = 3.79 \times 10^3$ MPa, $\nu = 0.3$, $\alpha = 5.4 \times 10^{-5}$ /°C; properties from reference [110], converted to SI (p. 258).
- Verification of all computed quantities: p-extension from 5 to 8 with limit estimation (p. 258).
- Hexagonal RVE dimensions: $a = b = c = 1.132615 \times 10^{-2}$ mm (p. 259).
- Hexagonal pattern, one RVE: $E_L = 1.5272 \times 10^5$ MPa, $E_T = 7.9143 \times 10^3$ MPa, $G_{LT} = 5.3708 \times 10^3$ MPa, $G_T = 3.5579 \times 10^3$ MPa, $\nu_{LT} = 0.300$, $\nu_T = 0.368$, $\alpha_L = -5.3323 \times 10^{-7}$ /°C, $\alpha_T = 2.8941 \times 10^{-5}$ /°C; largest one-vs-27-RVE difference is 1.23 % in $G_{LT}$ (Table 8.3, p. 259).
- Transverse isotropy applied to this hexagonal pattern gives $G_T = 2.8931 \times 10^3$ MPa, an 18.7 % underestimate (p. 260).
- Square RVE dimensions: $a = b = c = 8.0088 \times 10^{-3}$ mm (p. 260).
- Square pattern, one RVE: $E_L = 1.5272 \times 10^5$ MPa, $E_T = 9.0737 \times 10^3$ MPa, $G_{LT} = 5.4639 \times 10^3$ MPa, $G_T = 2.8932 \times 10^3$ MPa, $\nu_{LT} = 0.300$, $\nu_T = 0.27513$; one-vs-8-RVE differences at most 0.24 % (Table 8.4, p. 260).
- Transverse isotropy applied to the square pattern gives $G_T = 3.5583 \times 10^3$ MPa, off by 23 % (p. 260).
- Localisation example domain: 8 RVEs, $\ell_x = \ell_y = \ell_z = 1.6018 \times 10^{-2}$ mm, 128 elements, imposed $\bar{\epsilon}_x = 3.5 \times 10^{-3}$, $\bar{\epsilon}_y = -2.0 \times 10^{-3}$, $\bar{\gamma}_{xy} = 0$ (p. 262).
- Measured volume fraction in a plate fabricated under controlled laboratory conditions: raw range 9.5 % to 79.5 %; after smoothing, average 59.1 % with range 43.8 % to 69.5 %; lowest between plies (reference [11], p. 263).

## Definitions introduced
- Representative volume element (RVE) - sample of a heterogeneous material that has its average physical properties (p. 255).
- Floating symmetry ("float") - normal displacement is a constant, chosen so the area integral of the normal stress is zero (p. 256).
- Macroscopic compliance matrix - $[C_{\text{RVE}}] = [E_{\text{RVE}}]^{-1}$, relating average strain to average stress (p. 257).
- Transversely isotropic - material whose $[C_{\text{RVE}}]$ is computable from five constants (p. 258).
- Localisation - interpretation of the macroscopic solution on the scale of RVEs (p. 261).
- Equivalent strain - scalar strain measure matching the von Mises stress under uniaxial loading (p. 262).

## Figures and tables to return to
- Fig 8.1 - the two RVE geometries (hexagonal, square) and the dimension notation $a, b, c$ used throughout (p. 256).
- Table 8.1 - the six displacement boundary condition sets that generate the stiffness constants (p. 257).
- Table 8.2 - boundary conditions for the thermal expansion problem, $k = 7$ (p. 258).
- Fig 8.2 - 27-RVE solution domain, 864 elements, used for the size independence check (p. 259).
- Table 8.3 - hexagonal pattern properties, one RVE vs 27 (p. 259).
- Fig 8.3 - 8-RVE square-pattern domain (128 elements) with the region of interest marked, and the deformed shape under transverse shear showing periodicity (p. 260).
- Table 8.4 - square pattern properties, one RVE vs 8 (p. 260).
- Table 8.5 - hexagonal and square results against rule of mixtures and modified rule of mixtures, in psi (p. 261).
- Table 8.6 - displacement boundary conditions for localisation, built from eq. (8.13) (p. 262).
- Table 8.7 - boundary conditions for the failure prediction example (p. 262).
- Fig 8.4 - max vs RVE-averaged equivalent strain against degrees of freedom; the divergence of the maximum is the point of the whole example (p. 263).

## Where to find what
| Topic | Pages |
|---|---|
| RVE definition, homogenisation goal | 255 |
| $[E_{\text{RVE}}]$ by energy equivalence | 255-256 |
| Symmetry, six constants, boundary condition problems | 256-257 |
| Constants from strain energies | 257 |
| Compliance matrix, engineering constants | 257-258 |
| Transverse isotropy condition and caveat | 258-259 |
| Thermal expansion coefficients | 258 |
| Example constituent properties | 258 |
| Hexagonal pattern results, size independence | 259-260 |
| Square pattern results | 260 |
| Error of assuming transverse isotropy | 260 |
| Comparison with rule of mixtures | 261 |
| Localisation | 261-262 |
| Failure prediction, predictor requirements | 262-263 |
| Divergence of maximum equivalent strain | 262-263 |
| Uncertainties in volume fraction and waviness | 263 |
| Discussion, simulation governance | 264 |

## Links
[[Homogenisation]], [[Representative volume element]], [[Composite laminae]], [[Transverse isotropy]], [[Rule of mixtures]], [[p-version finite elements]], [[Failure predictors]], [[Verification and validation]], [[Simulation governance]]

## Flags
- Self-contained chapter: nothing continues into Chapter 9 (non-linear models, from p. 265). The predictor discussion points backwards, to Sections 6.3 and 6.5, not forwards.
- The refined-mesh confirmation of the $\max(\epsilon_{\text{eq}})$ divergence is claimed but not shown (footnote 2, p. 263).
- Table 8.3 shows a 1.23 % one-vs-27-RVE difference in $G_{LT}$ while all other entries differ by 0.05 % or less; the text still calls the results "virtually independent" of RVE count (p. 259).
- The book spells fiber; this note uses fibre.
- All assigned pages read; none unreadable.
