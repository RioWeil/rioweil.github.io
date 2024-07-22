---
layout: post
title: "UChicago Graduate Diagnostic Exam Prep - Quantum Mechanics"
date: 2024-07-18
description: Interesting quantum mechanics problems solved while studying for the graduate diagnostic exam.
categories: physics uchicago quantum
---
**July 18, 2024.** *Before the start of my PhD program at UChicago this fall, there is a diagnostic exam to test knowledge/ability in the core subjects of classical mechanics, electromagnetism, quantum mechanics, and statistical mechanics. Here, I share some interesting problems and solutions I came across while preparing for this exam. This is the first post in this series, where I go through quantum mechanics problems.*

### Contents
- <a href="#problem-qm-scmicroresonator" name="#problem-qm-scmicroresonator"> Superconducting Microwave Resonator</a>
- <a href="#problem-qm-twospinmeasurement" name="#problem-qm-twospinmeasurement"> Measuring a Two-Spin System </a>
- <a href="#problem-qm-rigidrotor" name="#problem-qm-rigidrotor"> Rigid Rotor in Magnetic Field </a>
- <a href="#problem-qm-symmetryamplitudes" name="#problem-qm-symmetryamplitudes"> Symmetries and Transition Amplitudes </a>
- <a href="#problem-qm-thermalstates" name="#problem-qm-thermalstates"> Thermal States </a>
- <a href="#problem-qm-identicalscattering" name="#problem-qm-identicalscattering"> Scattering of Identical Particles </a>
- <a href="#problem-qm-spinorbitqho" name="#problem-qm-spinorbitqho"> Spin-Orbit Coupling in the 3-D Harmonic Oscillator </a>
- <a href="#problem-qm-identicalcubicwell" name="#problem-qm-identicalcubicwell"> Identical Particles in an Infinite Cubic Well </a>
- <a href="#problem-qm-timevaryforce" name="#problem-qm-timevaryforce"> Time-Varying Force </a>
- <a href="#problem-qm-twofermions" name="#problem-qm-twofermions"> Two Interacting Fermions </a>
- <a href="#problem-qm-spinchain" name="#problem-qm-spinchain"> A Quantum Spin Chain </a>
- <a href="#problem-qm-emagmoment" name="#problem-qm-emagmoment"> Anomalous Magnetic Moment of the Electron </a>
- <a href="#problem-qm-heisenbergferro" name="#problem-qm-heisenbergferro"> A Heisenberg Ferromagnet </a>
- <a href="#problem-qm-susy" name="#problem-qm-susy"> The Supersymmetric Method </a>
- <a href="#problem-qm-timedepmag" name="#problem-qm-timedepmag"> Spin 1/2 in Time-Dependent Magnetic Field </a>
- <a href="#problem-qm-onedlattice" name="#problem-qm-onedlattice"> Particle on a 1-D Lattice </a>
- <a href="#problem-qm-spinhalfsg" name="#problem-qm-spinhalfsg"> Spin-1/2 and Stern-Gerlach </a>
- <a href="#problem-qm-qhotrans" name="#problem-qm-qhotrans"> Harmonic Oscillator and Translation </a>


#### Superconducting Microwave Resonator <a id="problem-qm-scmicroresonator" name="problem-qm-scmicroresonator"></a>
**Source:** UBC Spring 2024 Physics Qualifying Exam Q1

**Problem Statement:** *A superconducting microwave resonator is a small loop with an inductance of $$L$$ and a capacitance of $$C$$. It can be modelled quantum-mechanically. Its quantum state can be described by the charge $$Q$$ on the capacitor and the magnetic flux $$\phi$$ through the loop. The operators for these quantities satisfy an uncertainty relation $$[\hat{Q}, \hat{\phi}] = i\hbar$$. Write down the Hamiltonian for this system, and determine its ground state energy.*

**Solution:** We start by analyzing the system using knowing what we know about circuits in a classical setting, then promote the classical variables by classical quantization to obtain the quantum Hamiltonian and ground state energy.

The potential drop across a capacitor with charge $$dQ$$ and capacitance $$C$$ is:

$$
V_{\text{cap}}= \frac{Q}{C}
$$

and hence the energy stored by adding infinitesimal charge $$dQ$$ is:

$$
dE_{\text{cap}} = VdQ= \frac{Q}{C}dQ.
$$

Thus if we charge up the capacitor from 0 charge to final charge $$Q$$ we can integrate the above to obtain the total stored energy in the capacitor:

$$
E_{\text{cap}} = \frac{1}{2C}Q^2.
$$

Next, the potential drop across an inductor is:

$$
V_{\text{ind}} = L\dot{I} = \dot{\phi}
$$

where the second equality follows via Faraday's law. Integrating both sides of the second equality from zero current/flux at $$t = 0$$ to a final current/flux of $$I$$ and $$\phi$$, we obtain:

$$
LI = \phi
$$

Furthermore, the energy stored in the inductor per unit time (using $$P = IV$$) is:

$$
\dot{E}_{\text{ind}} = IV_{\text{ind}} = LI\dot{I}
$$

Therefore the energy stored per infinitesimal current $$dI$$ is:

$$
dE_{\text{ind}} = LIdI
$$

Thus if we go from 0 current to final current $$I$$ the inductor stores energy:

$$
E_{\text{ind}} = \frac{1}{2}LI^2.
$$

Rewriting this in terms of $$\phi$$:

$$
E_{\text{ind}} = \frac{1}{2L}\phi^2
$$

Thus we have determined the energy of the system in terms of $$L, C, Q, \phi$$ to be:

$$
E = \frac{1}{2C} Q^2 + \frac{1}{2L}\phi^2.
$$

Via canonical quantization we promote the classical variables $$Q, \phi$$ to quantum operators $$\hat{Q}, \hat{\phi}$$ and thus the energy $$E$$ to the Hamiltonian $$\hat{H}$$, thus obtaining:

$$
\color{blue}{\hat{H} = \frac{1}{2C}\hat{Q}^2 + \frac{1}{2L}\hat{\phi}^2.}
$$

To find the ground state energy, we note the similarities of the above Hamiltonian with that of the quantum harmonic oscillator:

$$
\hat{H}_{\text{HO}} = \frac{1}{2}k\hat{x}^2 + \frac{1}{2m}\hat{p}^2
$$

which has eigenenergies $$E_n = \hbar\omega(n + \frac{1}{2})$$ with $$\omega = \sqrt{k/m}$$. Since $$\hat{Q}, \hat{\phi}$$ obey the same (canonical) commutation relations as $$\hat{x}, \hat{p}$$ and this is the only algebraic data necessary to determine the eigenenergies, $$\hat{H}$$ has the same eigenenergies (just replacing $$k = \frac{1}{C}, m = L$$) ans so the ground state energy of the system is:

$$
\color{blue}{E_0 = \frac{1}{2}\hbar\sqrt{\frac{1}{LC}}.}
$$

#### Measuring a Two-Spin System <a id="problem-qm-twospinmeasurement" name="problem-qm-twospinmeasurement"></a>
**Source:** UBC Spring 2024 Physics Qualifying Exam Q6

**Problem Statement:** *Many copies of a system of two spin-1/2 particles are prepared in an identical spin state given by:*
\begin{equation}\label{eq:twospins}
\lvert \psi \rangle = a\lvert \uparrow\uparrow \rangle + b\lvert \uparrow \downarrow \rangle + c\lvert \downarrow \uparrow \rangle + d\lvert \downarrow \downarrow \rangle
\end{equation}
*An experimenter performs many measurements of these identical systems, and finds the following results:*
- *If only the first spin is measured, the result is spin up with 30% probability.*
- *If only the second spin is measured, the result is spin up with 40% probability.*
- *If both spins are measured, the result is both spins up with 10% probability.*
*Derive the upper and lower limits on the probability that a measurement of the total spin of this state will yield zero.*

**Solution:** From the experimental data (and the Born rule), we know that $$\lvert a \rvert^2 + \lvert b \rvert^2 = 3/10$$, $$\lvert a \rvert^2 + \lvert c \rvert^2 = 4/10$$, and $$\lvert a \rvert^2 = 1/10$$. For completeness' sake let us go through the full calculation for the first of these. The probability of measuring the first spin to be spin up is given by the Born rule to be:

