# The idealized double leaf model
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

**Collected pressure equations (splitting field step, now bundled before starting work :D ):**

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

**The four matched equations.** Note that the spatial harmonic component on the latter leaf do not cancel out, obviously... this is the main difference.

$$\tilde p_i - \tilde p_r = j\omega\rho_0 c\,\tilde\xi_1 \qquad \text{leaf 1 front, } x = 0$$

$$\tilde A - \tilde B = j\omega\rho_0 c\,\tilde\xi_1 \qquad \text{leaf 1 back, } x = 0$$

$$\tilde A\, e^{-jkd} - \tilde B\, e^{jkd} = j\omega\rho_0 c\,\tilde\xi_2 \qquad \text{leaf 2 front, } x = d$$

$$\tilde p_t\, e^{-jkd} = j\omega\rho_0 c\,\tilde\xi_2 \qquad \text{leaf 2 back, } x = d$$

## Step 1.5: substitute into collected pressure equations

For substitution into the incident side and transmitted side pressure equations the process is straightforward. Make the smart substitution choice, and there is only one to make here: express $\tilde p_r$ through $\tilde p_i$ and the leaf motion the match ties them with, and substitute into the incident side equation. On the transmitted side the match already is the substitution.

$$\tilde p_1 = \tilde p_i + \tilde p_r = 2\tilde p_i - j\omega\rho_0 c\,\tilde\xi_1$$

$$\tilde p_4 = \tilde p_t\, e^{-jkd} = j\omega\rho_0 c\,\tilde\xi_2$$

For the cavity space the substitution is more complex: the resulting expression must meet the matching condition at both ends of the space, so the two cavity matches are used jointly, both amplitudes expressed through the motion of both leaves.

**Stage 1.** Read the two cavity matches as simultaneous equations for $\tilde A$ and $\tilde B$, leaf motions as data. The smart substitution choice: raise the $x = 0$ match by $e^{jkd}$ so the $\tilde B$ terms twin and cancel, following the local convention of eliminating the reflected component first, the same choice that removed $\tilde p_r$ on the incident side.

