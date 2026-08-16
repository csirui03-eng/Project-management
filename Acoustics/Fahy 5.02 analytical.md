## The setup: 
an unbounded rigid leaf, mass m per unit area, on a distributed suspension (stiffness s, damping r). The suspension stands represent approximation of real panel edge support.![[Pasted image 20260812200942.jpg]]
## Derivation
### Step 1: the three waves

$$p_i = \tilde A_1 e^{j(\omega t - k_1 x)}, \qquad p_r = \tilde B_1 e^{j(\omega t + k_1 x)}, \qquad p_t = \tilde C_2 e^{j(\omega t - k_2 x)}$$

Basic plane wave in air expressions, incident and reflected on the source side, transmitted on the far side. Nothing to unpack, the content is only in the unknown amplitudes.

### Step 2: velocity matching

Setup is the pressure to particle velocity conversion, $u = p/\rho c$ along each wave's travel direction:

$$u_i = \frac{\tilde A_1}{\rho_1 c_1} e^{j(\omega t - k_1 x)}, \qquad u_r = -\frac{\tilde B_1}{\rho_1 c_1} e^{j(\omega t + k_1 x)}$$

The minus sign because the reflected wave travels opposite to the reference frame.

Write out the leaf's harmonic motion and take the time derivative to get leaf velocity too:

$$\xi = \tilde\xi\, e^{j\omega t} \quad\Rightarrow\quad \dot\xi = j\omega\tilde\xi\, e^{j\omega t}$$

We match at $x = 0$, the leaf's plane, so the space exponentials drop to 1 and only the time component has an effect. Every term then shares $e^{j\omega t}$, which cancels.

With everything written as velocity, just make them equal and simplify:

$$\tilde A_1 - \tilde B_1 = j\omega\rho_1 c_1\tilde\xi$$

Same procedure at the right face, except one term on that side, easy:

$$\tilde C_2 = j\omega\rho_2 c_2\tilde\xi$$

Result: every unknown amplitude hangs off leaf motion. Transmitted is purely leaf motion, reflected is leaf motion plus the known incident, $\tilde B_1 = \tilde A_1 - j\omega\rho_1 c_1\tilde\xi$. One degree of freedom left.

### Step 3: split the left field into blocked and radiated parts

With velocity matching complete, step 3 is where we spend the matched terms, that is the point of having them.

Start with the total left side pressure, the two step 1 waves:

$$p^- = p_i + p_r = \tilde A_1 e^{j(\omega t - k_1 x)} + \tilde B_1 e^{j(\omega t + k_1 x)}$$

Substitute the panel constraint from step 2, $\tilde B_1 = \tilde A_1 - j\omega\rho_1 c_1\tilde\xi$, and the realisation lands: a big component of $\tilde B_1$ is actually just $\tilde A_1$.


Regrouping by job gives the named split:

$$p^-(x,t) = \underbrace{2\tilde A_1 \cos k_1 x \, e^{j\omega t}}_{\text{blocked: rigid wall standing wave, known drive } 2\tilde A_1 \text{ at the face}} + \underbrace{-\,j\omega\rho_1 c_1\tilde\xi\, e^{j(\omega t + k_1 x)}}_{\text{radiated: all the wall physics, velocity proportional}}$$

The blocked part contains no $\tilde\xi$ and delivers the known forcing. The radiated part is velocity proportional and will fold into the equation of motion as radiation damping in step 5.

### Step 4: equation of motion of the leaf

The leaf is modelled as a SDOF oscillator. System forces on the left hand side, external forcing, the pressure on left and right faces, on the right hand side.

$$m\ddot\xi + r\dot\xi + s\xi = p(0^-) - p(0^+)$$

- $m\ddot\xi$: inertia of the leaf, per unit area.
- $r\dot\xi$: damping force of the suspension.
- $s\xi$: restoring force of the suspension. Both live in the mount anchoring the leaf, not in the leaf itself, which is rigid and carries only mass.

Apply the time harmonic assumption and do some substitution from the velocity matched results from above:

