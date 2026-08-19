---
source: Finite Element Analysis. Method, Verification and Validation, 2nd edition, Barna Szabó and Ivo Babuška, Wiley 2021
pages: 187-222
extracted: 2026-08-19
tags: [extract]
---

## In one paragraph
The chapter is the book's worked demonstration of validation, using one classical problem throughout: predicting fatigue failure of aluminium alloy components in the high cycle regime. The mathematical model has three sub-models, a linear elasticity problem, a predictor of fatigue failure defined on the elastic stress field, and a statistical model, and the chapter walks the full life cycle: collect notch-free S-N data, fit a random fatigue limit model, test the classical Peterson and Neuber notch predictors against notched-specimen data (both fail as stated, both are rescued by recalibration), formulate a competing integral-average predictor, rank the candidates by likelihood, extend validation to biaxial in-phase and out-of-phase loading, and quantify confidence in predictive performance by Bayesian updating. It closes with the management view: model development is open-ended, a model is validated only within its domain of calibration, and it is rejected only when a better model is found.

## Key ideas
- The fatigue model comprises three sub-models: linear elasticity, a predictor defined on elastic stress fields, and a statistical model (p. 187).
- All computed quantities of interest were verified so numerical error is negligible against experimental uncertainty; validation then tests the model, not the numerics (p. 187).
- Predictors treat elastic stresses as averages over representative volume elements; small plastic zones are admitted provided the surrounding elastic field controls them (p. 191).
- The S-N median calibrated on notch-free coupons underestimates the fatigue limit of notched specimens where the stress gradient is steep (p. 190).
- Calibration trains the predictor to match the calibration data; a calibrated predictor is a validated predictor only within the domain of calibration (p. 194, 197).
- Peterson's parameter $a$ is not a material constant: its coefficient of variation across six specimen types is 141%, so his formula (and Neuber's) is rejected in its original form (p. 194).
- $\log_{10}a$ against $\log_{10}r$ is nearly linear, so a two-parameter power law replaces the supposed material constant (p. 194).
- Validation tests the hypothesis that notched fatigue data come from the same population as the notch-free S-N data, by placing the empirical CDF against predicted 0.05 and 0.95 quantiles (p. 195-196).
- No yes/no verdict is offered: without a pre-declared tolerance the outcome is either "reject" or "no reason to reject" (p. 201).
- After validation, the validation set is merged into the calibration set and parameters are re-estimated; the likelihood ratio measures the gain (p. 197-198).
- Runouts cannot be reliably predicted; a runout is recorded whenever a test stops before failure for any reason (p. 197).
- Prediction of low probability events (fatigue limit at 99% survival) is extrapolation even inside the domain of calibration, because calibration data have high probability of occurrence; validating statistical models for fatigue limit prediction is not feasible (p. 201).
- $G_\alpha$ averages a convex combination of the first stress invariant and the von Mises stress over the highly stressed volume, so stress raisers need not be characterised by a notch radius (p. 202-203).
- Models are ranked by the log likelihood function given the available data; among $\alpha \in [0,1]$ the maximum is at $\alpha = 0$ (p. 204-205).
- $G_\alpha$ with $\alpha = 0$ outranks Peterson's updated predictor and holds a larger domain of calibration (p. 205, 210).
- The plastic-volume fraction $\eta$ delimits the domain of calibration for the biaxial tests; a threshold near 10% is consistent with the data (p. 208-209).
- Two extensions to out-of-phase loading both pass validation; their likelihood ratio of 1.86 lies inside $(1/3, 3)$, a virtual tie (p. 213-214).
- Predictive performance (fraction of outcomes inside the predicted 90% interval) is assessed by Bayes' theorem with a conjugate Beta prior; the credible interval shrinks as $1/\sqrt{m}$ (p. 214-218).
- Proper validation experiments need at least one admissible parameter outside the domain of calibration, or more general conditions than the calibration experiments (p. 217).
- Model development runs formulation, calibration, prediction, validation, disposition; managing it is simulation governance (p. 219).
- A mathematical model is not rejected until a better model is found; justification is by negation (p. 219-220).
- "Physics-based model" is argued to be an empty notion: a mathematical model is a precise statement of an idea about some aspects of reality and nothing more (p. 220).

