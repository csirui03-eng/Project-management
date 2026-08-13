Working object, book Eq (5.14) from the analytical note:

$$\tau = \frac{4n}{\left[\dfrac{\omega m - s/\omega}{\rho_2 c_2}\right]^2 + \left[\dfrac{\omega_0 m\,\eta}{\rho_2 c_2} + n + 1\right]^2}$$

**The two part denominator**

- The $\tau$ denominator splits into a storage term, the panel reactance $\omega m - s/\omega$, and a removal term, the three resistances ($\omega_0 m\eta$ mount heat, $n$ and $1$ radiation either side, all measured against $\rho_2 c_2$).
- Storage blocks by refusing motion, holding energy and handing it back. Removal blocks by carrying energy away for good.

**The regimes are just arm dominance**

- Low $\omega$: the mass part is small, the spring part is big. Storage is effectively $s/\omega$, stiffness controlled, TL falling 6 dB per octave toward the crossing, mass and damping absent (Eq 5.17).
- High $\omega$: the mass part is big, the spring part is small. Storage is effectively $\omega m$, the mass law, TL rising 6 dB per octave and 6 dB per doubling of mass, stiffness and damping absent (Eq 5.21).
- The crossing: set $\omega m = s/\omega$ and $\omega_0 = \sqrt{s/m}$ falls out. The storage term carries the resonance implicitly, as the frequency where its two arms tie.
- At the crossing storage is zero and only the resistive parts act. They fight: radiation dominant, total transmission, TL of 0 dB (Eq 5.25). Mount loss dominant, a dip floor $20\log_{10}\eta$ below the mass law line (Eq 5.26).

**Escape clause**

- If $n$ is too big (or the panel too light) the storage arm never beats the baseline, the wall drops out and $\tau \to 4/n$, the bare fluid interface. Air to water about 29.5 dB whatever you build (Eq 5.18).