$$(-\omega^2 m + j\omega r + s)\tilde\xi = 2\tilde A_1 - j\omega\rho_1 c_1\tilde\xi - j\omega\rho_2 c_2\tilde\xi$$

Both radiated loads are proportional to leaf velocity, which is what step 5 folds into the left hand side as radiation damping.

### Steps 5 and 6: fold the fluid loading, name the impedances

Reminder before the algebra: $j$ is the imaginary unit, the engineer's spelling of $i$. Multiplying by $j$ is a 90 degree phase advance, dividing by $j$ is a 90 degree retard, and $1/j = -j$.

From step 4, move the radiated loads left, where they read as added damping:

$$\left[-\omega^2 m + j\omega(r + \rho_1 c_1 + \rho_2 c_2) + s\right]\tilde\xi = 2\tilde A_1$$

The leaf now has two loss channels: heat in the mount ($r$) and sound radiated away by both fluids (radiation damping). Transmission looks like damping from the leaf's seat.

We are not interested in the leaf's displacement amplitude, we want its velocity: impedance is force over velocity, power is force times velocity, and the fluid's own property is the real constant $\rho c$ only in velocity terms. Swap variable:

$$\tilde v = j\omega\tilde\xi \quad\Longrightarrow\quad \tilde\xi = \frac{\tilde v}{j\omega}$$

Substitute and divide the bracket through by $j\omega$, using $1/j = -j$:

$$\frac{-\omega^2 m}{j\omega} = j\omega m, \qquad \frac{s}{j\omega} = -\,\frac{js}{\omega}$$

$$\left[\,j\left(\omega m - \frac{s}{\omega}\right) + (r + \rho_1 c_1 + \rho_2 c_2)\right]\tilde v = 2\tilde A_1$$

The damping terms were already velocity based, so they sit as bare constants. The inertia force ends up 90 degrees ahead of velocity, the spring force 90 degrees behind. Resonance is the imaginary part crossing zero.

Name the two halves by ownership:

$$\tilde z_p = j\left(\omega m - \frac{s}{\omega}\right) + r, \qquad \tilde z_f = \rho_1 c_1 + \rho_2 c_2$$

$\tilde z_p$ is the partition impedance in vacuo, what the leaf and mount present with no fluid anywhere. $\tilde z_f$ is the fluid loading impedance, what the fluids add purely by being there to radiate into, $\rho c$ each at normal incidence. They add due to our earlier velocity matching. 


Governing relation, book Eq (5.12):

$$(\tilde z_p + \tilde z_f)\,\tilde v = 2\tilde A_1$$

One sentence, whole problem: a fluid loaded SDOF oscillator forced by the blocked pressure.

Note on the two impedances:

- $\tilde z_p$ carries both parts: reactance $\omega m - s/\omega$ (mass and spring store energy and return it) and resistance $r$ (the damper dissipates it).
- $\tilde z_f$ is wholly resistive: the radiated wave travels off into an unbounded half space and does not return.

### Step 7: solve for $\tau$

$\tau$ is transmitted power over incident power. Per unit area both faces share the same area, so it is an intensity ratio. Intensity in the general pressure form:

$$I = \frac{|\tilde p|^2}{2\rho c}$$

Set up the fraction, each amplitude over its own fluid:

$$\tau = \frac{I_t}{I_i} = \frac{|\tilde C_2|^2 / 2\rho_2 c_2}{|\tilde A_1|^2 / 2\rho_1 c_1}$$

Substitute the step 6 results, transmitted amplitude from leaf velocity and velocity from the governing relation:

$$\tilde C_2 = \rho_2 c_2\,\tilde v, \qquad \tilde v = \frac{2\tilde A_1}{\tilde z_p + \tilde z_f}$$

The incident amplitude cancels, $\tau$ is a wall property, not a drive property:

$$\tau = \frac{4\rho_1 c_1\,\rho_2 c_2}{|\tilde z_p + \tilde z_f|^2}$$

Still fully general: any partition at normal incidence, whatever impedance it presents. Later sections reuse this form with a different z.