## Equations that matter
$$\sigma_{\mathrm{eq}} = \sigma_{\max}\left(\frac{1-R}{2}\right)^{c} \tag{6.5}$$
Equivalent stress for uniaxial cycling; the chapter fixes $c = 1/2$ (p. 189).

$$\mu(\sigma_{\mathrm{eq}}) = A_1 - A_2\log_{10}(\sigma_{\mathrm{eq}} - A_3), \quad \sigma_{\mathrm{eq}} - A_3 > 0 \tag{6.7}$$
Mean (and median) of $\log_{10}n$ in the random fatigue limit model; $A_3$ is the fatigue limit, itself a random variable (p. 189).

$$K_f = 1 + q(K_t - 1) \tag{6.10}$$
Fatigue stress concentration factor from the elastic factor $K_t$ via the notch sensitivity $q$ (p. 191).

$$q = \frac{1}{1 + a/r} \tag{6.11}$$
Peterson's notch sensitivity; $a$ was assumed a material constant, $r$ is the notch radius (p. 192).

$$q_N = \frac{1}{1 + f(\omega)\sqrt{A/r}}, \quad f(\omega) = \frac{\pi}{\pi - \omega} \tag{6.12}$$
Neuber's notch sensitivity; $\omega$ is the notch flank angle, $A$ a material parameter (p. 192).

$$q_{\mathrm{rev}} = \frac{1}{1 + 0.6817\, r^{-0.1610}}, \quad 0.02 < r < 1.5 \tag{6.21}$$
Peterson revised for 24S-T3 aluminium after calibration on six specimen types; $r$ in inches (p. 194).

$$q_{\mathrm{upd}} = \frac{1}{1 + 0.6798\, r^{-0.1791}}, \quad 0.003 < r < 1.5 \tag{6.25}$$
Updated form after merging the validation set into the calibration set, nine specimen types (p. 197).

$$G_\alpha(\sigma_{ij}, R) = \frac{1}{V_c}\int_{\Omega_c}\left(\alpha I_1 + (1-\alpha)\bar{\sigma}\right)\,dV \left(\frac{1-R}{2}\right)^{1/2} \tag{6.26}$$
Integral-average predictor over $\Omega_c = \{\mathbf{x} \mid \sigma_1 > \beta\sigma_{\max} > 0\}$; reduces to $\sigma_{\mathrm{eq}}$ for constant uniaxial stress (p. 202).

$$S(N) = 1 - \Phi_M(N \mid G_\alpha) \tag{6.37}$$
Survival function from the marginal CDF of the random fatigue limit model; sets the predicted interval $N_1$ (5%) to $N_2$ (95%) (p. 207).

$$\eta \; \overset{\mathrm{def}}{=} \; V_{\mathrm{yld}}/V_c \tag{6.38}$$
Plastic zone volume over integration volume; delimits the domain of calibration (p. 208).

$$(G_\alpha)_{\mathrm{eff}} = \kappa\,(G_\alpha)_{\mathrm{axl}}\,\frac{A_2}{A_1} \tag{6.44}$$
Extension A for out-of-phase biaxial loading; $A_1, A_2$ are half-cycle areas under the first principal stress, $\kappa$ calibrated (p. 212).

$$(G_{\alpha,p})_{\mathrm{eff}} = \left((G_\alpha)_{\mathrm{axl}}^{\,p} + (G_\alpha)_{\mathrm{tor}}^{\,p}\right)^{1/p}, \quad p \ge 1 \tag{6.49}$$
Extension B; $p = 2$ adopted rather than calibrated, given only three test records (p. 213).

$$Pr(\theta \mid D) = C\,\theta^{\,n+\alpha-1}(1-\theta)^{\,m-n+\beta-1} \tag{6.54}$$
Posterior for the pass fraction $\theta$: binomial likelihood with conjugate Beta prior, $n$ successes in $m$ trials (p. 215).

$$CI \approx 1.123\, m^{-0.4907} \tag{6.60}$$
Width of the minimum 95% credible interval against number of experiments, ideal data with $\theta_0 = 0.9$; consistent with $1/\sqrt{m}$ (p. 218).

