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

A perfectly rigid structure reflects all incident sound, so $\tilde B_1$ is another $\tilde A_1$ plus a radiated component. The rigid wall is a reference fiction, not an assumption: the radiated component is the exact correction restoring the real moving wall, an identity, not an approximation.

The radiated component is a left going wave, not the transmission. The wall radiates separately from both faces, same $\tilde\xi$, opposite signs.

Left going wave model: the leaf shifting right still disturbs the left air, so a wave propagates from that disturbance, and it can only go left because that is where the fluid is. Direction of leaf motion sets the sign, not the destination. The receding face creates the wave by a pull rather than a push, a rarefaction, pressure momentarily below ambient, which is why the amplitude carries a negative sign. Negative amplitude is a half cycle phase flip, nothing deeper.

The left radiated wave travels in the same direction as the rigid bounce and partially cancels it. Energy conservation routes the reflection deficit into transmission plus mount heat.

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




- Governing relation: (z_p + z_f) v = 2A1, with z_p = j(omega m minus s/omega) + r and z_f the two radiation resistances.
- TL = 10 log10(1/tau), and between rooms the same quantity is called sound reduction index R.
- Three regimes. Below resonance: stiffness controlled, TL falls 6 dB per octave as f rises, mass and damping irrelevant. At resonance: a dip, total transmission (0 dB) if radiation damping dominates, else a floor 20 log10(eta) dB below the mass law line. Above resonance: the normal incidence mass law, TL = 20 log10(mf) minus 42 dB, rising 6 dB per octave and 6 dB per doubling of mass.
- Impedance mismatch limit: with strongly different fluids the wall's construction stops mattering, air to water gives about 29.5 dB whatever you build.
- Reciprocity: tau is the same from either side.
- LPM tie: this is the one-mass one-spring ancestor. The book's eta here is your eta_c, no cavity yet, so no k_a, no MSM, no LR. 5.06-07 adds the second mass and the air spring.