One simplifying step: normalise by $\rho_2 c_2$ (divide top and bottom by its square, one copy cancels the numerator's $\rho_2 c_2$, the other turns $\rho_1 c_1$ into the fluid ratio), and name that ratio:

$$n = \frac{\rho_1 c_1}{\rho_2 c_2}, \qquad \tau = \frac{4n}{\left|\dfrac{\tilde z_p + \tilde z_f}{\rho_2 c_2}\right|^2}$$

First we substitute in the impedance symbolic expressions we have already derived from above for this limp leaf system, magnitude squared as real part squared plus imaginary part squared. Parameters still the raw $m$, $s$, $r$:

$$\tau = \frac{4n}{\left[\dfrac{\omega m - s/\omega}{\rho_2 c_2}\right]^2 + \left[\dfrac{r}{\rho_2 c_2} + n + 1\right]^2}$$

The current form is correct but unfriendly for direct analysis: the system's behaviour over frequency is in there but hidden. We define the panel's first resonant frequency and loss factor and move the equation onto them.

$$\omega_0 = \sqrt{\frac{s}{m}}$$

Loss factor from the energy definition, dissipated per radian over peak stored, the $2\pi$ being the radian conversion (the oscillator's native tick, which keeps $2\pi$ out of all downstream algebra):

$$\eta = \frac{E_d}{2\pi E_s}$$

Stored is the familiar spring potential energy, dissipated is the damper's per cycle work, walked in full in [[Dissipation]]:

$$E_s = \tfrac{1}{2}\,s X^2, \qquad E_d = \pi\,r\,\omega X^2$$

Assemble, freeze at resonance, and swap $s$ through the helper:

$$\eta = \frac{r\,\omega}{s} \;\xrightarrow{\;\omega = \omega_0\;}\; \frac{r}{\omega_0 m} \quad\Rightarrow\quad r = \omega_0 m\,\eta$$

Substitute $r$ into $\tau$. The definition of $\omega_0$ is never subbed in, it stands beside as the map from panel properties to the resonance. Book Eq (5.14):

$$\tau = \frac{4n}{\left[\dfrac{\omega m - s/\omega}{\rho_2 c_2}\right]^2 + \left[\dfrac{\omega_0 m\,\eta}{\rho_2 c_2} + n + 1\right]^2}$$

Every term is a dimensionless impedance measured against the receiving fluid's $\rho c$. The step 8 regimes are one term of this denominator dominating.

### System losses breakdown

$\eta$ was built from the mount damper alone, so it carries the structural loss only. The air's energy removal never entered it: it stands in the final $\tau$ as the radiation resistances, sitting beside the $\eta$ term in the resistance bracket:

$$\left[\underbrace{\dfrac{\omega_0 m\,\eta}{\rho_2 c_2}}_{\text{mount heat}} + \underbrace{n}_{\text{re radiation, side 1}} + \underbrace{1}_{\text{transmission, side 2}}\right]^2$$

Air both sides, $n = 1$:

$$\left[\frac{\omega_0 m\,\eta}{\rho_0 c} + 2\right]^2$$

$\eta$ carries the mount only. The 2 is the air loss, one per face, transmission itself reading as a resistance from the leaf's seat.

### Closing: TL, the log measure

$$TL = 10\log_{10}(1/\tau)\ \text{dB}$$

The definition is fully general, any medium either side: $\tau$ is defined for whatever fluids are present, the air to water case uses exactly this. Between rooms the same quantity goes by sound reduction index $R$.

What IS air specific are the regime limit formulas of step 8: they set $n = 1$, same fluid both sides, and their constants absorb air's $\rho_0 c$, the mass law's 42 dB buries $20\log_{10}(\rho_0 c/\pi)$. Different fluid, different constant, same definition.










- Reciprocity: tau is the same from either side.
- LPM tie: this is the one-mass one-spring ancestor. The book's eta here is your eta_c, no cavity yet, so no k_a, no MSM, no LR. 5.06-07 adds the second mass and the air spring.