## Numbers worth citing
- High cycle regime: more than $10^4$ cycles (p. 187).
- Qualified S-N range used for calibration: $8500 < n_f < 10^7$ cycles, notched 24S-T3 records; failures below 8500 cycles excluded (p. 193).
- Disqualified record: $\sigma_{\max} = 247.8$ ksi against yield near 54 ksi, plastic strains of order 5%, outside Peterson's scope (p. 193).
- Coefficient of variation of Peterson's $a$ across six specimen types: 141% (p. 194).
- $\log_{10}a$ vs $\log_{10}r$ fit: $R^2 = 0.979$ for both the six-point and nine-point fits (p. 194, 197).
- Likelihood ratios: $L_{\mathrm{upd}}/L_{\mathrm{rev}} = 13.8$ ($LL_{\mathrm{upd}} = -2534.440$, $LL_{\mathrm{rev}} = -2537.068$); $LL_{\mathrm{Pet}} = -3463.283$ with Peterson's handbook $a = 0.02$ in; $LL_{\mathrm{Neu}} = -2971.704$ with Neuber's $A = 0.018$ in interpolated at ultimate tensile strength 73 ksi (p. 198-199).
- Mean random fatigue limit, notch-free 24S-T3: $10^{1.344} = 22.08$ ksi (p. 200).
- Aluminum Association fatigue strength of 2024-T3: 20 ksi (138 MPa) at $5\times10^8$ fully reversed cycles; the random fatigue limit model puts failure probability below $5\times10^8$ cycles at 17% for $\sigma_{\mathrm{eq}} = 20$ ksi, outside its calibrated range of $10^7$ cycles (p. 200-201).
- Maximum $\sigma_{\mathrm{eq}}$ for 99% survival at $10^7$ fully reversed cycles: 18.2 ksi (p. 201).
- $G_\alpha$ calibration at $\alpha = 0$: $\bar{\beta} = 0.9422 + 0.08184\,\log_{10}V$, valid for $10^{-8} < V < 10^{-2}$ in³ of highly stressed volume (p. 203).
- Highly stressed volume threshold $\gamma = 0.85$; predicted cycle count insensitive to the choice (p. 203).
- Relative errors of all numerically computed data verified below 1% (p. 204).
- Log likelihood vs $\alpha$: $-2487.33$ at $\alpha = 0$ falling to $-2634.26$ at $\alpha = 1$; $G_\alpha(\alpha = 0)$ at $-2487.33$ beats Peterson updated at $-2534.44$ (p. 205).
- Tubular biaxial specimens (ASTM E2207, 2024-T3): 30 mm cylindrical test section, outside diameter 29 mm, inside diameter 25.4 mm, wall 1.8 mm, transverse hole 3.2 mm diameter; load control at 0.2 to 7.0 Hz, $R = -1$; crack initiation defined as first 0.2 mm surface crack (p. 206).
- Example 6.2: 81 MPa axial with 50 MPa shear in-phase gives $G_\alpha(\alpha = 0) = 31.6$ ksi (218 MPa); predicted 90% interval 77,000 to 671,000 cycles; observed failures at 130,000 and 302,000 cycles (p. 207-208).
- $\eta_{\lim}$: at 0.15, 10 of 11 qualified biaxial records pass; below 0.08, all 7 remaining pass; tentative threshold 10% (p. 209).
- Extension A calibration: $\kappa = 0.8680$, updated to $0.8840$ after adding the validation record (p. 212-213).
- Extension ranking: $L_A/L_B = 1.86$, inside the virtual-tie interval $(1/3, 3)$ (p. 214).
- Three passes in three trials: $\theta_0 = 1$, shortest 95% credible interval $(0.473, 1)$, expected value $\theta_M = 0.80$ (p. 216).
- Cumulative 11 passes in 12 trials: $\theta_0 = 0.917$, 95% credible interval $(0.681, 0.995)$ (p. 217).
- Highly stressed volumes in biaxial validation: $7.28\times10^{-6}$ in³ (axial), $4.29\times10^{-6}$ in³ (torsion), both inside the calibration domain (p. 218).
- Over 100 experiments needed to shrink the minimum 95% credible interval to 0.1 at $\theta_0 = 0.9$ (p. 218).
- Crack initiation taken to consume nearly all of coupon life; checked by crack growth rates for a 0.05 in (1.3 mm) crack in 2024-T3 sheet (p. 190).

