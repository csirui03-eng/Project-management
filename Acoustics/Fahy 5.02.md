## The setup: 
an unbounded rigid leaf, mass m per unit area, on a distributed suspension (stiffness s, damping r). The suspension stands represent approximation of real panel edge support.![[Pasted image 20260812200942.jpg]]
## Derivation
### Step 1: the three waves

$$p_i = \tilde A_1 e^{j(\omega t - k_1 x)}, \qquad p_r = \tilde B_1 e^{j(\omega t + k_1 x)}, \qquad p_t = \tilde C_2 e^{j(\omega t - k_2 x)}$$

Basic plane wave in air expressions, incident and reflected on the source side, transmitted on the far side. Nothing to unpack, the content is only in the unknown amplitudes.

### Step 2: velocity matching at the faces

$$\tilde A_1 - \tilde B_1 = j\omega\rho_1 c_1 \tilde\xi, \qquad \tilde C_2 = j\omega\rho_2 c_2 \tilde\xi$$

The fluid cannot detach from or interpenetrate the wall, so the particle velocity of the fluid at each face must equal the wall's own velocity $j\omega\tilde\xi$.

The goal of this move is elimination of degrees of freedom: every wave amplitude becomes slaved to the single leaf displacement $\tilde\xi$. After this step the whole problem has one unknown left, and the remaining work is a single equation of motion for $\tilde\xi$.

### Step 3: split the left field into blocked and radiated parts

The matching merged two jobs into one amplitude: substituting step 2 gives $\tilde B_1 = \tilde A_1 - j\omega\rho_1 c_1\tilde\xi$, so the reflected wave now carries both the passive bounce off an immobile wall (the $\tilde A_1$ part) and the wave the moving wall itself radiates (the $j\omega\rho_1 c_1\tilde\xi$ part).

Regrouping the left field by job instead of by travel direction:

$$p^-(x,t) = \underbrace{2\tilde A_1 \cos k_1 x \, e^{j\omega t}}_{\text{blocked field}} + \underbrace{-\,j\omega\rho_1 c_1\tilde\xi\, e^{j(\omega t + k_1 x)}}_{\text{radiated field}}$$

The blocked field is the standing wave against a rigid wall, contains no $\tilde\xi$, and delivers a known forcing pressure $2\tilde A_1$ at the face (pressure doubling at a rigid reflector).

The radiated field is everything the wall's motion adds, proportional to velocity, so it will fold into the equation of motion as radiation damping rather than as forcing.

The goal of this move is separating known drive from motion dependent self loading, setting up a standard forced oscillator: known right hand side, all $\tilde\xi$ dependence on the left.



- Governing relation: (z_p + z_f) v = 2A1, with z_p = j(omega m minus s/omega) + r and z_f the two radiation resistances.
- TL = 10 log10(1/tau), and between rooms the same quantity is called sound reduction index R.
- Three regimes. Below resonance: stiffness controlled, TL falls 6 dB per octave as f rises, mass and damping irrelevant. At resonance: a dip, total transmission (0 dB) if radiation damping dominates, else a floor 20 log10(eta) dB below the mass law line. Above resonance: the normal incidence mass law, TL = 20 log10(mf) minus 42 dB, rising 6 dB per octave and 6 dB per doubling of mass.
- Impedance mismatch limit: with strongly different fluids the wall's construction stops mattering, air to water gives about 29.5 dB whatever you build.
- Reciprocity: tau is the same from either side.
- LPM tie: this is the one-mass one-spring ancestor. The book's eta here is your eta_c, no cavity yet, so no k_a, no MSM, no LR. 5.06-07 adds the second mass and the air spring.