$$\begin{aligned}
R_1 &= j\omega\rho_0 c\,\tilde\xi_1, \qquad R_2 = j\omega\rho_0 c\,\tilde\xi_2 \\[4pt]
\tilde A - \tilde B &= R_1 &&\text{(i)} \\
\tilde A\, e^{-jkd} - \tilde B\, e^{jkd} &= R_2 &&\text{(ii)} \\[4pt]
\tilde A\, e^{jkd} - \tilde B\, e^{jkd} &= R_1\, e^{jkd} &&\text{(i')} \\
\tilde A\left(e^{jkd} - e^{-jkd}\right) &= R_1\, e^{jkd} - R_2 &&\text{(i') minus (ii)} \\
\tilde A\,\left(2j\sin kd\right) &= R_1\, e^{jkd} - R_2 &&\text{Euler} \\[4pt]
\tilde A &= \frac{\omega\rho_0 c\left(\tilde\xi_1\, e^{jkd} - \tilde\xi_2\right)}{2\sin kd}
\end{aligned}$$

$$\begin{aligned}
\tilde B &= \tilde A - R_1 &&\text{rearranged (i)} \\
&= \frac{\omega\rho_0 c\left(\tilde\xi_1\, e^{jkd} - \tilde\xi_2\right)}{2\sin kd} - j\omega\rho_0 c\,\tilde\xi_1 \\
&= \frac{\omega\rho_0 c\left(\tilde\xi_1\left(e^{jkd} - 2j\sin kd\right) - \tilde\xi_2\right)}{2\sin kd} \\[4pt]
\tilde B &= \frac{\omega\rho_0 c\left(\tilde\xi_1\, e^{-jkd} - \tilde\xi_2\right)}{2\sin kd}
\end{aligned}$$

**Stage 2.** Now we can substitute both $\tilde A$ and $\tilde B$ directly into the pressure expression for the cavity:

$$\begin{aligned}
p^{(2)}(x) &= \tilde A\, e^{-jkx} + \tilde B\, e^{jkx} \\
&= \frac{\omega\rho_0 c}{2\sin kd}\left[\left(\tilde\xi_1\, e^{jkd} - \tilde\xi_2\right) e^{-jkx} + \left(\tilde\xi_1\, e^{-jkd} - \tilde\xi_2\right) e^{jkx}\right] \\
&= \frac{\omega\rho_0 c}{2\sin kd}\left[\tilde\xi_1\left(e^{jk(d-x)} + e^{-jk(d-x)}\right) - \tilde\xi_2\left(e^{-jkx} + e^{jkx}\right)\right] &&\text{group by leaf} \\[4pt]
p^{(2)}(x) &= \frac{\omega\rho_0 c}{\sin kd}\left[\tilde\xi_1\, \cos k(d-x) - \tilde\xi_2\, \cos kx\right] &&\text{Euler, sum pair}
\end{aligned}$$

**Notice:** with substitution complete, due to the velocity matching the only dependency on pressure left is the incident amplitude $\tilde p_i$. The pressure in all other regions is described by leaf motion only.


# Step 2: Panel EOMs

Forces in each leaf are the restoring and damping forces of its mount, modelled as the spring and damper, plus the leaf's inertial force. The sum of those equals the pressure difference across the leaf.

**EOMs:**

$$m_1\ddot\xi_1 + r_1\dot\xi_1 + s_1\xi_1 = P_1 - P_2$$

$$m_2\ddot\xi_2 + r_2\dot\xi_2 + s_2\xi_2 = P_3 - P_4$$

**Bring EOMs to time harmonic form.** Every term carries the shared clock, so it divides out and amplitudes remain:

$$\left(-\omega^2 m_1 + j\omega r_1 + s_1\right)\tilde\xi_1 = \tilde p_1 - \tilde p_2$$

$$\left(-\omega^2 m_2 + j\omega r_2 + s_2\right)\tilde\xi_2 = \tilde p_3 - \tilde p_4$$

**The four face amplitudes**, outer pair $d$ free, cavity pair carrying $d$ twice over:

$$\tilde p_1 = 2\tilde p_i - j\omega\rho_0 c\,\tilde\xi_1$$

$$\tilde p_2 = \tilde p^{(2)}(0) = \frac{\omega\rho_0 c}{\sin kd}\left(\tilde\xi_1\cos kd - \tilde\xi_2\right)$$

$$\tilde p_3 = \tilde p^{(2)}(d) = \frac{\omega\rho_0 c}{\sin kd}\left(\tilde\xi_1 - \tilde\xi_2\cos kd\right)$$

$$\tilde p_4 = j\omega\rho_0 c\,\tilde\xi_2$$

**Substitute the pressure amplitude at each face into the EOMs and isolate the driving pressure amplitude:**

$$\left(-\omega^2 m_1 + j\omega r_1 + s_1\right)\tilde\xi_1 + j\omega\rho_0 c\,\tilde\xi_1 + \frac{\omega\rho_0 c}{\sin kd}\left(\tilde\xi_1\cos kd - \tilde\xi_2\right) = 2\tilde p_i$$

$$\left(-\omega^2 m_2 + j\omega r_2 + s_2\right)\tilde\xi_2 + j\omega\rho_0 c\,\tilde\xi_2 - \frac{\omega\rho_0 c}{\sin kd}\left(\tilde\xi_1 - \tilde\xi_2\cos kd\right) = 0$$

Now take the pair to reference panel velocity instead of panel displacement:

$$\tilde\xi_i = \frac{\tilde v_i}{j\omega}$$

Dividing each equation by $j\omega$, the mechanical bracket collapses to the textbook impedance:

$$\frac{-\omega^2 m_i + j\omega r_i + s_i}{j\omega} = r_i + j\left(\omega m_i - \frac{s_i}{\omega}\right) = z_i$$

$$z_1\,\tilde v_1 + \rho_0 c\,\tilde v_1 - \frac{j\rho_0 c}{\sin kd}\left(\tilde v_1\cos kd - \tilde v_2\right) = 2\tilde p_i$$

$$z_2\,\tilde v_2 + \rho_0 c\,\tilde v_2 + \frac{j\rho_0 c}{\sin kd}\left(\tilde v_1 - \tilde v_2\cos kd\right) = 0$$