## Definitions introduced
- Cycle ratio - $R = \sigma_{\min}/\sigma_{\max}$ of the principal stress (p. 188).
- Equivalent stress - member of the family $\sigma_{\mathrm{eq}} = \sigma_{\max}^{1-c}\sigma_a^c$, $0 < c < 1$; definition not unique (p. 188-189).
- S-N data - records $(n_i, \sigma_{\mathrm{eq}}^{(i)})$ from tests where the first principal stress in the test section is constant or has small gradient (p. 189).
- Random fatigue limit model - $\log_{10}n$ normal with mean per eq. 6.7 and constant standard deviation; $\log_{10}A_3$ normal with mean $\mu_f$, standard deviation $s_f$ (p. 189).
- Fatigue limit (endurance limit) - parameter $A_3$, treated as a random variable (p. 189).
- Stress concentration factor - $K_t = \sigma_{\max}/\sigma_{\mathrm{ref}}$ (p. 190).
- Fatigue stress concentration factor $K_f$ - notch-free fatigue limit divided by notched fatigue limit; also usable above the fatigue limit (p. 191).
- Representative volume element - smallest volume over which averaged material properties match the whole (p. 191).
- Notch sensitivity factor $q$ - factor relating $K_f$ to $K_t$; Peterson and Neuber defined it differently (p. 192).
- Runout - test stopped before failure for any reason (p. 188, 197).
- Coefficient of variation - standard deviation over absolute mean (p. 194).
- Highly stressed volume $V$ - volume where $\sigma_1 > \gamma\sigma_{\max}$, characterising stress raisers without a notch radius (p. 203).
- Qualified test records - records satisfying the assumptions on which the model formulation rests, here $\eta < \eta_{\lim}$ (p. 209).
- Domain of calibration - subset of admissible parameters on which the model was calibrated; essential attribute of a model (p. 208, 217).
- Conjugate prior - prior with the same functional form as the posterior, simplifying updates (p. 215).
- Uninformative, informative, weakly informative priors - expressing ignorance, definite information, or partial information about a variable (p. 215).
- Credible interval - shortest interval holding 95% posterior probability (p. 216).

## Figures and tables to return to
- Fig 6.1 - notch-free coupon geometry, dimensions in inches, thickness 0.090 in (p. 188).
- Fig 6.2 - nine notched specimen types plotted against the notch-free-calibrated median: the mismatch that motivates the chapter (p. 191).
- Fig 6.3 - near-linear $\log_{10}a$ vs $\log_{10}r$, the basis of the revised Peterson formula (p. 195).
- Fig 6.4 - empirical vs predicted CDF, edge notch $r = 0.760$ in, validation inside quantiles (p. 196).
- Fig 6.5 - same for $r = 0.0035$ in, well outside the calibration interval of notch radii (p. 198).
- Fig 6.6 - nine specimen types collapsed by $\sigma'_{\mathrm{eq}}$; compare against Fig 6.2 for the improvement (p. 199).
- Fig 6.7 - $q$ vs $r$ for Peterson, Neuber, revised and updated formulas; the originals sit far above (p. 200).
- Fig 6.8 - $\beta_k$ against highly stressed volume with the fitted $\bar{\beta}$ line, $\alpha = 0$ (p. 204).
- Fig 6.9 - combined qualified records under $G_\alpha(\alpha = 0)$; the cleanest collapse in the chapter (p. 206).
- Fig 6.11 and 6.12 - biaxial outcomes and the survival function used to state a prediction interval (p. 207-208).
- Fig 6.13 - nominal first principal stress histories for axial, torsion and combined out-of-phase loading; source of the area ratio in Extension A (p. 211).
- Fig 6.14 to 6.16 - posterior pdfs for 3/3 passes, the 11/12 update, and convergence with $m$ (p. 216-218).
- Fig 6.17 - schematic of the whole validation process, formulation through disposition (p. 219).
- Table 6.1 - Peterson calibration results for six specimen types: $r_k$, $K_t$, $x_k$, $q_k$, $a_k$ (p. 193).
- Table 6.2 - the three added specimen types after validation (p. 198).
- Table 6.3 - fatigue limit values: random fatigue limit model vs Peterson vs Neuber, nine specimen types (p. 200).
- Table 6.4 - $V_k$, $\beta_k$, $\bar{\beta}_k$, $\bar{x}_k$ for $\alpha = 0$ (p. 204).
- Table 6.5 - log likelihood against $\alpha$, the ranking evidence (p. 205).
- Table 6.6 - 13 biaxial validation records with survival probabilities and $\eta$ values (p. 209).
- Tables 6.7 to 6.10 - out-of-phase test data, calibration and validation outcomes for Extensions A and B (p. 210-213).
- Table 6.11 - log likelihood values for predictors A and B (p. 214).
- Table 6.12 - credible interval width vs number of experiments (p. 218).

