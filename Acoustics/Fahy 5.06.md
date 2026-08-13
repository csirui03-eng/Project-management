right # The idealized double leaf model
![[Pasted image 20260814010159.png]]
## Preamble
**Spatial counterpart to omega:**

$$k = \frac{\omega}{c}$$

$\omega$ counts radians of phase per second at a fixed point, $k$ counts radians per metre at a fixed instant. Two rulers for one wave, $c$ the exchange rate between them.

$$\lambda = \frac{2\pi}{k}$$

The human facing form of $k$: nobody quotes $k$ in conversation, everybody quotes $\lambda$.

$$kd \ll 1 \qquad\qquad kd \sim 1$$

$kd$ is the cavity depth $d$ measured in radians of phase, and the section forks on it: on the left the air collapses to a single spring, on the right standing waves fit inside and $k$ leads.
btw

**Collected pressure equations:**

$$p^{(1)}(x,t) = \tilde p_i\, e^{j(\omega t - kx)} + \tilde p_r\, e^{j(\omega t + kx)} \qquad x \le 0$$

$$p^{(2)}(x,t) = \tilde A\, e^{j(\omega t - kx)} + \tilde B\, e^{j(\omega t + kx)} \qquad 0 \le x \le d$$

$$p^{(3)}(x,t) = \tilde p_t\, e^{j(\omega t - kx)} \qquad x \ge d$$

Five amplitudes, $\tilde p_i$ the known drive, the other four unknown. 

# Step 1: Velocity matching

**Conversion to particle velocity.** Pressure is what the waves carry, velocity is what matching needs: the leaf faces impose their velocity on the fluid touching them. Per travelling wave:

$$u = \frac{p}{\rho_0 c}$$

along the wave's own travel direction, so backward waves take a minus sign in the $+x$ frame. The three fields converted:

$$u^{(1)}(x,t) = \frac{1}{\rho_0 c}\left[\tilde p_i\, e^{j(\omega t - kx)} - \tilde p_r\, e^{j(\omega t + kx)}\right]$$

$$u^{(2)}(x,t) = \frac{1}{\rho_0 c}\left[\tilde A\, e^{j(\omega t - kx)} - \tilde B\, e^{j(\omega t + kx)}\right]$$

$$u^{(3)}(x,t) = \frac{\tilde p_t}{\rho_0 c}\, e^{j(\omega t - kx)}$$

The leaves' own velocities, time derivative of the harmonic displacements:

$$\dot\xi_1 = j\omega\tilde\xi_1\, e^{j\omega t}, \qquad \dot\xi_2 = j\omega\tilde\xi_2\, e^{j\omega t}$$
**Formal rule:**

$$u_{\text{fluid}}(x_{\text{face}}, t) = \dot\xi_{\text{leaf}}(t) \qquad \text{at every instant}$$

The summed particle velocity of all waves in the medium on one side of a face, evaluated at the boundary's $x$, equals the leaf's harmonic motion velocity there. One condition per face, the same leaf velocity serving both its faces. Kinematic boundary condition: the fluid cannot pass through the leaf or pull away from it, so it rides with the face.