$$p(s_1 = \uparrow) = \rangle \psi \lvert \Pi_1^{\uparrow} \otimes I_2 \lvert \psi \rangle$$

Where $$\Pi_{\uparrow}^{(1)} = \lvert \uparrow \rangle_1 \langle \uparrow \rvert_1$$ is the projector onto the $$\uparrow$$ state for the first spin and $$I_2$$ is the identity matrix on the second spin. Thus using that $$\langle \uparrow \vert \uparrow \rangle = 1$$ and $$\langle \uparrow \vert \downarrow \rangle = 0$$ we find:

$$
p(s_1 = \uparrow) = (a^*\langle \uparrow \rvert_2 + b^* \langle \downarrow \rvert_2)(a\lvert \uparrow \rangle_2 + b\lvert \downarrow \rangle_2) = \lvert a \rvert^2 + \lvert b \rvert^2
$$

which from the experimental data is equal to $$3/10$$. Analogous calculations follow for the other cases.

Now, substituting the third expression into the first/second we find that $$\lvert b \rvert^2 = 2/10$$ and $$\lvert c \rvert^2 = 3/10$$, and from the normalization of the state it must hold that:

$$
\lvert a \rvert^2 + \lvert b \rvert^2 + \lvert c \rvert^2 + \lvert d \rvert^2 = 1
$$

from which we find that $$\lvert d \rvert^2 = 4/10$$. The question asks for the probability that we measure the total spin of the state to be zero. To this end we rewrite the state in the $$\lvert s m \rangle$$ basis, with: $$ \lvert 1 1 \rangle = \lvert \uparrow \uparrow \rangle$$, $$ \lvert 1 -1 \rangle = \lvert \downarrow \downarrow \rangle$$, $$\lvert 1 0 \rangle = \frac{1}{\sqrt{2}}(\lvert \uparrow \downarrow \rangle + \lvert \downarrow \uparrow \rangle)$$ and $$\lvert 0 0 \rangle = \frac{1}{\sqrt{2}}(\lvert \uparrow \downarrow \rangle - \lvert \downarrow \uparrow \rangle)$$. Thus:

$$
\lvert \psi \rangle = a\lvert 1 1 \rangle + \frac{b + c}{\sqrt{2}}\lvert 1 0 \rangle + \frac{b - c}{\sqrt{2}}\lvert 0 0 \rangle + d\lvert 1 -1 \rangle
$$

We are interested in the probability of measuring $$s = 0$$, and hence:

$$
p(s=0) = \lvert\frac{b - c}{\sqrt{2}} \rvert^2 = \frac{1}{2}(\lvert b \rvert^2 + \lvert c \rvert^2 - b^*c - bc^*) = \frac{1}{2}(\frac{1}{2} - b^*c - bc^*)
$$

where in the last equality we use the known values of $$\lvert b \rvert^2$$ and $$\lvert c \rvert^2$$. $$b, c$$ have undetermined phases with $$b = e^{i\phi_b}\sqrt{\frac{2}{10}}$$ and $$c = e^{i\phi_c}\sqrt{\frac{3}{10}}$$. We thus determine the upper and lower bounds on:

$$
-(b^*c + bc^*) = -\frac{\sqrt{6}}{10}(e^{i(-\phi_b + \phi_c)} + e^{i(\phi_b - \phi_c)}) = -\frac{\sqrt{6}}{5}\cos(\phi)
$$
where we defined $$\phi = \phi_b - \phi_c$$ and applied Euler's identity. This quantity maximized when $$\phi = \pi$$ for which we have:

$$
\color{blue}{p(s=0)_{\text{max}} = \frac{1}{4} + \frac{\sqrt{6}}{10}.}
$$

Conversely, we have the minimum when $$\phi = 0$$ for which:

$$
\color{blue}{p(s=0)_{\text{min}} = \frac{1}{4} - \frac{\sqrt{6}}{10}.}
$$

#### Rigid Rotor in Magnetic Field <a id="problem-qm-rigidrotor" name="problem-qm-rigidrotor"></a>
**Source:** UBC PHYS 402 2022 Final Q4

**Problem Statement:** *The Hamiltonian of a rigid rotor placed in a magnetic field perpendicular to its axis takes the approximate:*
\begin{equation}\label{eq:rigidrotor}
H = \alpha L^2 + \beta L_z + \gamma L_x
\end{equation}
with $$\alpha, \beta, \gamma$$ real and $$L_i$$ the angular momentum operators.

*(a) Show that the exact eigenenergies are given by:*
\begin{equation}\label{eq:exact}
E_{l, m} = \alpha \hbar^2l(l+1) + \sqrt{\beta^2 + \gamma^2}\hbar m.
\end{equation}

*(b) Assuming $$\gamma \ll \beta$$, use perturbation theory to lowest non-vanishing order to independently obtain approximate energy eigenvalues.*

*(c) Check consistency between the results in (a) and (b)*

**Solution:** (a) We can exactly solve the problem via a coordinate transformation. In particular, we rotate the system about the $$y$$-axis by angle $$\theta$$ such that $$\tan\theta = \gamma/\beta$$. This gives us the transformed Hamiltonian:

$$
H = \alpha L^2 + \sqrt{\beta^2 + \gamma^2}L_z'
$$

where we note that $$L^2$$ is invariant under rotations and $$L_z'$$ is the $$z$$-angular momentum operator in the transformed coordiante system. Since $$[L^2, L_z'] = 0$$, they share a simultaneous eigenbasis, and labelling the eigenstates as $$\lvert l, m' \rangle$$ we find the eigenergies to be:

$$
\color{blue}{E_{l, m'} = \alpha \hbar^2l(l+1) + \sqrt{\beta^2 + \gamma^2}\hbar m'}
$$

as claimed.

(b) The perturbation theory, we take the base Hamiltonian to be $$H_0 = \alpha L^2 + \beta L_z$$ and the perturbation to be $$H' = \gamma L_x = \gamma\frac{L_+ + L_-}{2}$$ where we write $$L_x$$ in terms of the raising/lowering operators of angular momentum. The eigenbasis of $$H_0$$ is $$\lvert l, m\rangle$$. Thus, the zeroth order energy eigenvalues are:

$$
E^{(0)}_{l, m} = \alpha\hbar^2l(l+1) + \beta\hbar m.
$$

Computing the first order corrections, we find:

$$
E^{(1)}_{l, m} = \langle l, m \rvert H' \lvert l, m \rangle = \frac{\gamma}{2}\langle l, m \rvert (L_+ + L_-)\lvert l, m \rangle = 0.
$$

These vanish and we must go to second order:

$$
E^{(2)}_{l, m} = \sum_{l', m' \neq l, m} \frac{\lvert \langle l, m \vert H' \lvert l', m' \rangle \rvert^2}{E^{(0)}_{l, m} - E^{(0)}_{l', m'}} = \frac{\gamma^2\hbar^2}{4}\left[\frac{l(l+1) - m(m-1)}{E^{(0)}_{l, m} - E^{(0)}_{l, m-1}} + \frac{l(l+1) - m(m+1)}{E^{(0)}_{l, m} - E^{(0)}_{l, m+1}}\right]
$$

Substituing in the zeroth order energies we find:

$$
\color{blue}{E^{(2)}_{l, m} = \frac{\gamma^2\hbar m}{2\beta}}.
$$

(c) We Taylor expand the exact result in (a) in powers of (small) $$\gamma/\beta$$:

$$
E_{l, m} = \alpha \hbar^2 l(l+1) + \beta\sqrt{1 + \left(\frac{\gamma}{\beta}\right)^2}\hbar m = \alpha \hbar^2 l(l+1) + \beta\left(1 + \frac{1}{2}\left(\frac{\gamma}{\beta}\right)^2\right)\hbar m + O(\left(\frac{\gamma}{\beta}\right)^3)
$$

thus:

$$
\color{blue}{E_{l, m} = \alpha\hbar^2l(l+1) + \beta\hbar m + \frac{\gamma^2\hbar m}{2\beta} + O(\left(\frac{\gamma}{\beta}\right)^3)}
$$

and the exact result agrees to perturbation theory to second order.

#### Symmetries and Transition Amplitudes <a id="problem-qm-symmetryamplitudes" name="problem-qm-symmetryamplitudes"></a>
**Source:** UBC PHYS 500 2023 HW2 Q2

**Problem Statement:** *One of the most important applications of symmetries in quantum mechanics is that they can be used to constrain the amplitudes for many dynamical processes without doing any calculation.*

*(a) Consider a time-independent Hamiltonian $$H$$ and a symmetry operation implemented by a unitary operator $$S$$ that commutes with $$H$$, $$[S, H] = 0$$. Show that the amplitude $$\langle \psi_f \rvert U(t) \lvert \psi_i \rangle$$ for a state $$\lvert \psi_i \rangle$$ to transition to a different state $$\lvert \psi_f \rangle$$ vanishes if $$\lvert \psi_{i, f} \rangle$$ are eigenstates of $$S$$ with different eigenvalues, i.e. if $$S\lvert \psi_{i, f} \rangle = e^{i\phi_{i, f}}\lvert \psi_{i, f} \rangle$$ with $$\phi_i \neq \phi_f$$. Here $$U(t) = \exp(-iHt)$$ is the time evolution unitary.*

*(b) The quadratic/harmonic potential is symmetric under parity, $$\Pi: x \to -x$$ and $$\Pi: p \to -p$$. Denote the unitary opeartor that implements parity by the same symbol, $$\Pi$$. What are the possible eigenvalues of $$\Pi$$? What is the parity of the $$n$$th energy eigenstate $$\lvert n \rangle = \frac{(a^\dagger)^n}{\sqrt{n!}}\lvert 0 \rangle$$? Suppose we start with an initial state equal to the ground state $$\lvert 0 \rangle$$ of the Harmonic oscillator, and turn on a quartic potential $$V_4 = \alpha x^4$$. What is the amplitude to find the particle in the first excited state of the harmonic oscillator at time $$t$$ later?*

**Solution:** (a) We evaluate the expression $$\langle \psi_f \rvert S^\dagger U(t) S - U(t)\lvert \psi_i \rangle$$ in two different ways. First, since $$[S, H] = 0$$ then $$[S, U(t)] = 0$$ and so:

$$
\langle \psi_f \rvert S^\dagger U(t) S - U(t)\lvert \psi_i \rangle = \langle \psi_f \rvert S^\dagger S U(t) - U(t)\lvert \psi_i \rangle = \langle \psi_f \rvert U(t) - U(t)\lvert \psi_i \rangle = 0
$$

For the other way we evaluate the two terms:

$$
\langle \psi_f \rvert S^\dagger U(t) S - U(t)\lvert \psi_i \rangle = \langle \psi_f \rvert S^\dagger U(t) S \lvert \psi_i \rangle - \langle \psi_f \rvert U(t)\lvert \psi_i \rangle = e^{i(\phi_{i} - \phi_f)}\langle \psi_f \rvert U(t)\lvert \psi_i \rangle - \langle \psi_f \rvert U(t)\lvert \psi_i \rangle = (e^{i(\phi_{i} - \phi_f)} - 1)\langle \psi_f \rvert U(t)\lvert \psi_i \rangle
$$

Thus:

$$
0 = (e^{i(\phi_{i} - \phi_f)} - 1)\langle \psi_f \rvert U(t)\lvert \psi_i \rangle
$$

so unless $$\phi_i = \phi_f$$ then $$\color{blue}{\langle\psi_f \rvert U(t)\lvert \psi_i \rangle = 0.}$$

(b) Note that applying spatial inversion twice amounts to doing nothing; $$P^2(x) = P\circ P(x) = P(-x) = x$$ (and analogously for $$p$$) and so $$P^2 = I$$. Hence the square of the eigenvalues of $$P$$ are $$\lambda^2 = 1$$ and hence $$\color{blue}{\lambda = \pm 1}$$. Next, note the definition of the raising operator $$a^\dag$$:

$$
  a^\dag = \sqrt{\frac{m\omega}{2}}(x - i\frac{p}{m\omega}).
$$

$$a^\dag$$ is linear in $$x, p$$ and so $$Pa^\dag = -a^\dag$$, and more generally $$P (a^\dag)^n = (-1)^n (a^\dag)^n$$. Noting that $$\ket{0}$$ has even parity (its wavefunction is a Gaussian symmetric about $$x = 0$$), the parity of $$\ket{n} = \frac{1}{\sqrt(n+1)!}(a^\dag)^n\ket{0}$$ is therefore $\color{blue}{(-1)^n}$.

Next, note that $$V_4 = \alpha x^4$$ commutes with $$P$$ as it is even in $$x$$. Therefore, $$[P, H_{\text{SHO}} + V_4] = 0$$ and since the ground state $$\ket{0}$$ and first excited state $$\ket{1}$$ of the harmonic oscillator have different parities, by our result in (a) <span style="color:blue">the transition amplitude vanishes.</span>

#### Thermal States TODO <a id="problem-qm-thermalstates" name="problem-qm-thermalstates"></a>
**Source:** UBC PHYS 500 2023 HW3 Q1

**Problem Statement:** *Consider a single electron spin (spin-1/2) in a magnetic field with Hamiltonian:*

$$
H = -g\mu_B B S_z
$$

*where $$g$$ is the g-factor of the spin, $$\mu_B$$ is the Bohr magneton, $$B$$ is the magnetic field (here in the $$z$$-direction) and $$S_z = \frac{1}{2}\sigma_z$$ is the $$z$$-component of spin (with $$\hbar = 1$$).*

*(a) What is the the expected $$z$$-magnetization, $$m = \langle S_z \rangle = \langle \frac{1}{2}\sigma_z \rangle$$ for a thermal equilibrium state of the spin at temperature $$T$$?*

*(b) Compute the spin suceptibility $$\chi = \frac{\partial m}{\partial B}$$ as a function of temperature. How does this quantity behave asymptotically in the extreme limits of $$T \to 0, \infty$$?*

*(c) Compare the entropy as a function of temperature. How does this quantity behave asymptotically in the extreme limits of $$T \to 0, \infty$$?*

**Solution:**

#### Scattering of Identical Particles <a id="problem-qm-identicalscattering" name="problem-qm-identicalscattering"></a>
**Source:** UBC PHYS 500 2023 HW6 Q4

**Problem Statement:**

**Solution:**

#### Spin-Orbit Coupling in the 3-D Harmonic Oscillator <a id="problem-qm-spinorbitqho" name="problem-qm-spinorbitqho"></a>
**Source:** UChicago 2014 Quantum Mechanics Graduate Diagnostic Exam Q2

**Problem Statement:** *Consider a spin 1/2 particle of mass $$m$$ moving in a three-dimensional harmonic oscillator potential:*
\begin{equation}\label{eq:3dqho}
V(r) = \frac{1}{2}m\omega^2r^2
\end{equation}
*with $$r^2 = x^2 + y^2 + z^2$$.*

*(a) What are the energy and degeneracy (including spin) of the ground state(s) and the first excited state(s) of this system?*

*(b) The general form of the spin-orbit coupling for a particle of mass m and spin \mathbf{S} moving in a radial potential $$V(r)$$ is:*
\begin{equation}\label{eq:spinorbit}
H_{s-o} = \frac{1}{2m^2c^2}\mathbf{S} \cdot \mathbf{L} \frac{1}{r}\frac{dV(r)}{dr}
\end{equation}
*What are the corrections to the ground state and first excited state energy eigenvalues for a spin 1/2 particle in the three-dimensional isotropic harmonic oscillator potential above when this spin-orbit interaction is included?*

**Solution:** (a) We can write the 3-D harmonic oscillator Hamiltonian as the sum of 1-D harmonic oscillator Hamiltonians:

$$
H_{3D} = \frac{\mathbf{p}^2}{2m} + V(r) = \frac{p_x^2 + p_y^2 + p_z^2}{2m} + \frac{1}{2}m\omega^2(x^2 + y^2 + z^2) = H_{x} + H_y + H_z
$$

Thus the eigenstates of $$H_{3D}$$ are simply the tensor product of the eigenstates of the 1D harmonic oscillators in each direction, denoted by the four (including spin) quantum numbers to be $$\lvert n_x, n_y, n_z, s_z \rangle$$, and with energies:

$$
E_{n_x, n_y, n_z, s_z} = E_{n_x} + E_{n_y} + E_{n_z} = \hbar\omega(n_x + \frac{1}{2}) + \hbar\omega(n_y + \frac{1}{2}) + \hbar\omega(n_z + \frac{1}{2}) = \hbar\omega(n_x + n_y + n_z + \frac{3}{2}).
$$

Thus the ground state energy is obtained by taking $$n_x = n_y = n_z = 0$$:

$$
\color{blue}{E_{g} = \frac{3}{2}\hbar\omega}
$$

which is <span style="color:blue">2-fold degenerate</span> due to the spin (which can be $$\pm 1/2$$). The first excited state has one of the $$n_i$$ equal to one and the rest to 0, and has energy:

$$
\color{blue}{E_{1-ex} = \frac{5}{2}\hbar\omega.}
$$

There are three options for which of the $$n_i$$ are one and two choices for the spin state, and thus this state is <span style="color:blue">6-fold degenerate</span>.

(b) We first convert the eigenstates of the previous section to be eigenstates of the angular momentum operators $$L^2$$ and $$L_z$$. First, we note that $$L_i = \epsilon_{ijk}r_jp_k$$ (with $$\epsilon_{ijk}$$ the Levi-Civita symbol and using the Einstein summation notation), and that we can express the position/momentum operators in terms of the raising/lowering operators $$a_i^\dagger/a_i$$ as:

$$
r_i = \sqrt{\frac{\hbar}{2m\omega}}(a_i^\dagger + a_i)
$$

$$
p_i = i\sqrt{\frac{\hbar m \omega}{2}}(a_i^\dagger - a_i).
$$

Thus we can express the angular momentum operators in terms of the raising/lowering operators:

$$
L_i = i\hbar\epsilon_{ijk}a_ja_k^\dagger
$$

$$
L^2 = L_iL_i = \hbar^2(N(N+1) - a_k^\dagger a_k^\dagger a_j a_j)
$$
where repeated indices are summed over and $$N = a_i^\dagger a_i$$ is the (total) number operator.

Using these expressions, we find that the states $$\lvert n_x=0, n_y=0, n_z=0, s_z=\pm 1/2 \rangle$$ of the last section are eigenstates of $$L^2$$ and $$L_z$$ with eigenvalue zero (using that $$a_j\lvert n_j = 0 \rangle = 0$$), and thus we may write them as angular momentum eigenstates of $$\lvert l=0, m=0, s=1/2, s_z=\pm 1/2 \rangle$$. 

The first excited states with one quanta are eigenstates of $$L^2$$ - the $$a_ja_j$$ term vanishes and we are left with $$L^2 = \hbar^2l(l+1) = \hbar^2(1)(1+1) = 2\hbar^2$$. The $$\lvert n_x=0, n_y=0, n_z=1, s_z=\pm 1/2 \rangle$$ states are also an eigenstate of $$L_z$$ (with eigenvalue 0) and can be identified with $$\lvert l=1, m=0, s=1/2, s_z=\pm 1/2 \rangle$$. The other two states are not immediately eigenstates of $$L_z$$ but by taking linear combinations we obtain:

$$
\lvert l = 1, m = \pm 1, s=1/2, s_z = \pm 1/2 \rangle = \frac{\lvert n_x=1, n_y = 0, n_z = 0, s_z = \pm 1/2\rangle \pm \lvert n_x=0, n_y = 1, n_z = 0, s_z = \pm 1/2\rangle}{\sqrt{2}}.
$$

We now have a basis more convenient for thinking about spin-orbit coupling. We treat the spin-orbit coupling as a perturbation, with the form:

$$
H_{s-o} = \frac{1}{2m^2c^2}\mathbf{S} \cdot \mathbf{L} \frac{1}{r}\frac{dV(r)}{dr} = \frac{1}{2m^2c^2}\mathbf{S} \cdot \mathbf{L} \frac{1}{r}\left(\frac{1}{2}m\omega^2 2r\right) = \frac{\omega^2}{mc^2}\mathbf{S} \cdot \mathbf{L}
$$ 

The $$\lvert l, m, s, s_z \rangle$$ basis we use is inconvenient for calculating the energy corrections as these states are not eigenstates of $$\mathbf{S} \cdot \mathbf{L}$$. However, defining the joint angular momentum $$J_i = L_i + S_i$$ we find that $$J^2 = L^2 + S^2 + 2\mathbf{S} \cdot \mathbf{L}$$ and so $$\mathbf{S} \cdot \mathbf{L} = \frac{J^2 - L^2 - S^2}{2}$$. Thus we will find it convenient to work in the $$\lvert j, j_z, l, s\rangle$$ basis. To this end we note:

$$
\lvert j=1/2, j_z = \pm 1/2, l = 0, s = 1/2 \rangle = \lvert l = 0, m = 0, s = 1/2, s_z = \pm 1/2 \rangle
$$

$$
\lvert j=3/2, j_z = \pm 3/2, l = 1, s = 1/2 \rangle = \lvert l = 1, m = \pm 1, s = 1/2, s_z = \pm 1/2 \rangle
$$

$$
\lvert j=3/2, j_z = 1/2, l = 1, s = 1/2 \rangle = \sqrt{\frac{1}{3}}\lvert l=1, m=1, s=1/2, s_z=-1/2\rangle + \sqrt{\frac{2}{3}}\lvert l=1, m=0, s=1/2, s_z=1/2\rangle
$$

$$
\lvert j=1/2, j_z = 1/2, l = 1, s = 1/2 \rangle = \sqrt{\frac{2}{3}}\lvert l=1, m=1, s=1/2, s_z=-1/2\rangle - \sqrt{\frac{1}{3}}\lvert l=1, m=0, s=1/2, s_z=1/2\rangle
$$

$$
\lvert j=3/2, j_z = -1/2, l = 1, s = 1/2 \rangle = \sqrt{\frac{1}{3}}\lvert l=1, m=-1, s=1/2, s_z=1/2\rangle + \sqrt{\frac{2}{3}}\lvert l=1, m=0, s=1/2, s_z=-1/2\rangle
$$

$$
\lvert j=1/2, j_z = -1/2, l = 1, s = 1/2 \rangle = -\sqrt{\frac{2}{3}}\lvert l=1, m=-1, s=1/2, s_z=1/2\rangle + \sqrt{\frac{1}{3}}\lvert l=1, m=0, s=1/2, s_z=-1/2\rangle.
$$

These equations can be obtained by comparing the quantum numbers on each side, with the coefficients in the last four equations being determined with the help of a Clebsh-Gordon table (Note: to do this part of the question properly, we could apply the raising/lowering operators of angular momentum to find the coefficients (and indeed this is how the CG-table is derived). However, the exact coefficients presented here are not strictly relevant for solving the problem, and so we omit this (slightly tedious) step of the calculation). With this basis transformation established, we can compute the energy corrections using first-order perturbation theory:

$$
E^{(1)}_{j, j_z, l, s} = \langle j, j_z, l, s \rvert H_{s-0} \lvert j, j_z, l, s \rangle = \frac{\omega^2}{mc^2}\langle j, j_z, l, s \rvert \frac{J^2 - L^2 - S^2}{2} \lvert j, j_z, l, s \rangle = \frac{\hbar^2\omega^2}{2mc^2}(j(j+1) - l(l+1) - s(s+1))
$$

Thus for the ground state(s) with $$l = 0$$, $$s = 1/2$$ and $$j = 1/2$$ we find:

$$
\color{blue}{E^{(1)}_{j=1, j_z=\pm 1/2, l=0, s=1/2} = \frac{\hbar^2\omega^2}{2mc^2}(\frac{1}{2}(\frac{1}{2} + 1) - 0(0+1) - \frac{1}{2}(\frac{1}{2} + 1)) = 0.}
$$

Note that we could have deduced this without any calculation, as the ground state(s) are spherically symmetric, and spin-orbit coupling does not impact such states. For the first excited state(s), the energy correction depends on the total angular momenta, as there are $$j = 3/2$$ and $$j = 1/2$$ sectors:

$$
\color{blue}{E^{(1)}_{j=3/2, j_z=\pm 3/2 \pm 1/2, l=1, s=1/2} = \frac{\hbar^2\omega^2}{2mc^2}(\frac{3}{2}(\frac{3}{2} + 1) - 1(1+1) - \frac{1}{2}(\frac{1}{2} + 1)) = \frac{\hbar^2\omega^2}{2mc^2}.}
$$

$$
\color{blue}{E^{(1)}_{j=1/2, j_z=\pm 1/2, l=1, s=1/2} = \frac{\hbar^2\omega^2}{2mc^2}(\frac{1}{2}(\frac{1}{2} + 1) - 1(1+1) - \frac{1}{2}(\frac{1}{2} + 1)) = -\frac{\hbar^2\omega^2}{mc^2}.}
$$

#### Identical Particles in an Infinite Cubic Well <a id="problem-qm-identicalcubicwell" name="problem-qm-identicalcubicwell"></a>
**Source:** UChicago 2014 Quantum Mechanics Graduate Diagnostic Exam Q3

**Problem Statement:** *(a) First, consider a single particle of mass $$m$$ in a three-dimensional box of dimensions $$L \times L \times L/4$$:*

\begin{equation}\label{eq:infcubicwell}
V(x, y, z) = \begin{cases} 
0 & \text{if } 0 \leq x \leq L, 0 \leq y \leq L, 0 \leq z \leq L/4 
\\ \infty & \text{otherwise.} 
\end{cases}
\end{equation}

*Find the three lowest energy eigenvalues and all the corresponding eigenfunctions of the particle in the box. Express all energies in units of $$\epsilon_0 = \frac{\hbar^2\pi^2}{2mL^2}$$.* 

*(b) Now suppose that we place three identical spin-0 particles in the box. For the combined system of three particles, find the two lowest eigenvalues of the total energy. Find the degeneracy associated with each of these eigenvalues (i.e. find the total number of distinct three-particle states corresponding to each eigenvalue).*

*(c) Repeat part (b) for spin-1/2 particles.*

*(d) Repeat part (b) for spin-1 particles.*

**Solution:** We can solve the problem independently in $$x, y, z$$ and then combine the eigenvalues/eigenfunctions to obtain the 3D solution. The eigenvalues and eigenfunctions of the 1-D infinite square well of length $$L$$ are $$E_n, \psi_n(x)$$ where:

$$
E_n = \frac{\hbar^2\pi^2 n^2}{2mL^2} = \epsilon_0 n^2
$$

$$
\psi_n(x) = \sqrt{\frac{2}{L}}\sin(\frac{n\pi x}{L})
$$

Thus the eigenvalues/eigenfunctions of the 3D cubic infinite square well are labelled by quantum numbers $$n_x, n_y, n_z$$, with:

$$
E_{n_x, n_y, n_z} = \epsilon_0 n_x^2+ \epsilon_0 n_y^2 + 16\epsilon_0 n_z^2
$$

$$
\psi_{n_x, n_y, n_z}(x, y, z) = \psi_{n_x}(x)\psi_{n_y}(y)\psi_{n_z}(4z) = 2\left(\frac{2}{L}\right)^{3/2}\sin(\frac{n_x\pi x}{L})\sin(\frac{n_y\pi y}{L})\sin(\frac{n_z 4 \pi z}{L})
$$

where $$n_i \in \mathbb{N}$$ and we note that the length is $$L/4$$ in the $$z$$-direction. From this, we can easily read off the three lowest eigenenergies to be $$\color{blue}{E_{1, 1, 1} = 18\epsilon_0, E_{2, 1, 1} = E_{1, 2, 1} = 19\epsilon_0, E_{2, 2, 1} = 20\epsilon_0}$$. With the respective eigenfunctions given in the equation above with the corresponding $$n_x, n_y, n_z$$.

(b) We first note the celebrated *spin-statistics theorem*, which tells us that bosons have integer spin and fermions have half-integer spin. Thus the spin-0 particles here are bosons, which can occupy the same quantum state. They each only have a single $$s = 0$$ spin state, and thus this does not enter into the degeneracy.

The lowest eigenvalue is with all three particles in the $$(n_x, n_y, n_z) = (1, 1, 1)$$ state, with a total energy of $$3 \cdot 18 \epsilon_0 = \color{blue}{54\epsilon_0}$$ with <span style="color:blue">no degeneracy</span>. The next lowest eigenvalue is with one particle in either $$(2, 1, 1)$$ or $$(1, 2, 1)$$ with the other two particles in the $$(1, 1, 1)$$ state, giving a total energy of $$2 \cdot 18\epsilon_0 + 19\epsilon_0 = \color{blue}{55\epsilon_0}$$. Since the particles are indistinguishable, the only choice is whether the more energetic particle is in $$(2, 1, 1)$$ or $$(1, 2, 1)$$ and thus this eigenvalue is <span style="color:blue">2-fold degenerate</span>.

(c) The spin-1/2 particles are fermions, which obey Pauli exclusion - hence any two particles cannot be in the same state. We also note that there is an additional quantum number for spin with $$s_z = \pm 1/2$$ - this does not affect the energy of the single-particle states, but will enter into our considerations of degeneracy.

The lowest eigenvalue is with one particle in $$(n_x, n_y, n_z, s_z) = (1, 1, 1, 1/2)$$, another in $$(1, 1, 1, -1/2)$$, and the last particle in one of $$(2, 1, 1, \pm 1/2)$$ or $$(1, 2, 1, \pm 1/2)$$. Hence the eigenvalue is $$\color{blue}{55\epsilon_0}$$ with <span style="color:blue">4-fold degeneracy</span>. The second lowest eigenvalue is $$\color{blue}{56\epsilon_0}$$, which has combinations of one particle in $$(1, 1, 1, \pm 1/2)$$, and the other two particles being in $$(2, 1, 1, \pm 1/2)$$ or $$(1, 2, 1, \pm 1/2)$$ states (so long as they are not in the same state). There are $$2 \cdot 6 = 12$$ possible choices in this way. Another possibility is for one particle in $$(1, 1, 1, 1/2)$$, the second in $$(1, 1, 1, -1/2)$$, and the last in $$(2, 2, 1, \pm 1/2)$$. There are 2 possible choices in this configuration. Thus in total this eigenvalue is <span style="color:blue">14-fold degenerate</span>.

(d) The spin-1 particles are bosons. They can occupy the same state, and have the spin quantum number $$s_z = -1, 0, 1$$. This again does not affect the energy of the single particle states, but will again enter in degeneracy counting.

The lowest eigenvalue is with all particles in $$(n_x, n_y, n_z, s_z) = (1, 1, 1, s_z)$$ states, with eigenvalue $$\color{blue}{54\epsilon_0}$$. The possibilities for the spins are all $$+1$$, all $$0$$, all $$-1$$, two $$+1$$/one $$0$$ or $$-1$$, two $$0$$/one $$+1$$ or $$-1$$, two $$-1$$/one $$+1$$ or $$0$$. Thus this eigenvalue is <span style="color:blue">9-fold degenerate</span>. The next lowest eigenvalue is $$\color{blue}{55\epsilon_0}$$. Here two particles are in $$(1, 1, 1, s_z)$$ and one particle is in $$(2, 1, 1, s_z)$$ or $$(1, 2, 1, s_z)$$. There are 6 choices for the excited particle (3 for the spin state, 2 for which of $$n_x, n_y$$ is 2) and 6 choices for the spin states of the ground state particles (both $$+1$$, both $$0$$, both $$-1$$, one $$+1$$/one $$0$$, one $$+1$$/one $$-1$$, one $$0$$/one $$-1$$) and by multiplying we find <span style="color:blue">36-fold degeneracy</span>.

#### Time-Varying Force <a id="problem-qm-timevaryforce" name="problem-qm-timevaryforce"></a>
**Source:** UChicago 2014 Quantum Mechanics Graduate Diagnostic Exam Q4

**Problem Statement:** *A one-dimensional harmonic oscillator of mass $$m$$ and frequency $$\omega$$ is in its ground state for $$t < 0$$. For $$t \geq 0$$ it is subject to a time-dependent but spatially constant force in the $$x$$-direction of $$F(t) = F_0\exp(-t/\tau)$$.*

*(a) Calculate the probability of finding the oscillator in the first excited state for $$t > 0$$ as a function of time $$t$$ to lowest order in $$F_0$$. You may need the creation and annihilation operators in terms of $$x$$ and $$p$$:*

\begin{equation}\label{eq:creationop}
    a = \sqrt{\frac{m\omega}{2\hbar}}x + i \frac{1}{\sqrt{2m\omega\hbar}}p
\end{equation}
\begin{equation}\label{eq:annihilationop}
    a^\dagger = \sqrt{\frac{m\omega}{2\hbar}}x - i \frac{1}{\sqrt{2m\omega\hbar}}p.
\end{equation}

*(b) The probability of finding the oscillator in the $$n$$th excited state for $$t > 0$$ is proportional to a power of $$F_0$$ for small $$F_0$$. What is that power?*

**Solution:** (a) First recalling that $$F = -\frac{\partial V}{\partial x}$$ for a conservative force, we have that a time-dependent potential of $$V(t) = -F_0x\exp(-t/\tau)$$ can give rise to $$F(t)$$. To first order in perturbation theory, the transition probability to the first excited state as a function of time $$t$$ is given by:

$$
p_{0 \to 1}(t) = \lvert \int_{0}^t \langle 1 \vert V(t') \vert 0 \rangle e^{-i\omega_{0, 1}t'} dt' \rvert^2
$$

The difference in energy between the ground state and first excited state is $$E_{0, 1} = \frac{3}{2}\hbar\omega - \frac{1}{2}\hbar\omega = \hbar\omega$$ and so the characteristic frequency between the two states is just the frequency of the oscillator $$\omega{0, 1} = \frac{E_{0, 1}}{\hbar} = \omega$$. To evaluate the matrix element, we first note that (inverting the definitions of the creation/annihilation operators):

$$
x = \sqrt{\frac{\hbar}{2m\omega}}(a + a^\dagger)
$$

and so:

$$
\langle 1 \vert V(t') \vert 0 \rangle =  -F_0\exp(-t'/\tau) \langle 1 \rvert x \lvert 0 \rangle = -F_0\exp(-t'/\tau)\sqrt{\frac{\hbar}{2m\omega}} \langle 1 \rvert (a + a^\dagger) \lvert 0 \rangle = -F_0\exp(-t'/\tau)\sqrt{\frac{\hbar}{2m\omega}}
$$

Thus the transition probability becomes:

$$
p_{0 \to 1}(t) =  \frac{F_0^2\hbar^2}{2m\omega} \lvert \int_{0}^t \exp(-(i\omega + \frac{1}{\tau})t') dt' \rvert^2
$$

Carrying out the integral:

$$
p_{0 \to 1}(t) =  \frac{F_0^2\hbar^2}{2m\omega} \lvert \frac{exp(-(i\omega + \frac{1}{\tau})t) - 1}{i\omega + \frac{1}{\tau}} \rvert^2
$$

Computing the modulus squared we conclude:

$$
\color{blue}{p_{0 \to 1}(t) = \frac{F_0^2\hbar^2\tau^2}{2m\omega}\frac{1 - 2\exp(-t/\tau)\cos(\omega t) + \exp(-2t/\tau)}{\tau^2\omega^2 + 1}}
$$

(b) Now considering higher-order perturbation theory, the transition amplitude to the $$\lvert n \rangle$$ state only becomes nonvanishing at $$n$$th order (as each order can raise the energy by one level). Each order picks up a factor of $$F_0$$ in the amplitude and thus the dependency of the probability is $$\color{blue}{F_0^{2n}.}$$


#### Two Interacting Fermions <a id="problem-qm-twofermions" name="problem-qm-twofermions"></a>
**Source:** MIT Fall 2015 Doctoral General Examination Quantum Q2

**Problem Statement:** *Consider two identical fermions of mass $$m$$ interacting with each other through an attractive harmonic potential. The Hamiltonian is*

\begin{equation}\label{eq:twofermions}
    H = \frac{\mathbf{p}_1^2}{2m} + \frac{\mathbf{p}_2^2}{2m} + \frac{k}{2}(\mathbf{x}_1 - \mathbf{x}_2)^2
\end{equation}

*$$\mathbf{x}_{1, 2}$$ are the coordinates of the two fermions, and $$\mathbf{p}_{1,2}$$ are the conjugate momenta. For simplicity assume that the spins of both fermions are polarized in the same direction (e.g, in the $$\uparrow$$ direction) so that we may ignore the spin degree of freedom.*

*(a) State the restriction imposed by Fermi statistics on acceptable wave functions $$\psi(\mathbf{x}_1, \mathbf{x}_2)$$ of this system.*

*(b) Rewrite $$H$$ in terms of center-of-mass and relative coordinates.*

*(c) Ignoring the restriction imposed by Fermi statistics what is the ground state energy? What is the energy of the first excited bound state?*

*(d) Including the effects of Fermi statistics what is the ground state energy? What is the degeneracy of the ground state?*

**Solution:** (a) Fermi statistics dictate that the wavefunction must have odd parity/be antisymmetric under exchange of the particles, and therefore:

$$
\color{blue}{\psi(\mathbf{x}_1, \mathbf{x}_2) = -\psi(\mathbf{x}_2, \mathbf{x}_1)}
$$

(b) We define the center of mass and relative coordinates $$\mathbf{R} = \frac{m\mathbf{r}_1 + m\mathbf{r}_2}{m + m} = \frac{\mathbf{r}_1 + \mathbf{r}_2}{2}$$ and $$\mathbf{r} = \mathbf{r}_1 - \mathbf{r}_2$$. We also have the conjugate center of mass and relative momenta of $$\mathbf{P} = \mathbf{p}_1 + \mathbf{p}_2$$ and $$\mathbf{p} = \frac{\mathbf{p}_1 - \mathbf{p}_2}{2}$$, which inverting we obtain $$\mathbf{p}_1 = \frac{\mathbf{P} + 2\mathbf{p}}{2}$$ and $$\mathbf{p}_2 = \frac{\mathbf{P} - 2\mathbf{p}}{2}$$, and thus we can rewrite $$H$$ as:

$$
\color{blue}{H = \frac{\mathbf{P}^2}{4m} + \frac{\mathbf{p}^2}{m} + \frac{k}{2}\mathbf{r}^2}
$$

(c) The Hamiltonian decouples into $$H = H_{cm} + H_{rel}$$ where $$H_{cm}$$ is the Hamiltonian of a free particle with mass $$2m$$ and $$H_{rel}$$ is the Hamiltonian of a particle of mass $$\frac{m}{2}$$ in a 3-D harmonic oscillator potential with spring constant $$k$$. The former has unbounded spectrum $$E_{cm} = \in [0, \infty)$$ and for simplicity we assume that $$E_{cm} = 0$$ for the rest of the problem. The latter has quantized spectrum $$E_{n_x, n_y, n_z} = \frac{3}{2}\hbar\omega(n_x + n_y + n_z + \frac{3}{2})$$ (as $$H_{rel}$$ can be decomposed into 3 1-D simple harmonic oscillators, each with energy $$E_n = \frac{\hbar}\omega(n + \frac{1}{2})$$), with $$\omega = \sqrt{\frac{2k}{m}}$$. Ignoring the restriction from Fermi statistics, the ground state is then the state with $$n_x = n_y = n_z = 0$$ and has energy $$\color{blue}{\frac{3}{2}\hbar\omega}$$. The excited state has one $$n_i = 1$$ and the other two zero, with energy $$\color{blue}{\frac{5}{2}\hbar\omega}$$.

(d) Including the effects of fermionic exchange statistics, the answer to (c) changes. To this end, we note that the eigenstates of the SHO are eigenstates of parity (this follows as $$H$$ is quadratic in the $$x, p$$ quadrature operators and thus $$[\Pi, H] = 0$$), and in particular (recalling the parity of the Hermite polynomials/wavefunctions, or thinking about the parity of raising operators as is done in <a href="#problem-qm-symmetryamplitudes" name="#problem-qm-symmetryamplitudes"> Symmetries and Transition Amplitudes </a>) $$\Pi\lvert n \rangle = (-1)^n\lvert n \rangle$$. In 3-D this generalizes $$\Pi\lvert n_x, n_y, n_z \rangle = (-1)^{n_x + n_y + n_z} \lvert n_x, n_y, n_z \rangle$$. Since fermionic exchange statistics requires that the acceptable states of this system have odd parity, the $$n_x = n_y = n_z$$ state from (c) with even parity is forbidden. The ground states are instead those with one $$n_i = 1$$ and the other two zero (these have odd parity), with energy $$\color{blue}{\frac{5}{2}\hbar\omega}$$. The ground space is thus <span style="color:blue">3-fold degenerate</span>.

Note: We could reach the same conclusion by observing that the eigenstates of the 3-D harmonic oscillator are eigenstates of angular momentum (see <a href="#problem-qm-spinorbitqho" name="#problem-qm-spinorbitqho"> Spin-Orbit Coupling in the 3-D Harmonic Oscillator </a> for more discussion) and can be labelled by quantum numbers $$l, m$$. We also recall that the angular momentum eigenstates are eigenstates of parity $$\Pi\lvert l, m \rangle = (-1)^l\lvert l, m \rangle$$, thus the fermionic exchange statistics/antisymmetric wavefunction forbids $$l = 0$$ and the ground state(s) consist of the 3-fold degenerate $$l = 1$$ subspace with $$E = \frac{5}{2}\hbar\omega$$.

#### A Quantum Spin Chain <a id="problem-qm-spinchain" name="problem-qm-spinchain"></a>
**Source:** MIT Fall 2012 Doctoral General Examination Quantum Q1

**Problem Statement:** 

**Solution:**

#### Anomalous Magnetic Moment of the Electron <a id="problem-qm-emagmoment" name="problem-qm-emagmoment"></a>
**Source:** MIT Fall 2012 Doctoral General Examination Quantum Q2

**Problem Statement:**

**Solution:**

#### A Heisenberg Ferromagnet <a id="problem-qm-heisenbergferro" name="problem-qm-heisenbergferro"></a>
**Source:** MIT Spring 2012 Doctoral General Examination Quantum Q1

**Problem Statement:**

**Solution:**

#### The Supersymmetric Method <a id="problem-qm-susy" name="problem-qm-susy"></a>
**Source:** MIT Spring 2012 Doctoral General Examination Quantum Q2

**Problem Statement:**

**Solution:**

#### Spin-1/2 in Time-Dependent Magnetic Field <a id="problem-qm-timedepmag" name="problem-qm-timedepmag"></a>
**Source:** MIT Fall 2002 Doctoral General Examination Quantum Q2

**Problem Statement:**

**Solution:**

#### Particle on a 1-D Lattice <a id="problem-qm-onedlattice" name="problem-qm-onedlattice"></a>
**Source:** MIT Spring 2002 Doctoral General Examination Quantum Q1

**Problem Statement:**

**Solution:**

#### Spin-1/2 and Stern-Gerlach <a id="problem-qm-spinhalfsg" name="problem-qm-spinhalfsg"></a>
**Source:** MIT Spring 2001 Doctoral General Examination Quantum Q1

**Problem Statement:** *Consider a spin-1/2 particle where $$S_j = \frac{\hbar}{2}\sigma_j$$ and*

\begin{equation}\label{eq:paulis}
    \sigma_x = \left( \begin{array}{cc} 0 & 1 \\ 1 & 0\end{array} \right) \quad \sigma_y = \left( \begin{array}{cc} 0 & -i \\ i & 0\end{array} \right) \quad \sigma_z = \left( \begin{array}{cc} 1 & 0 \\ 0 & -1\end{array} \right)
\end{equation}

*(a) The operator along the $$\hat{n} = (\sin\theta\cos\phi, \sin\theta\sin\phi, \cos\theta)$$ direction is:*

\begin{equation}\label{eq:Sn}
    S_{\hat{n}} = n_xS_x + n_yS_y + n_zS_z.
\end{equation}

*Find the eigenvalues of $$S_{\hat{n}}$$ and the associated eigenvectors.*

*(b) Is it possible for a spin-1/2 particle to be in a state $$\lvert\psi\rangle$$ such that:*

$$
\langle \psi \rvert S_x \lvert \psi \rangle = \langle \psi \rvert S_y \lvert \psi \rangle = \langle \psi \rvert S_z \lvert \psi \rangle = 0?
$$

*If it is possible, find $$\lvert \psi \rangle$$. If it is not, show why.*

*(c) A beam of spin-1/2 particles enters a Stern-Gerlach filter which allows only particles whose spin is $$+\frac{\hbar}{2}$$ along the $$z$$ direction to pass. the particles then pass through a region where there is a magnetic field $$\mathbf{B} = (0, B, 0)$$ and spend time $$T$$ in this region. Then the particles enter a Stern-Gerlach filter which allows only particles whose spin is $$+\frac{\hbar}{2}$$ along the $$x$$ direction to pass. What fraction of the electrons which exit the first filter exit the second? Assume that the particles interact with the magnetic field via $$H = -\sum_j B_jS_j$$.* 

**Solution:** (a) We first calculate:

$$
S_{\hat{n}} = \frac{\hbar}{2}\begin{pmatrix} \cos\theta & \sin\theta e^{-i\phi} \\ \sin\theta e^{i\phi} & -\cos\theta \end{pmatrix}.
$$

Then if $$\lambda_+, \lambda_-$$ are the two eigenvalues of $$S_{\hat{n}}$$, we have $$\det S_{\hat{n}} = -\frac{\hbar^2}{4} = \lambda_+\lambda_-$$ and $$\text{Tr}S_{\hat{n}} = 0 = \lambda_+ + \lambda_-$$ from which we conclude that $$\color{blue}{\lambda_\pm = \pm \frac{\hbar}{2}}$$. 

We now solve for the eigenvectors, which obey $$\hat{S}_{\hat{n}}\lvert \pm \hat{n} \rangle = \pm\frac{\hbar}{2}\lvert \pm \hat{n} \rangle$$ and so:

$$
\begin{pmatrix} x\cos\theta + y\sin\theta e^{-i\phi} \\ x\sin\theta e^{i\phi} - y\cos\theta \end{pmatrix} = \pm \begin{pmatrix} x \\ y \end{pmatrix}
$$

where $$x, y$$ are the entries of the eigenvectors. Since the global phase of a state is irrelevant, WLOG we can take $$x$$ to be real and set $$x = \cos\alpha$$. Then by normalization we have $$\lvert y \rvert = \sin\alpha$$ and so $$y = e^{i\beta}\sin\alpha$$ including the relative phase. Thus the above equations become:

$$
\begin{pmatrix} \cos\alpha\cos\theta + e^{i\beta}\sin\alpha\sin\theta e^{-i\phi} \\ \cos\alpha\sin\theta e^{i\phi} - e^{i\beta}\sin\alpha\cos\theta \end{pmatrix} = \pm \begin{pmatrix} \cos\alpha \\ e^{i\beta}\sin\alpha \end{pmatrix}
$$
The only choice of $$\beta$$ that satisfies the above equations is $$\beta = \phi$$. The above then reduces to:

$$
\begin{pmatrix} \cos(\theta - \alpha) \\ \sin(\theta - \alpha) \end{pmatrix} = \pm \begin{pmatrix} \cos\alpha \\ \sin\alpha \end{pmatrix}
$$

Which is satisfied by $$\alpha = \frac{\theta}{2}$$ for the $$+$$ case and $$\alpha = \frac{\theta}{2} + \pi$$ for the $$-$$ case, and hence:

$$
\color{blue}{\lvert +\hat{n} \rangle = \begin{pmatrix} \cos(\frac{\theta}{2}) \\ e^{i\phi}\sin(\frac{\theta}{2}) \end{pmatrix} \quad \lvert -\hat{n} \rangle = \begin{pmatrix} -\sin(\frac{\theta}{2}) \\ e^{i\phi}\cos(\frac{\theta}{2}) \end{pmatrix}.}
$$

(b) <span style="color:blue">Such a state cannot exist.</span> Suppose for the sake of contradiction that such a $$\lvert \psi \rangle$$ did - since all spin-1/2 pure states can be case in the form of $$\lvert + \hat{n} \rangle$$ for appropriate choices of $$\theta, \phi$$ (and possible adjustment of the global phase) it follows that there exists some $$\hat{n}$$ for which $$\langle \psi \rvert S_{\hat{n}}\lvert \psi \rangle = \frac{\hbar}{2} \langle \psi \lvert \psi \rangle \frac{\hbar}{2}$$. But then:

$$
\frac{\hbar}{2} = \langle \psi \rvert S_{\hat{n}}\lvert \psi \rangle = n_x\langle \psi \rvert S_x \lvert \psi \rangle + n_y \langle \psi \rvert S_y \lvert \psi \rangle + n_z \langle \psi \rvert S_z \lvert \psi \rangle = n_x \cdot 0 + n_y \cdot 0 + n_z \cdot 0 = 0
$$

which is a contradiction.

(c) The particles coming out of the first apparatus are $$\lvert \uparrow \rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$. In the magnetic field region we have the time-evolution operator (for a constant Hamiltonian):

$$
U(T) = \exp(-\frac{iHT}{\hbar}) = \exp(-\frac{i(-BS_y)T}{\hbar}) = \exp(\frac{BT \sigma_y}{2}) = \cos(\frac{BT}{2}) + i\sin(\frac{BT}{2})\sigma_y
$$

where the last equality can be obtained by expanding out the exponential in a Taylor series, grouping the odd and even terms, and noting that $$\sigma_y^2 = 1$$. Applying this to the initial state we have:

$$
\lvert\psi(T)\rangle = U(T)\lvert\uparrow\rangle = \cos(\frac{BT}{2})\lvert \uparrow \rangle + i\sin(\frac{BT}{2})(i\lvert\downarrow\rangle) = \begin{pmatrix} \cos(\frac{BT}{2}) \\ -\sin(\frac{BT}{2}) \end{pmatrix}.
$$

The probability that we measure $$S_x = +\frac{\hbar}{2}$$ in the second filter is given by the Born rule to be:

$$
P_+ = \lvert \langle +x \vert \psi(T) \rangle \rvert^2 = \lvert \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \end{pmatrix}  \begin{pmatrix} \cos(\frac{BT}{2}) \\ -\sin(\frac{BT}{2}) \end{pmatrix} \rvert^2 = \frac{1 - 2\cos(\frac{BT}{2})\sin(\frac{BT}{2})}{2}
$$

where we use that $$\lvert + x \rangle = \frac{\lvert \uparrow \rangle + \lvert \downarrow \rangle}{\sqrt{2}}$$. The above is precisely the fraction of particles that passes through the second filter relative to the first, and hence:

$$
\color{blue}{P_+ = \frac{1 - \sin(BT)}{2}.}
$$

#### Harmonic Oscillator and Translation <a id="problem-qm-qhotrans" name="problem-qm-qhotrans"></a>
**Source:** MIT Spring 2001 Doctoral General Examination Quantum Q2

**Problem Statement:** *A particle with mass $$m=1$$ is in the ground state of a harmonic oscillator with Hamiltonian*

\begin{equation}\label{eq:sho}
    H = \frac{1}{2}(p^2 + \omega^2x^2)
\end{equation}

*The state is translated a distance $$d$$ while $$H$$ is left alone.*

*(a) What is the probability that a measurement of the energy will yield the value $$\hbar\omega(j + \frac{1}{2})$$? You may find the following formulas useful:*

\begin{equation}\label{eq:annihilation}
    a = \frac{1}{\sqrt{2\hbar\omega}}(\omega x + ip) \quad \lvert n \rangle = \frac{(a^\dagger)^n}{\sqrt{n!}}\lvert 0 \rangle
\end{equation}

*and also if $$A, B$$ are two operators such that $$[A, B]$$ is proportional to a unit operator, then*

\begin{equation}\label{eq:opexponential}
    e^{A + B} = e^Ae^B + e^{-\frac{1}{2}[A, B]}.
\end{equation}

*At $$t= 0$$ th equantum system is prepared in the translated state described above. It then evolves according to the Schrodinger equation with the Hamiltonian $$H$$*.

*(b) Supose that at the time $$t$$ the momentum is measured. At what values of $$t$$ wil the probability distribution for getting any value of the momentum be identical to the $$t = 0$$ probability distribution?*

*(c) Repeat (b) with momentum measurement replaced by energy measurement.*

**Solution:** (a) We first note that the translation operator by distance $$d$$ is given by $$T(d) = e^{-\frac{ipd}{\hbar}}$$ recalling momentum as the generator of translations. We also can express $$p$$ in terms of $$a, a^\dagger$$:

$$
p = i\sqrt{\frac{\hbar\omega}{2}}(a^\dagger - a)
$$

We also calculate $$[a^\dagger, a]$$:

$$
[a^\dagger, a] = [\frac{1}{\sqrt{2\hbar\omega}}(\omega x - ip), \frac{1}{\sqrt{2\hbar\omega}}(\omega x + ip)] = \frac{1}{2\hbar\omega}([\omega x, \omega x] + [\omega x, ip] - [ip, \omega x] - [ip, ip]) = \frac{1}{2\hbar\omega}(0 + \omega i (i\hbar) - \omega i (-i\hbar) + 0) = -1
$$

Thus Eq. \eqref{eq:opexponential} applies. Now calculating the probability of measuring $$E_j = \hbar\omega(j + \frac{1}{2})$$ using the Born rule, we have:

$$
p(j) = \lvert \langle j \rvert e^{-\frac{ipd}{\hbar}} \lvert 0 \rangle \rvert^2 = \lvert \langle j \rvert e^{\sqrt{\frac{\omega d^2}{2\hbar}}(a^\dagger - a)} \lvert 0 \rangle \rvert^2
$$

For brevity let us define $$\alpha = \sqrt{\frac{\omega d^2}{2\hbar}}$$. Then using Eq. \eqref{eq:opexponential} with $$A = \alpha a^\dagger$$ and $$B = -\alpha a$$ (and $$[\alpha a^\dagger, -\alpha a] = -\alpha^2 [a^\dagger, a] = \alpha^2$$) we obtain:

$$
p(j) = \lvert \langle j \rvert e^{\alpha a^\dagger}e^{-\alpha a}e^{-\frac{\alpha^2}{2}}\lvert 0 \rangle \rvert^2
$$

Now, since $$a\lvert 0 \rangle = 0$$, when expanding $$e^{-\alpha a}$$ in a power series all term vanish except the $$n = 0$$ identity term. Therefore the above reduces to:

$$
p(j) = e^{-\alpha^2} \lvert \langle j \rvert  e^{\alpha a^\dagger} \lvert 0 \rangle \rvert^2
$$

Since $$\lvert j \vert i \rangle = \delta_{ji}$$ the only term of the above that survives when expanding $$e^{\alpha a^\dagger}$$ in a power series is the $$n = j$$ term, so:

$$
p(j) =  e^{-\alpha^2} \lvert \langle j \rvert \frac{(\alpha a^\dagger)^j}{j!} \lvert 0 \rangle \rvert^2 = e^{-\alpha^2} \lvert \langle j \rvert \frac{\alpha^j}{\sqrt{j}!} \lvert j \rangle \rvert^2
$$

Thus we conclude:

$$
\color{blue}{p(j) = \frac{e^{-\alpha^2}\alpha^{2j}}{j!}}
$$

(b) Let us study the time evolution of the state (which starts in $$\lvert\psi(0) \rangle = e^{-\frac{ipd}{\hbar}}\lvert 0 \rangle$$):

$$
\lvert \psi(t) \rangle = \exp(-iHt)\lvert \psi(0) \rangle = \left(\sum_{n}e^{-i\frac{\hbar\omega(n + \frac{1}{2})}{\hbar}t} \lvert n \rangle \langle n \rvert \right)\lvert\psi(0) \rangle = \sum_{n}e^{-i\omega nt}\langle n \lvert\psi(0) \rangle \lvert n \rangle 
$$

where in the last equality we discard the global phase factor $$e^{-i\omega t/2}$$ as this does not affect the measurement statistics. Looking at the above, the $$t = 0$$ measurement probabilities of momentum (and any other observable) is reproduced when $$e^{-i\omega nt} = 1$$, i.e. when:

$$
\color{blue}{t = \frac{2\pi m}{\omega}, \quad m \in \mathbb{N}.}
$$

(c) Since $$H$$ commutes with itself, the energy is conserved through the time evolution and thus <span style="color:blue">the probability for measuring a given energy is constant in time.</span>