## Where to find what
| Topic | Pages |
|---|---|
| Chapter scope, three sub-models, verification stance | 187 |
| Fatigue data, cycle ratio, sinusoidal stress field, test records | 187-188 |
| Equivalent stress family, S-N data | 188-189 |
| Random fatigue limit statistical model | 189-190 |
| Effect of notches, $K_t$, RVE argument | 190-191 |
| Predictor formulation philosophy | 190-191 |
| Peterson and Neuber notch sensitivity, stress averaging remark | 191-192 |
| Calibration of Peterson's $a$, qualified records, rejection of material constant | 193-194 |
| Revised formula $q_{\mathrm{rev}}$, least squares as maximum likelihood | 194-195 |
| Validation against notched data, CDF comparisons | 195-197 |
| Updated calibration $q_{\mathrm{upd}}$, likelihood ratios vs Peterson and Neuber | 197-199 |
| Fatigue limit comparison, AA fatigue strength example | 199-201 |
| Discussion: no tolerance, reject or no-reason-to-reject, Hume | 201-202 |
| Predictor $G_\alpha$, highly stressed volume | 202-203 |
| Calibration of $\beta(V, \alpha)$ | 203-204 |
| Ranking over $\alpha$, comparison with Peterson updated | 204-205 |
| Biaxial specimens and test programme | 205-206 |
| In-phase axial, torsion, combined validation; survival function | 206-208 |
| Domain of calibration, $\eta$ restriction, qualified records | 208-210 |
| Out-of-phase loading, Extensions A and B, ranking | 210-214 |
| Bayesian predictive performance, priors, credible intervals | 214-217 |
| Updated domain of calibration, number of experiments | 217-218 |
| Management of model development, simulation governance | 218-220 |
| Obstacles: fuzzy terminology, empty notions, Hawking and Popper | 220-221 |

## Links
[[High cycle fatigue]], [[S-N curve]], [[Notch sensitivity]], [[Stress concentration]], [[Random fatigue limit model]], [[Model calibration]], [[Model validation]], [[Maximum likelihood]], [[Bayesian inference]], [[Likelihood ratio]], [[Simulation governance]], [[Linear elasticity]], [[Representative volume element]], [[Verification and validation]]

## Flags
- Table 6.8 caption reads "calibration of Model B" but its columns ($A_1$, $A_2$) belong to Extension A; suspected erratum (p. 212).
- Fig 6.3 caption names the alloy "24S-T3 (7024-T3)"; elsewhere the chapter equates 24S-T3 with 2024-T3, so 7024-T3 looks like an erratum for 7024/2024 (p. 195, cf. p. 190, 200).
- Table 6.3, specimen $k = 9$ ($r = 0.0035$ in): Peterson's value 7.48 ksi sits below the RFL value 10.90 ksi, against the stated pattern that Peterson and Neuber overestimate; the radius is far outside the original calibration data (p. 200).
- The chapter leans on Appendix I throughout: data Tables I.2 and I.5, marginal pdf and CDF equations I.18 to I.20, and maximum likelihood procedures; that appendix is outside this slice (p. 189-190, 194, 196).
- Simulation governance picks up a thread from Section 5.2.4 in the previous slice (p. 219).
- No fatigue topic continues into Chapter 7 (beams, plates and shells); the chapter is self-contained apart from the Appendix I dependency.
- Book page 222 is blank; all assigned pages read successfully.
