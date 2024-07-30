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
- <a href="#problem-qm-timedepmag" name="#problem-qm-timedepmag"> Spin-1/2 in Time-Dependent Magnetic Field </a>
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
\langle \psi_f \rvert S^\dagger U(t) S - U(t)\lvert \psi_i \rangle = \langle \psi_f \rvert S^\dagger U(t) S \lvert \psi_i \rangle - \langle \psi_f \rvert U(t)\lvert \psi_i \rangle = (e^{i(\phi_{i} - \phi_f)} - 1)\langle \psi_f \rvert U(t)\lvert \psi_i \rangle
$$

Thus:

$$
0 = (e^{i(\phi_{i} - \phi_f)} - 1)\langle \psi_f \rvert U(t)\lvert \psi_i \rangle
$$

so unless $$\phi_i = \phi_f$$ then $$\color{blue}{\langle\psi_f \rvert U(t)\lvert \psi_i \rangle = 0.}$$

(b) Note that applying spatial inversion twice amounts to doing nothing; $$P^2(x) = P\circ P(x) = P(-x) = x$$ (and analogously for $$p$$) and so $$P^2 = I$$. Hence the square of the eigenvalues of $$P$$ are $$\lambda^2 = 1$$ and hence $$\color{blue}{\lambda = \pm 1}$$. Next, note the definition of the raising operator $$a^\dagger$$:

$$
  a^\dagger = \sqrt{\frac{m\omega}{2}}(x - i\frac{p}{m\omega}).
$$

$$a^\dagger$$ is linear in $$x, p$$ and so $$Pa^\dagger = -a^\dagger$$, and more generally $$P (a^\dagger)^n = (-1)^n (a^\dagger)^n$$. Noting that $$\ket{0}$$ has even parity (its wavefunction is a Gaussian symmetric about $$x = 0$$), the parity of $$\ket{n} = \frac{1}{\sqrt(n+1)!}(a^\dagger)^n\ket{0}$$ is therefore $\color{blue}{(-1)^n}$.

Next, note that $$V_4 = \alpha x^4$$ commutes with $$P$$ as it is even in $$x$$. Therefore, $$[P, H_{\text{SHO}} + V_4] = 0$$ and since the ground state $$\ket{0}$$ and first excited state $$\ket{1}$$ of the harmonic oscillator have different parities, by our result in (a) <span style="color:blue">the transition amplitude vanishes.</span>

#### Thermal States <a id="problem-qm-thermalstates" name="problem-qm-thermalstates"></a>
**Source:** UBC PHYS 500 2023 HW3 Q1

**Problem Statement:** *Consider a single electron spin (spin-1/2) in a magnetic field with Hamiltonian:*

$$
H = -g\mu_B B S_z
$$

*where $$g$$ is the g-factor of the spin, $$\mu_B$$ is the Bohr magneton, $$B$$ is the magnetic field (here in the $$z$$-direction) and $$S_z = \frac{1}{2}\sigma_z$$ is the $$z$$-component of spin (with $$\hbar = 1$$).*

*(a) What is the the expected $$z$$-magnetization, $$m = \langle S_z \rangle = \langle \frac{1}{2}\sigma_z \rangle$$ for a thermal equilibrium state of the spin at temperature $$T$$?*

*(b) Compute the spin suceptibility $$\chi = \frac{\partial m}{\partial B}$$ as a function of temperature. How does this quantity behave asymptotically in the extreme limits of $$T \to 0, \infty$$?*

*(c) Compute the entropy as a function of temperature. Compute and explain the limiting value of the entropy in the extreme limits of $$T \to 0, \infty$$?*

**Solution:** The thermal equilibrium state is given by (working in units with $$ = 1$$):

$$
\rho_T = \frac{e^{-H/T}}{Z} = \frac{1}{e^{-\frac{g\mu_B B}{T}} + e^{\frac{g\mu_B B}{T}}}\begin{pmatrix} e^{\frac{g\mu_B B}{T}} & 0 \\ 0 & e^{-\frac{g\mu_B B}{T}} \end{pmatrix} = \frac{1}{2\cosh(\frac{g\mu_B B}{T})} \begin{pmatrix} e^{\frac{g\mu_B B}{T}} & 0 \\ 0 & e^{-\frac{g\mu_B B}{T}}\end{pmatrix}.
$$

From this we can easily compute the $$z$$-magnetization:

$$
m = \langle \frac{1}{2}\sigma_z \rangle = \text{Tr}(\frac{1}{2}\sigma_z\rho_T) =  \frac{1}{4\cosh(\frac{g\mu_B B}{T})}\text{Tr}\left(\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}  \begin{pmatrix} e^{\frac{g\mu_B B}{T}} & 0 \\ 0 & e^{-\frac{g\mu_B B}{T}}\end{pmatrix} \right) = \frac{1}{4\cosh(\frac{g\mu_B B}{T})}(e^{\frac{g\mu_B B}{T}} - e^{-\frac{g\mu_B B}{T}})
$$

so we conclude:

$$
\color{blue}{m = \frac{1}{2}\tanh(\frac{g\mu_B B}{T}).}
$$

(b) Computing the susceptibility we have:

$$
\color{blue}{\chi = \frac{\partial m}{\partial B} = \frac{g\mu_B}{2T}\text{sech}^2\left(\frac{g\mu_B B}{T}\right)}
$$

where we use that $$\partial_x \tanh(x) = \text{sech}^2(x)$$ and the chain rule. In the $$T \to \infty$$ limit, we note first that $$\lim_{T \to \infty}\text{sech}(\frac{g\mu_B B}{T}) \sim \frac{1}{4}$$ and so:

$$
\color{blue}{\lim_{T \to \infty}\chi \sim \frac{g\mu_B}{32T}}
$$

and the magnetization drops to 0 as $$\sim 1/T$$. in the $$T \to 0$$ limit, $$\lim_{T \to 0}\sech(\frac{g\mu_B B}{T}) \sim \frac{e^{-\frac{g\mu_B B}{T}}}{2}$$ and so:

$$
\color{blue}{\lim_{T \to 0}\chi \sim \frac{g\mu_B}{8T}e^{-\frac{2g\mu_B B}{T}}}
$$

so the magnetization drops exponentially quickly to 0.

(c) We recall the entropy of a quantum state is given by $$S(\rho) = -\text{Tr}(\rho\log \rho) = - \sum_i \lambda_i \log \lambda_i$$ with $$\lambda_i$$ the eigenvalues of $$\rho$$. Therefore:

$$
S(\rho_T) = -\frac{e^{\frac{g\mu_B B}{T}}}{Z}\log(\frac{e^{\frac{g\mu_B B}{T}}}{Z}) -\frac{e^{-\frac{g\mu_B B}{T}}}{Z}\log(\frac{e^{-\frac{g\mu_B B}{ T}}}{Z}) = \frac{\log(Z)}{Z}\left(e^{\frac{g\mu_B B}{ T}} + e^{-\frac{g\mu_B B}{T}}\right) -\frac{1}{Z}\frac{g\mu_B B}{T}\left(e^{\frac{g\mu_B B}{T}} - e^{-\frac{g\mu_B B}{T}}\right)
$$

which with $$Z = 2\cosh(\frac{g\mu_B B}{T})$$ becomes:

$$
\color{blue}{S(\rho_T) = \log(2) + \log(\cosh(\frac{g\mu_B B}{T})) - \frac{g\mu_B B}{T}\tanh(\frac{g\mu_B B}{T})}
$$

In the $$T \to \infty$$ limit the second/third terms go to zero and we have:

$$
\color{blue}{\lim_{T \to \infty} S(\rho_T) = \log(2).}
$$

This makes sense as at infinite temperature both of the spin states are equally favoured and hence the quantum state is maximally mixed, thus yielding the maximal 1-spin entropy of $$\log(2)$$. The $$T \to 0$$ limit must be taken more carefully as both terms diverge; letting $$x = \frac{T}{g\mu_B B}$$ we find:

$$
\lim_{x \to 0}  \log(\cosh(\frac{1}{x})) - \frac{1}{x}\tanh(\frac{1}{x}) = \lim_{x \to 0} \log(\frac{e^{\frac{1}{x}}}{2}) - \frac{1}{x}\frac{e^{\frac{1}{x}}}{e^{\frac{1}{x}}} = \lim_{x \to 0} \log(e^{\frac{1}{x}}) - \log(2) - \frac{1}{x} = -\log(2)
$$

Thus:

$$
\color{blue}{\lim_{T \to 0}S(\rho_T) = 0.}
$$

This also makes sense, as at $$T = 0$$ the thermal equilibrium is simply the pure ground state $$\lvert \uparrow \rangle$$ which has no entropy.

#### Scattering of Identical Particles <a id="problem-qm-identicalscattering" name="problem-qm-identicalscattering"></a>
**Source:** UBC PHYS 500 2023 HW6 Q4

**Problem Statement:** *Consider two particles of mass $$m$$, interacting by the Yukawa potential:*
\begin{equation}\label{eq:yukawa}
    V(r) = \frac{e^{-\kappa r}}{r}
\end{equation}
*where $$r = \lvert \vec{r}_1 - \vec{r}_2 \rvert^2$$ is the distance between the two particles. Denote the initial momenta of the particles as $$\pm k \hat{z}$$ where $$\hat{z}$$ is the unit vector in the $$z$$-direction. Find the differential cross section $$\frac{d\sigma}{d\Omega}$$ for particles to scatter into a thin shell of solid angle $$d\Omega = \sin\theta d\theta$$ around the final momenta $$\pm \vec{k}_f$$, where $$\vec{k}_f$$ has angle $$\theta$$ from the $$z$$-axis. Express your final answer in terms of $$k, m \theta$$. Compute separately for the case of (spin-less or spin-polarized) bosons and fermions. Comment on the effect of identical particle statistics for the case $$\theta = \pi/2$$. The Fourier transform of the Yukawa potential may be useful:*
\begin{equation}\label{eq:yukawaft}
    \tilde{V}(\vec{q}) = \int d^3r e^{-i\vec{q} \cdot \vec{r}}V(r) = \frac{4\pi}{q^2 + \kappa^2}.
\end{equation}

**Solution:** The state corresponding to the particles with momenta $$\vec{k}_1, \vec{k}_2$$ is given by:

$$
\lvert \psi(\vec{k}_1, \vec{k}_2) \rangle = \lvert \vec{k}_1, \vec{k}_2 \rangle + \zeta \lvert \vec{k}_2, \vec{k}_1 \rangle
$$

where $$\zeta = \pm 1$$ accounts for the particle exchange statistics (1 for bosons, -1 for fermions). Expanding out the above in the position basis:

$$
\lvert \psi(\vec{k}_1, \vec{k}_2) \rangle = \int d^3r_1 d^3r_2 \frac{1}{L^3\sqrt{2}}\left(e^{i\vec{k}_1 (\vec{r}_1 - \vec{r}_2)} + \zeta e^{-i\vec{k}_2(\vec{r}_1 - \vec{r}_2)}\right)\lvert r_1, r_2 \rangle
$$

The initial state is the above with $$\vec{k}_1 = \vec{k}_i = k\zhat, \vec{k}_2 = -\vec{k}_i = -k\zhat$$ and the final state is the above with $$\vec{k}_1 = \vec{k}_f, \vec{k}_2 = -\vec{k}_f$$. The scattering matrix element is:

$$
M(\vec{k}_f, \vec{k}_i) = \langle \psi(\vec{k}_f, -\vec{k}_f) \rvert V(\vec{r}_1 - \vec{r}_2) \lvert \psi(\vec{k}_i, -\vec{k}_i) \rangle
$$

as an integral this takes the form:

$$
M(\vec{k}_f, \vec{k}_i) = \int d^3r_1 d^3r_2 \frac{1}{2L^6}\left[e^{i(\vec{k}_f - \vec{k}_i) \cdot (\vec{r}_1 - \vec{r}_2)} + c.c. + \zeta e^{i(\vec{k}_f + \vec{k}_i) \cdot (\vec{r}_1 - \vec{r}_2)} + c.c.]V(\vec{r}_1 - \vec{r}_2)
$$

with c.c. denoting the complex conjugate. If we convert to center of mass $$\vec{R} = \frac{\vec{r}_1 + \vec{r}_2}{2}$$ and relative coordinates $$\vec{r} = \vec{r}_1 - \vec{r}_2$$, the above simplifies significantly:

$$
M(\vec{k}_f, \vec{k}_i) = \int \frac{d^3R}{L^3} \frac{d^3r}{2L^3}\left[e^{i(\vec{k}_f - \vec{k}_i) \cdot \vec{r}} + c.c. + \zeta e^{i(\vec{k}_f + \vec{k}_i)\cdot \vec{r}} + c.c.]V(\vec{r}).
$$

The integral over $$R$$ yields one as the integrand is independent of $$R$$, and the leftover integrals are simply the fourier transform of $$V$$:

$$
M(\vec{k}_f, \vec{k}_i) = \frac{1}{2}\left(\tilde{V}(\vec{k}_f - \vec{k}_i) + \tilde{V}(\vec{k}_f - \vec{k}_i) + 2\zeta\tilde{V}(\vec{k}_f + \vec{k}_i)\right)
$$

Up until this point the discussion has been for a totally general potential $$V/\tilde{V}$$. However, using the Hint we see that $$\tilde{V}(\vec{q})$$ for the Yukawa potential only depends on the magnitude of the momenta, and so the above simplifies even further:

$$
M(\vec{k}_f, \vec{k}_i) = \tilde{V}(\lvert \vec{k}_f - \vec{k}_i\rvert) + \zeta\tilde{V}(\lvert \vec{k}_f + \vec{k}_i \rvert)
$$

Since the scattering is elastic, $$\lvert \vec{k}_f \rvert = \lvert \vec{k}_i \rvert$$ and hence:

$$
\lvert \vec{k}_f \pm \vec{k}_i \rvert = k\sqrt{2(1\pm \cos\theta)} = \begin{cases} 2k\cos(\theta/2) & (+) \\ 2k\sin(\frac{\theta}{2}) & (-) \end{cases}
$$

where $$\theta$$ is the angle between the initial and final momenta (and here also the polar angle, as $$\vec{k}_i = k\zhat$$). Thus:

$$
M(\vec{k}_f, \vec{k}_i) = M(k, \theta) =  \tilde{V}(2k\sin(\frac{\theta}{2})) + \zeta\tilde{V}(2k\cos(\frac{\theta}{2}))
$$

Then computing the differential cross section as the square of the scattering matrix element/amplitude:

$$
\frac{d\sigma}{d\Omega} = \lvert \frac{m}{2\pi} M(k, \theta) \rvert^2 = \frac{m^2}{4\pi^2}\lvert\tilde{V}(2k\sin(\frac{\theta}{2})) + \zeta\tilde{V}(2k\cos(\frac{\theta}{2})) \rvert^2
$$

using the form of $$\tilde{V}(\vec{q})$$ provided we conclude:

$$
\color{blue}{\frac{d\sigma}{d\Omega} = 4m^2\left(\frac{1}{4k^2\sin^2(\frac{\theta}{2}) + \kappa^2} + \frac{\zeta}{4k^2\sin^2(\frac{\theta}{2}) + \kappa^2}\right)^2}
$$

for $$\theta = \pi/2$$, for bosons we have:

$$
\color{blue}{\frac{d\sigma}{d\Omega}(\theta=\pi/2) = 4m^2\left(\frac{2}{2k^2\sin^2+ \kappa^2}\right)^2.}
$$

which is twice the result for distinguishable particles. For fermions we have:

$$
\color{blue}{\frac{d\sigma}{d\Omega}(\theta=\pi/2) = 0.}
$$

arising from destructive interference between the two possible scattering processes ($$k_i \zhat \to k_f\xhat, -k_i \zhat \to -k_f\xhat$$ and $$k_i \zhat \to -k_f\xhat, -k_i \zhat \to k_f\xhat$$).

#### Spin-Orbit Coupling in the 3-D Harmonic Oscillator <a id="problem-qm-spinorbitqho" name="problem-qm-spinorbitqho"></a>
**Source:** UChicago 2014 Quantum Mechanics Graduate Diagnostic Exam Q2

**Problem Statement:** *Consider a spin-1/2 particle of mass $$m$$ moving in a three-dimensional harmonic oscillator potential:*
\begin{equation}\label{eq:3dqho}
V(r) = \frac{1}{2}m\omega^2r^2
\end{equation}
*with $$r^2 = x^2 + y^2 + z^2$$.*

*(a) What are the energy and degeneracy (including spin) of the ground state(s) and the first excited state(s) of this system?*

*(b) The general form of the spin-orbit coupling for a particle of mass m and spin \vec{S} moving in a radial potential $$V(r)$$ is:*
\begin{equation}\label{eq:spinorbit}
H_{s-o} = \frac{1}{2m^2c^2}\vec{S} \cdot \vec{L} \frac{1}{r}\frac{dV(r)}{dr}
\end{equation}
*What are the corrections to the ground state and first excited state energy eigenvalues for a spin-1/2 particle in the three-dimensional isotropic harmonic oscillator potential above when this spin-orbit interaction is included?*

**Solution:** (a) We can write the 3-D harmonic oscillator Hamiltonian as the sum of 1-D harmonic oscillator Hamiltonians:

$$
H_{3D} = \frac{\vec{p}^2}{2m} + V(r) = \frac{p_x^2 + p_y^2 + p_z^2}{2m} + \frac{1}{2}m\omega^2(x^2 + y^2 + z^2) = H_{x} + H_y + H_z
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
H_{s-o} = \frac{1}{2m^2c^2}\vec{S} \cdot \vec{L} \frac{1}{r}\frac{dV(r)}{dr} = \frac{1}{2m^2c^2}\vec{S} \cdot \vec{L} \frac{1}{r}\left(\frac{1}{2}m\omega^2 2r\right) = \frac{\omega^2}{mc^2}\vec{S} \cdot \vec{L}
$$ 

The $$\lvert l, m, s, s_z \rangle$$ basis we use is inconvenient for calculating the energy corrections as these states are not eigenstates of $$\vec{S} \cdot \vec{L}$$. However, defining the joint angular momentum $$J_i = L_i + S_i$$ we find that $$J^2 = L^2 + S^2 + 2\vec{S} \cdot \vec{L}$$ and so $$\vec{S} \cdot \vec{L} = \frac{J^2 - L^2 - S^2}{2}$$. Thus we will find it convenient to work in the $$\lvert j, j_z, l, s\rangle$$ basis. To this end we note:

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
    H = \frac{\vec{p}_1^2}{2m} + \frac{\vec{p}_2^2}{2m} + \frac{k}{2}(\vec{x}_1 - \vec{x}_2)^2
\end{equation}

*$$\vec{x}_{1, 2}$$ are the coordinates of the two fermions, and $$\vec{p}_{1,2}$$ are the conjugate momenta. For simplicity assume that the spins of both fermions are polarized in the same direction (e.g, in the $$\uparrow$$ direction) so that we may ignore the spin degree of freedom.*

*(a) State the restriction imposed by Fermi statistics on acceptable wave functions $$\psi(\vec{x}_1, \vec{x}_2)$$ of this system.*

*(b) Rewrite $$H$$ in terms of center-of-mass and relative coordinates.*

*(c) Ignoring the restriction imposed by Fermi statistics what is the ground state energy? What is the energy of the first excited bound state?*

*(d) Including the effects of Fermi statistics what is the ground state energy? What is the degeneracy of the ground state?*

**Solution:** (a) Fermi statistics dictate that the wavefunction must have odd parity/be antisymmetric under exchange of the particles, and therefore:

$$
\color{blue}{\psi(\vec{x}_1, \vec{x}_2) = -\psi(\vec{x}_2, \vec{x}_1)}
$$

(b) We define the center of mass and relative coordinates $$\vec{R} = \frac{m\vec{r}_1 + m\vec{r}_2}{m + m} = \frac{\vec{r}_1 + \vec{r}_2}{2}$$ and $$\vec{r} = \vec{r}_1 - \vec{r}_2$$. We also have the conjugate center of mass and relative momenta of $$\vec{P} = \vec{p}_1 + \vec{p}_2$$ and $$\vec{p} = \frac{\vec{p}_1 - \vec{p}_2}{2}$$, which inverting we obtain $$\vec{p}_1 = \frac{\vec{P} + 2\vec{p}}{2}$$ and $$\vec{p}_2 = \frac{\vec{P} - 2\vec{p}}{2}$$, and thus we can rewrite $$H$$ as:

$$
\color{blue}{H = \frac{\vec{P}^2}{4m} + \frac{\vec{p}^2}{m} + \frac{k}{2}\vec{r}^2}
$$

(c) The Hamiltonian decouples into $$H = H_{cm} + H_{rel}$$ where $$H_{cm}$$ is the Hamiltonian of a free particle with mass $$2m$$ and $$H_{rel}$$ is the Hamiltonian of a particle of mass $$\frac{m}{2}$$ in a 3-D harmonic oscillator potential with spring constant $$k$$. The former has unbounded spectrum $$E_{cm} = \in [0, \infty)$$ and for simplicity we assume that $$E_{cm} = 0$$ for the rest of the problem. The latter has quantized spectrum $$E_{n_x, n_y, n_z} = \frac{3}{2}\hbar\omega(n_x + n_y + n_z + \frac{3}{2})$$ (as $$H_{rel}$$ can be decomposed into 3 1-D simple harmonic oscillators, each with energy $$E_n = \frac{\hbar}\omega(n + \frac{1}{2})$$), with $$\omega = \sqrt{\frac{2k}{m}}$$. Ignoring the restriction from Fermi statistics, the ground state is then the state with $$n_x = n_y = n_z = 0$$ and has energy $$\color{blue}{\frac{3}{2}\hbar\omega}$$. The excited state has one $$n_i = 1$$ and the other two zero, with energy $$\color{blue}{\frac{5}{2}\hbar\omega}$$.

(d) Including the effects of fermionic exchange statistics, the answer to (c) changes. To this end, we note that the eigenstates of the SHO are eigenstates of parity (this follows as $$H$$ is quadratic in the $$x, p$$ quadrature operators and thus $$[\Pi, H] = 0$$), and in particular (recalling the parity of the Hermite polynomials/wavefunctions, or thinking about the parity of raising operators as is done in <a href="#problem-qm-symmetryamplitudes" name="#problem-qm-symmetryamplitudes"> Symmetries and Transition Amplitudes </a>) $$\Pi\lvert n \rangle = (-1)^n\lvert n \rangle$$. In 3-D this generalizes $$\Pi\lvert n_x, n_y, n_z \rangle = (-1)^{n_x + n_y + n_z} \lvert n_x, n_y, n_z \rangle$$. Since fermionic exchange statistics requires that the acceptable states of this system have odd parity, the $$n_x = n_y = n_z$$ state from (c) with even parity is forbidden. The ground states are instead those with one $$n_i = 1$$ and the other two zero (these have odd parity), with energy $$\color{blue}{\frac{5}{2}\hbar\omega}$$. The ground space is thus <span style="color:blue">3-fold degenerate</span>.

Note: We could reach the same conclusion by observing that the eigenstates of the 3-D harmonic oscillator are eigenstates of angular momentum (see <a href="#problem-qm-spinorbitqho" name="#problem-qm-spinorbitqho"> Spin-Orbit Coupling in the 3-D Harmonic Oscillator </a> for more discussion) and can be labelled by quantum numbers $$l, m$$. We also recall that the angular momentum eigenstates are eigenstates of parity $$\Pi\lvert l, m \rangle = (-1)^l\lvert l, m \rangle$$, thus the fermionic exchange statistics/antisymmetric wavefunction forbids $$l = 0$$ and the ground state(s) consist of the 3-fold degenerate $$l = 1$$ subspace with $$E = \frac{5}{2}\hbar\omega$$.

#### A Quantum Spin Chain <a id="problem-qm-spinchain" name="problem-qm-spinchain"></a>
**Source:** MIT Fall 2012 Doctoral General Examination Quantum Q1

**Problem Statement:** *Consider a one-dimensional chain of $$N$$ spin-1/2 particles coupled through the Hamiltonian*

\begin{equation}\label{eq:heisenbergchain}
H = J \sum_{i=1}^{N-1}\vec{S}_i \cdot \vec{S}_{i+1}
\end{equation}

*where $$\vec{S} = (S_x, S_y, S_z)$$ are the usual spin operators for a spin-1/2 particle, $$J > 0$$ is a positive constant, and $$N \gg 1$$.*

*In a famous 1931 paper, Hans Bethe showed that for this Hamiltonian, the ground state energy per particle $$E_{GS}/N \equiv E_0$$ was equal to $$\hbar^2 J(\log 2 - 1/4) \approx -0.433\hbar^2J$$. You will not be required to reproduce this result. Instead, you will determine upper and lower bounds for the ground state energy per particle.*

*(a) If the spin operators are treated as classical spin vectors with $$\lvert \vec{S} \rvert = \hbar/2$$, what is the ground state spin configuration and what is the ground state energy per particle $$E_0$$?*

*(b) Consider the trial wave function*

\begin{equation}\label{eq:singletchain}
    \lvert \Psi \rangle = \bigotimes_{i = \text{odd}}\lvert i, i+1 \rangle_0 = \lvert 1, 2 \rangle_0 \otimes \lvert 3, 4 \rangle_0 \otimes \ldots \otimes \lvert N-1, N \rangle_0
\end{equation}

*where $$\lvert i, j \rangle_0$$ is the spin singlet state formed from the spins on sites $$i$$ and $$j$$. Use this state to find an upper bound on $$E_0$$.*

*(c) Prove the following lower bound on E_0:*

\begin{equation}\label{eq:lowerbound}
    -\frac{3}{4}\hbar^2 J \leq E_0
\end{equation}

**Solution:** (a) If the spin operators are classical spin vectors, then the most energetically optimal configuration is to make $$\vec{S}_{i} \cdot \vec{S}_{i+1} = -\lvert \vec{S}_{i}\rvert \lvert \vec{S}_{i+1}\rvert = -\frac{\hbar^2}{4}$$ for each term in the Hamiltonian. The spin configuration that accomplishes this is <span style="color:blue">$$\vec{S}_{i} = +\frac{\hbar}{2}\hat{z}$$ for odd sites, $$\vec{S}_{i+1} = -\frac{\hbar}{2}\hat{z}$$ for even sites (or vise versa).</span> Since each term in the Hamiltonian contributes $$-\frac{1}{4}\hbar^2J$$, the ground state energy is thus $$E_{GS} = -(N-1)\frac{1}{4}\hbar^2J$$ and thus the energy per particle (in the $$N \gg 1$$ limit in which $$N-1 \sim N$$) is $$\color{blue}{E_0 = E_{GS}/N = -\frac{1}{4}\hbar^2J.}$$

(b) We first prove the variational theorem, that says that for a Hamiltonian $$H$$ with ground state energy $$E_{GS}$$ that $$\langle \psi \rvert H \lvert \psi \rangle \geq E_{GS}$$ for any normalized $$\lvert \psi \rangle$$. To begin, we expand $$\lvert \psi \rangle$$ in the eigenbasis of $$H$$, so $$\lvert \psi \rangle = \sum_n c_n \lvert n \rangle$$ where $$H\lvert n \rangle = E_n \lvert n \rangle$$, with $$E_0 = E_{GS} \leq E_n$$ for all $$n$$. It then follows that:

$$
\langle \psi \rvert H \lvert \psi \rangle = \left(\sum_n c_n^* \langle n \rvert\right) H \left(\sum_{n'}c_{n'} \lvert n' \rangle \right) = \sum_n \lvert c_n \rvert^2 E_n \geq \sum_n \lvert c_n \rvert^2 E_{GS} = E_{GS} \sum_n \lvert c_n \rvert^2 = E_{GS}.
$$

In the second equality we use the eigenvalue equation and the orthogonality of the eigenstates, and in the last equality we use the normalization of $$\lvert \psi \rangle$$ that ensures that $$\sum_n \lvert c_n \rvert^2 = 1$$. We now apply the variational theorem with the provided trial state. We will find it convenient to split the Hamiltonian into two parts:

$$
\langle \Psi \rvert H \lvert \Psi \rangle = J\sum_{i \text{odd}} \langle \Psi \rvert \vec{S}_i \cdot \vec{S}_{i+1} \lvert \Psi \rangle + \sum_{i \text{even}} \langle \Psi \rvert \vec{S}_i \cdot \vec{S}_{i+1} \lvert \Psi \rangle
$$

Studying the first sum, we have $$(N-1)/2$$ terms of the form:$$ \langle i, i+1 \rvert_0 \vec{S}_i \cdot \vec{S}_{i+1} \rvert i, i + 1 \rangle_0$$. Defining $$\vec{S} = \vec{S}_i + \vec{S}_{i+1}$$, we note that $$\vec{S}_i \cdot \vec{S}_{i+1} = \frac{1}{2}(\vec{S} - \vec{S}_1 - \vec{S}_2)$$ and so joint eigenstates of $$\vec{S}, \vec{S}_1, \vec{S}_2$$ have eigenvalue $$\frac{\hbar^2}{2}(s(s + 1) - s_1(s_1 + 1) - s_2(s_1 + 1)) = \frac{\hbar^2}{2}(s(s+1) - \frac{3}{2})$$ where $$s$$ is the total joint spin. For a singlet state $$s = 0$$ and so:

$$
\lvert i, i+1 \rvert_0 \vec{S}_i \cdot \vec{S}_{i+1} \rvert i, i + 1 \rangle_0 = \frac{\hbar^2}{2}(0 - \frac{3}{2}) = -\frac{3}{4}\hbar^2
$$

thus we compute the energy from the odd terms:

$$
J\sum_{i \text{odd}} \langle \Psi \rvert \vec{S}_i \cdot \vec{S}_{i+1} \lvert \Psi \rangle = -\frac{N-1}{2}\frac{3}{4}\hbar^2J = -(N-1)\frac{3}{8}.
$$

Now studying the second sum, we have $(N-1)/2$$ terms of the form:

$$ \langle i, i+1 \rvert_0\langle i+2, i+3 \rvert_0 \vec{S}_{i+1} \cdot \vec{S}_{i+2} \rvert i, i+1\rangle_0 \rvert i+2, i+3\rangle_0$$

which we evaluate to be:

$$
\langle i, i+1 \rvert_0 \vec{S}_{i+1} \rvert i, i+1\rangle_0 \langle i+2, i+3 \rvert_0\vec{S}_{i+2} \rvert i+2, i+3\rangle_0 = 0 \cdot 0 = 0
$$

where we use that the $$\v{S}_{i+1} \cdot \v{S}_{i+2}$$ acts on the subspaces independently (allowing us to factor the expectation value) and we use that the singlet state is spherically symmeric to conclude that $$\langle i, i+1 \rvert_0 \vec{S}_{i+1} \rvert i, i+1\rangle_0 = 0$$. Thus:

$$
\sum_{i \text{even}} \langle \Psi \rvert \vec{S}_i \cdot \vec{S}_{i+1} \lvert \Psi \rangle = 0
$$

Thus, using the variational theorem we conclude:

$$
E_{GS} \leq \langle \Psi \rvert H \lvert \Psi \rangle \leq -\frac{N-1}{2}\frac{3}{4}\hbar^2J
$$

from which we can bound $$E_0 = E_{GS}/N$$ to be:

$$
\color{blue}{E_0 \leq -\frac{3}{8}\hbar^2 J.}
$$

(c) Let $$H$$ be any Hamiltonian of the form $$H = \sum_k H_k$$ such that $$H$$ has ground state energy $$\lvert \psi_{GS} \rangle$$ and $$E_{GS}$$ and the $$H_k$$s have ground state energy $$E_{GS, k}$$. Then it follows that:

$$
E_{GS} = \langle \psi_{GS} \rvert H \lvert \psi_{GS} \rangle = \sum_k \langle \psi_{GS} \rvert H_k \lvert \psi_k \rangle \geq \sum_k E_{GS, k}
$$

where in the last inequality we use the variational theorem on the individual $$H_k$$ terms. Since the ground state energy of $$\vec{S}_i \cdot \vec{S}_{i+1}$$ is $$-\frac{3}{4}\hbar^2J$$, using this we can lower bound $$E_{GS} \geq -(N-1)\frac{3}{4}\hbar^2J$$ and thus we obtain the upper-bound on $$E_0$$:

$$
\color{blue}{E_0 \geq -\frac{3}{4}\hbar^2J.}
$$

Combining the above two results we have an upper and lower bound on $$E_0$$:

$$
-\frac{3}{4}\hbar^2J \leq E_0 \leq -\frac{3}{8}\hbar^2J
$$

which (as must be the case) the exact result falls within.


#### Anomalous Magnetic Moment of the Electron TODO <a id="problem-qm-emagmoment" name="problem-qm-emagmoment"></a>
**Source:** MIT Fall 2012 Doctoral General Examination Quantum Q2

**Problem Statement:** *The gyromagnetic factor of the electron $$g$$ determines the relationship between the electron magnetic moment $$\vec{\mu}$$ and the electron spin $$\vec{S}$$,

\begin{equation}\label{eq:emagmoment}
    \vec{\mu} = g\frac{e}{2m}\vec{S},
\end{equation}

*where $$e$$ is the electron charge and $$m$$ is the electron mass. Famously, the Dirac equation predicts $$g = 2$$, but in quantum electrodynamics, the electron picks up na anomalous magnetic moment $$g = 2(1+a)$$, where the current experimental value is $$a = 0.00115965218076(27)$$.*

*One way to experimentally measure $$a$$ is the allow a beam of electrons to interact with a constant magnetic field $$\vec{B} = B\hat{z}$$ via the Hamiltonian:*

\begin{equation}\label{eq:emagmoment}
    H = \frac{1}{2m}\left(\vec{p} - e\vec{A}\right)^2 - \vec{\mu} \cdot \vec{B}
\end{equation}

*where $$\vec{A}$$ is the vector potential. The electrons are confined to the $$x-y$$ plane, and you can ignore any electron-electron interactions. The electrons will exhibit cyclotron motion with frequency $$\omega = EB/m$$, but will also exhibit spin precession with a slightly different frequency. In this problem, you will show how to use this phenomenon to extract $$a$$.*

*(a) Verify the commutation relations*

\begin{equation}\label{eq:commutationv}
    [v_x, H] = i\hbar\omega v_y, \quad [v_y, H] = -i\hbar\omega v_x,
\end{equation}

*where $$\vec{v} = (\vec{p} - e\vec{A})/m$$ is the gauge-invariant velocity operator. Hint: $$\vec{v}$$ is gauge-invariant and thus this problem can be solved in any choice of gauge.*

*(b) Consider the two expectation values*

\begin{equation}\label{eq:spinvelocityexpectation}
    C_1(t) = \langle S_xv_x + S_yv_y \rangle, \quad C_2(t) = \langle S_xv_y - S_yv_x\rangle.
\end{equation}

*Derive a set of coupled differential equations that describe the time evolution of $$C_1(t)$$ and $$C_2(t)$$. In the special case that $$a = 0$$ (i.e. $$g=2$$), verify that $$C_1(t)$$ and $$C_2(t)$$ do not change with time.*

*(c) A beam of electrons of velocity $$\vec{v}$$ is prepared at time $$t = 0$$ in a spin state with known values of $$C_1(0)$$ and $$C_2(0)$$. The beam interacts with a magnetic field $$\vec{B} = B\hat{z}$$ between $$t = 0$$ and $$t = T$$. The expectation value $$C_1(T)$$ is experimentally measured to be periodic with period $$2\pi/\Omega$$, i.e. $$C_1(T) = C_1(T + 2\pi/\Omega)$$. Use this information to determine the value of $$a$$ in terms of $$\Omega$$ and other physical parameters.*

**Solution:**

#### A Heisenberg Ferromagnet <a id="problem-qm-heisenbergferro" name="problem-qm-heisenbergferro"></a>
**Source:** MIT Spring 2012 Doctoral General Examination Quantum Q1

**Problem Statement:** *In a ferromagnetic material the electron spins are aligned, suggesting that an interaction of the form:*

\begin{equation}\label{eq:spininteraction}
\delta H = \kappa \vec{S}_1 \cdot \vec{S}_2
\end{equation}

*is present between each pair of electrons, where $$\vec{S}_1, \vec{S}_2$$ are the operators corresponding to the spins of the two electrons. While Eq. \eqref{eq:spininteraction} does not appear explicitly in the Hamiltonian for a ferromagnet, Heisenberg realized that Eq. \eqref{eq:spininteraction} could appear as an effective interaction, arising from Coulomb repulsion and fermionic properties of electrons.*

*In this problem you will derive a Heisenberg ferromagnetism for two spin-1/2 electrons in a common potential $$V(\vec{r})$$, with Hamiltonian:*

\begin{equation}\label{eq:interactionelectronsH}
    H = \frac{\vec{p}_1^2}{2m} + \frac{\vec{p}_2^2}{2m} + V(\vec{r}_1) + V(\vec{r}_2) + \frac{e^2}{\lvert \vec{r}_1 - \vec{r}_2\rvert}
\end{equation}

*Note that $$\delta H$$ does not appear in the above, so there is no explicit spin dependence. The single-particle Schrodinger equation with potential $$V(\vec{r})$$ has eigenstates with energies $$E_i$$ and wavefunctions $$\psi_i(\vec{r})$$.*

*(a) The total wave function $$\Psi(\vec{r}_1, s_1 \vec{r}_2, s_2)$$ depends on the set of spin variables $$s_1, s_2$$ (use whichever notation for spin that you prefer, including bra/ket notation). Show that the eigenstates of the Hamiltonian can be written as a separable form $$\psi(\vec{r}_1, \vec{r}_2)\chi(s_1, s_2)$$. Construct eigenstates of total spin, and describe the symmetry properties of $$\psi(\vec{r}_1, \vec{r}_2)$$ under particle exchange for each of the spin states.*

*(b) In the absence of Coulomb repulsion, consider the two-particle configurations where one electron is in state $$\psi_a(\vec{r})$$ and the other is in state $$\psi_b(\vec{r})$$. What are the corresponding two-particle wavefunctions, including spin?*

*(c) The degeneracy of the states in part (b) is broken by Coulomb repulsion, yielding two distinct energy levels. Identify the two-particle wavefunctions associated with these two levels, and find an expression for the energy splitting $$\delta E$$ to first order in the Coulomb interaction in terms of $$\psi_a$$ and $$\psi_b$$.*

*(d) Show that the energy splitting in part (c) can be mimicked (at first order) by turning off the Coloumb interaction in Eq. \eqref{eq:interactionelectronsH} and replacing it with Eq. \eqref{eq:spininteraction}. Find an expression for $$\kappa$$ in terms of $$\delta E$$.*

*(e) Determine the sign of $$\kappa$$. Hint: Judicious use of Fourier transforms may be helpful. Recall that*

\begin{equation}\label{eq:fourieridentities}
\int d^3r e^{i\vec{q} \cdot \vec{r}}  (2\pi)^3\delta^{(3)}(\vec{q}), \quad \int d^3r e^{i\vec{q} \vec{r}} \frac{1}{\lvert \vec{r} \rvert} = \frac{4\pi}{\vec{q}^2}.
\end{equation}

**Solution:** (a) Since Eq. \eqref{eq:interactionelectronsH} is independent of spin, its eigenstates are the position eigenstates $$\lvert \psi(\vec{r}_1, \vec{r}_2) \rangle$$ multiplied by an arbitrary spin state $$\lvert \chi(s_1, s_2) \rangle$$. Thus the wavefunctions have the claimed separable form of $$\color{blue}{\Psi(\vec{r}_1, \vec{r}_2, s_1, s_2) = \psi(\vec{r}_1, \vec{r}_2)\chi(s_1, s_2)}$$. The eigenstates of total spin $$\vec{S} = \vec{S}_1 + \vec{S}_2$$ are the triple states:

$$
\color{blue}{\lvert s=1, m \rangle = \begin{cases} \lvert \uparrow \uparrow \rangle & m = 1 \\ \frac{\lvert \uparrow \downarrow \rangle + \lvert \downarrow \uparrow \rangle}{\sqrt{2}} & m = 0 \\ \lvert \downarrow \downarrow \rangle & m = -1 \end{cases}}
$$

and the singlet state:

$$
\color{blue}{\lvert s = 0, m = 0 \rangle = \frac{\lvert \uparrow \downarrow \rangle - \lvert \downarrow \uparrow \rangle}{\sqrt{2}}.}
$$

Since electrons are fermions, the total wavefunction $$\Psi(\vec{r}_1, \vec{r}_2, s_1, s_2)$$ must be antisymmetric under particle exchange $$1 \leftrightarrow 2$$. For the triplet states (for which the spins are symmetric under exchange) we therefore must have the position wavefunction be antisymmetric and vise versa for the singlet state (for which the spins are antisymmetric under exchange), so we conclude:

$$
\color{blue}{\psi(\vec{r}_1, \vec{r}_2) = \begin{cases} -\psi(\vec{r}_2, \vec{r}_1) & s = 1 \\ \psi(\vec{r}_2, \vec{r}_1) & s = 0 \end{cases}.}
$$

(b) In the absence of the coloumb repulsion, $$H$$ splits into the sum of $$H_1 + H_2$$ for the individual electrons. Thus we can find the individual eigenfunctions $$\psi_a(\vec{r}), \psi_b(\vec{r})$$ and antisymmetrize (for triplet states)

$$
\color{blue}{\Psi(\vec{r}_1, \vec{r}_2, s = 1, m) = \frac{\psi_a(\vec{r}_1)\psi_b(\vec{r}_2) + \psi_b(\vec{r}_1)\psi_a(\vec{r}_2)}{\sqrt{2}}\chi(s=1, m)}
$$

or symmetrize (for the singlet states):

$$
\color{blue}{\Psi(\vec{r}_1, \vec{r}_2, s = 0, m=0) = \frac{\psi_a(\vec{r}_1)\psi_b(\vec{r}_2) + \psi_b(\vec{r}_1)\psi_a(\vec{r}_2)}{\sqrt{2}}\chi(s=0, m=0).}
$$

(c) The distinct particle-wavefunctions are those in the triplet states $$\Psi'(\vec{r}_1, \vec{r}_2, s = 1, m)$$ and those in the singlet state $$\Psi'(\vec{r}_1, \vec{r}_2, s = 0, m)$$ (note that due to the Coloumb repulsion, we can no longer write $$H = H_1 + H_2$$ and thus the decomposition into individual one-particle wavefunctions $$\psi_a, \psi_b$$ from (b) no longer holds - thus the eigenfunctions $$\Psi'$$ here are distinct from the $$\Psi$$s in (b)). We can find the energy splitting $$\delta E$$ to first order using perturbation theory, treating $$\delta H = \frac{e^2}{\lvert \vec{r}_1 - \vec{r}_2\rvert}$$ as a perturbation:

$$
\delta E = E_{s=1}^{(1)} - E_{s=0}^{(1)} = \langle \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rvert \delta H \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rangle - \langle \Psi(\vec{r}_1, \vec{r}_2, s = 0, m) \rvert \delta H \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 0, m) \rangle.
$$

The degeneracy of $$\lvert \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rangle, \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 0, m=0) \rangle$$ is a priori a cause for concern, as the perturbation must be diagonal in the above basis for degenerate perturbation theory to give a valid result for the energy splitting. However, since $$\delta H = \frac{e^2}{\lvert \vec{r}_1 - \vec{r}_2\rvert}$$ is symmetric under particle interchange, the off diagonal terms indeed vanish, as can be seen via an insertion of the particle exchange operator $$\Pi$$:

$$
\langle \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rvert \delta H \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 0, m=0) \rangle = \langle \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rvert \Pi^\dagger \delta H \Pi\lvert \Psi(\vec{r}_1, \vec{r}_2, s = 0, m=0) \rangle = -\langle \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rvert \delta H \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 0, m=0) \rangle.
$$

Thus the expression for the energy splitting using perturbation theory is valid. We can evaluate the (diagonal) matrix elements via carrying out integrals by taking integrals in position space and sums in spin space - the sum over spin states drops out as $$\delta H$$ is independent of spin, and thus we have:

$$
\delta E = \int d^3r_1 d^3r_2 \frac{e^2}{\lvert \vec{r}_1 - \vec{r}_2\rvert}\left(\frac{\psi_a(\vec{r}_1)\psi_b(\vec{r}_2) - \psi_b(\vec{r}_1)\psi_a(\vec{r}_2)}{\sqrt{2}} \cdot c.c. - \frac{\psi_a(\vec{r}_1)\psi_b(\vec{r}_2) + \psi_b(\vec{r}_1)\psi_a(\vec{r}_2)}{\sqrt{2}} \cdot c.c. \right)
$$

with c.c. denoting the complex conjugate. After the cancellation of terms, we conclude:

$$
\color{blue}{\delta E = -2\int d^3r_1 d^3r_2 \frac{e^2}{\lvert \vec{r}_1 - \vec{r}_2\rvert}\psi_a^*(\vec{r}_1)\psi_b^*(\vec{r}_2)\psi_b(\vec{r}_1)\psi_a(\vec{r}_2).}
$$

(d) Turning off the Coloumb interaction and turning on the spin interactions, if we again study:

$$
\delta E = E_{s=1}^{(1)} - E_{s=0}^{(1)} = \langle \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rvert \delta H \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 1, m) \rangle - \langle \Psi(\vec{r}_1, \vec{r}_2, s = 0, m) \rvert \delta H(\vec{r}_1, \vec{r}_2) \lvert \Psi(\vec{r}_1, \vec{r}_2, s = 0, m) \rangle
$$

it is now the integral over position space that drops out as $$\delta H = \kappa \vec{S}_1 \cdot \vec{S}_2$$ is independent of position, and we are left with:

$$
\delta E = \kappa\left(\langle s = 1, m \rvert \vec{S}_1 \cdot \vec{S}_2 \lvert s = 1, m \rangle - \langle s = 0, m=0\rvert \vec{S}_1 \cdot \vec{S}_2 \lvert s = 0, m=0 \rangle\right)
$$

We write $$\vec{S}_1 \cdot \vec{S}_2 = \frac{1}{2}(S^2 - S_1^2 - S_2^2)$$, which has eigenvalues $$\frac{\hbar^2}{2}(s(s+1) - s_1(s_1 + 1) - s_2(s_2 + 1))$$. Here $$s_1 = s_2 = \frac{1}{2}$$, and for the triplet ($$s = 1$$) states evaluates to -\frac{\hbar^2}{4}$$ and for the singlet ($$s = 0$$)states evaluates to $$-\frac{3\hbar^2}{4}$$. Thus:

$$
\delta E = \kappa\left(\frac{\hbar^2}{4} - \left(-\frac{3\hbar^2}{4}\right)\right) = \kappa\hbar^2
$$

Thus the energy splitting in (c) can be mimicked via the spin interaction. Specifically, we tune $$\kappa$ to:

$$
\color{blue}{\kappa = \frac{\delta E}{\hbar^2}.}
$$

(e) We determine the sign of $$\kappa$$ by reasoning about $$\delta E$$ from the expression in (c). Defining $$F(\vec{r}) = \psi_a^*(\vec{r}_1)\psi_b(\vec{r}_1)$$ and $$G(\vec{r}_2 - \vec{r}_1) = \frac{1}{\lvert \vec{r}_2 - \vec{r}_1 \rvert}$$, the expression becomes:

$$
\delta E = -2e^2\int d^3r_1 d^3r_2 F(\vec{r}_1)G(\vec{r}_2 - \vec{r}_1)F^*(\vec{r}_2)
$$

Now using the expression in the hint, we can write $$G(\vec{r}_2 - \vec{r}_1)$$ in terms of its Fourier transform:

$$
G(\vec{r}_2 - \vec{r}_1) = \frac{1}{(2\pi)^3}\int d^3q\tilde{G}(\vec{q})e^{i\vec{q}(\vec{r}_2 - \vec{r}_1)}
$$

Thus:

$$
\delta E = -2e^2\frac{1}{(2\pi)^3}\int d^3r_1d^3r_2d^3q F(\vec{r}_1)e^{-i\vec{q} \cdot \vec{r}_1}\tilde{G}(\vec{q})F^*(\vec{r}_2)e^{i\vec{q} \cdot \vec{r}_1}
$$

The integrals over $$r_1, r_2$$ simply give the Fourier transforms of $$F(\vec{r}_1)/F^*(\vec{r}_2)$$ and thus:

$$
\delta E = -2e^2\frac{1}{(2\pi)^3}\int d^3q \tilde{F}(\vec{q})\tilde{G}(\vec{q})\tilde{F}^*(\vec{q}) = -2e^2\frac{1}{(2\pi)^3}\int d^3\lvert \tilde{F}(\vec{q})\rvert^2\tilde{G}(\vec{q})
$$

Now evaluating substituting the expression for $$\tilde{G}(\vec{q})$$ from the hint, we obtain:

$$
\delta E = -2e^2\frac{1}{(2\pi)^3}\int d^3q \lvert \tilde{F}(\vec{q})\rvert^2 \frac{4\pi}{\vec{q}^2} = -\frac{e^2}{\pi^2}\int d^3q \frac{\lvert \tilde{F}(\vec{q})\rvert^2}{\vec{q}^2}.
$$

Since the integrand is positive definite, we conclude $$\delta E < 0$$. Since $$\kappa = \delta E/\hbar^2$$ we conclude that $$\color{blue}{\kappa < 0}$$. The spins being aligned is favoured, as we would expect for a ferromagnet.


#### The Supersymmetric Method TODO <a id="problem-qm-susy" name="problem-qm-susy"></a>
**Source:** MIT Spring 2012 Doctoral General Examination Quantum Q2

**Problem Statement:** *In this problem you will solve for the energy spectrum of a particle of mass $$m$$ confined to a potential*

\begin{equation}\label{eq:tanpotential}
    V(x) = V_0\left[\sec^2\frac{x}{x_0} + \tan^2\frac{x}{x_0}\right] = V_0\left[1 + 2\tan^2\frac{x}{x_0}\right]
\end{equation}

*where $$-\frac{\pi}{2}x_0 \leq x \leq \frac{\pi}{2}x_0$$ (recall that $$\sec x = 1/\cosx$$, and the equality of the two expressions above follows from trigonometric identities). Amazingly, this system is exactly solvable for the especial value:*

\begin{equation}\label{eq:specialV0}
    V_0 = \frac{\hbar^2}{2m}\frac{1}{x_0^2},
\end{equation}

*and you will derive the spectrum using the supersymmetric method. (Supersymmetry is a possible symmetry between bosons and fermions, but that fact will not be relevant for this problem).*

*(a) Consider two Hamiltonians*

\begin{equation}\label{eq:HHtilde}
    H = A^\dag A, \quad \tilde{H} = AA^\dag,
\end{equation}

*Where $$A$$ is an unspecified operator. Assume that $$H$$ has (normalized) eigenstates $$\lvert n \rangle$$ with*

\begin{equation}\label{eq:eigenvalue}
    H\lvert n \rangle = E_n \lvert n \rangle
\end{equation}

*for $$n \geq 1$$. For every $$n$$ with $$E_n \neq 0$$, show that $$A\lvert n \rangle$$ is an unnormalized eigenstate of $$\tilde{H}$$. Find the normalized eigenstates $$\lvert \tilde{n} \rangle$$ and their eigenvalues $$\tilde{E}_n$$ under $$\tilde{H}$$. What goes wrong with this argument if $$E_n = 0$$? Can $$E_n$$ or $$\tilde{E}_n$$ ever be negative? Note: For the remainder of this problem, you can assume that $$\lvert \tilde{n} \rangle$$ forms a complete basis for $$\tilde{H}$$, up to possible zero energy states.*

*(b) Now consider a specific operator $$A$$ of the form*

\begin{equation}\label{eq:A}
    A = \frac{\partial}{\partial x} + W(x)
\end{equation}

*where $$W(x)$$ is real. Show that $$H$$ and $$\tilde{H}$$ each describe a particle moving in a potential, in units where $$\hbar^2/2m = 1$$. Find the two potential energy functions, $$V(x)$$ and $$\tilde{V}(x)$$, corresponding to $$H$$ and $$\tilde{H}$$, respectively.*

*(c) We will be considering Hamiltonians defined on a finite range $$-\frac{\pi}{2}x_0 \leq x \leq \frac{\pi}{2}x_0$$. This means that the wave functions will have Dirichlet boundary conditions at $$x = \frac{\pi}{2}x_0$$, i.e. $$\psi(\pm \frac{\pi}{2}x_0) = 0$$. Assume that $$H$$ has a zero energy ground state consisten with these boundary conditions. Find the unnormalized ground state wave function $$\psi_0(x)$$ for $$H$ in terms of $$W(x)$$. Show that $$\tilde{H}$$ cannot have a zero energy ground state consistent with these boundary conditions.*

*(d) The potential in Eq. \eqref{tanpotential} is dual to a constant potential. That is, there is a $$W(x)$$ such that for $$-\frac{\pi}{2}x_0 \leq x \leq \frac{\pi}{2}x_0$$,*

\begin{equation}\label{eq:dualtanpotential}
    V(x) = a, \quad \tilde{V}(x) = b\left[\sec^2\frac{x}{x_0} + \tan^2\frac{x}{x_0}\right] = b\left[1 + 2\tan^2\frac{x}{x_0}\right]
\end{equation}

*where $$a, b$$ are constants. What is $$W(x)$$, and what are $$a$$ and $$b$$? You may find the following formulas helpful:*

\begin{equation}\label{eq:integralidentities}
    \int \frac{dx}{1+x^2} = \arctan x, \quad \int d\theta \sec^2\theta = \tan\theta, \quad \int \tan^2\theta = -\theta + \tan\theta
\end{equation}

*(e) Find the energy spectrum and energy eigenstates for the potential in Eq. \eqref{eq:tanpotential}. Does this system have a zero energy ground state? You should assume that all wave functions vanish at $$x = \frac{\pi}{2}x_0$$ (i.e. Dirichlet boundary conditions), and you should restore all factors of $$\hbar$$ and $$m$$. You do not need to normalize the states.*

**Solution:** (a) We apply $$\tilde{H}$$ to $$A\lvert n \rangle$$:

$$
\tilde{H}A\lvert n \rangle = AA^\dagger A \lvert n \rangle = A H \lvert n \rangle = A E_n \lvert n \rangle = E_n A \lvert n \rangle.
$$

Thus <span style="color:blue">$$A \lvert n \rangle$$ is an eigenstate of $$\tilde{H}$$</span>. Since $$\langle n \vert A^\dagger A \lvert n \rangle = \langle n \vert H \lvert n \rangle = E_n \langle n \vert n \rangle$$, the $$A \lvert n \rangle$$ have norm of $$\sqrt{E_n}$$ and thus the normalized eigenstates of $$\tilde{H}$$ are $$\color{blue}{\lvert \tilde{n} \rangle = \frac{1}{\sqrt{E_n}}A\lvert n \rangle}$$ with eigenvalues $$\color{blue}{\tilde{E}_n = E_n}$$. The argument fails if $$E_n = 0$$ as then $$A \lvert n \rangle$$ has zero norm, i.e. it is the zero vector (which cannot be an eigenstate). Further, since $$E_n = \norm{A\lvert n \rangle}^2$$ and norms are positive semidefinite, <span style="color:blue">$$E_n/\tilde{E}_n$$ cannot be negative. </span>

(b) Note that $$A = ip + W(x)$$ as $$p = -i\frac{\partial}{\partial x}$$. Note that from the canonical commutation relation $$[x, p] = i$$ it follows that $$[p, x^n] = -inx^{n-1}$$ (by induction on $$n$$) and thus Taylor expanding a function of $$x$$ it follows that $$[p, G(x)] = -iG'(x)$$ (alternatively, since $$p = -i\frac{\partial}{\partial x}$$ is given, the commutator can be evaluated by acting on a test function). In any case, we then compute:

$$
H = A^\dagger A = \left(-ip + W(x)\right)\left(ip + W(x)\right) = p^2 - i[p, W(x)] + W^2(x) = p^2 - W'(x) + W^2(x) = -\frac{\partial^2}{\partial x^2} - W'(x) + W^2(x)
$$

$$
\tilde{H} = A A^\dagger = \left(ip + W(x)\right)\left(-ip + W(x)\right) = p^2 + i[p, W(x)] + W^2(x) = p^2 + W'(x) + W^2(x) = -\frac{\partial^2}{\partial x^2} + W'(x) + W^2(x)
$$

Thus <span style="color:blue">$$H, \tilde{H}$$ both describe a particle in a potential</span> with $$\color{blue}{V(x) = -W'(x) + W^2(x)}$$ and $$\color{blue}{\tilde{V}(x) = W'(x) + W^2(x)}.$$

(c) From (a), we know that for eigenstates $$\lvert n \rangle$$ with energy $$E_n = 0$$ it follows that $$A\lvert n \rangle = 0$$. Thus we obtain the following ODE for the wavefunction $$\psi_0(x)$$:

$$
\left(\frac{\partial}{\partial x} + W(x))\psi_0(x) = 0 \implies \frac{\partial}{\partial x}\psi_0(x) = -W(x)\psi_0(x).
$$

Which can be solved via inspection:

$$
\color{blue}{\psi_0(x) = \exp(-\int_0^x W(x')dx').}
$$

Now consider $$\tilde{H}$$; by an anlogous argument, if an eigenstate $$\lvert \tilde{n} \rangle$$ exists with energy $$\tilde{E}_n = 0$$ then $$A^\dagger \lvert n \rangle = 0$$ and thus:

$$
\left(-\frac{\partial}{\partial x} + W(x))\tilde{\psi}_0(x) = 0 \implies \frac{\partial}{\partial x}\tilde{\psi}_0(x) = W(x)\tilde{\psi}_0(x).
$$

This has solution:

$$
\tilde{\psi}_0(x) = \exp(\int_0^x W(x')dx') = \frac{1}{\psi_0(x)}
$$

But $$\psi_0(\pm \frac{\pi}{2}x_0) = 0$$ means that $$\tilde{\psi}_0(\pm \frac{\pi}{2}x_0) = \infty$$, so it is impossible for both $$\psi, \tilde{\psi}$$ to have a zero-energy eigenstate that satisfies the Dirchlet boundary conditions.

(d) Since $$\tilde{V}(x) = b\left[\sec^2\frac{x}{x_0} + \tan^2\frac{x}{x_0}\right] = W'(x) + W^2(x)$$, recalling that $$\frac{\partial}{\partial x} \tan x = \sec^2 x$$ we observe $$\color{blue}{W(x) = \frac{1}{x_0}\tan(\frac{x}{x_0})}$$ works with with $$\color{blue}{b = \frac{1}{x_0^2}}$$. Then since $$V(x) = a = W'(x) - W^2(x)$$ we find that $$\color{blue}{a = -\frac{1}{x_0^2}.}$$.

(e) We find the spectrum and eigenstates for the dual potential and use this to construct the spectrum and eigenstates for the potential of Eq. \eqref{eq:dualtanpotential}. The Dirchlet boundary conditions of $$\psi(\pm \frac{\pi}{2}x_0) = 0$$ means that the dual problem is simply that of the infinite square well with walls at $$x = \pm \frac{\pi}{2}x_0$$ and with the bottom of the potential shifted by $-V_0 = \frac{\hbar^2}{2m}\frac{1}{x_0^2}$$. These we recall to be:

$$
\psi_n(x) = \sin(n\left(\frac{x}{x_0} - \frac{\pi}{2}))
$$

$$
E_n = \frac{\hbar^2 n^2}{2m x_0^2} - V_0 = V_0(n^2 - 1) \quad n \geq 1.
$$

The eigenvalues of $$\tilde{H}$$ are identical:

$$
\color{blue}{\tilde{E}_n = V_0(n^2 - 1) \quad n \geq 2}
$$

noting that since the result of (c) tells us that $$H, \tilde{H}$$ cannot share states with zero eigenvalue and hence $$E_1 = 0$$ means that $$\tilde{H}$$ cannot have the $$n = 1$$ state. The eigenstates of $$\tilde{H}$$ are obtained by applying $$A$$ to the above eigenstates and so:

$$
\tilde{\psi}_n(x) = \left(\frac{\partial}{\partial x} + W(x))\psi_n(x) = \left(\frac{\partial}{\partial x} + \frac{1}{x_0}\tan(\frac{x}{x_0})\right)\sin(n(\frac{x}{x_0} - \frac{\pi}{2}))
$$

thus we conclude:

$$
\color{blue}{\tilde{\psi}_n(x) = \frac{1}{x_0}\left(n\cos(n(\frac{x}{x_0} - \frac{\pi}{2})) + \sin(n(\frac{x}{x_0} - \frac{\pi}{2}))\tan(\frac{x}{x_0})\right).}
$$

#### Spin-1/2 in Time-Dependent Magnetic Field <a id="problem-qm-timedepmag" name="problem-qm-timedepmag"></a>
**Source:** MIT Fall 2002 Doctoral General Examination Quantum Q2

**Problem Statement:** Consider a spin-1/2 particle interacting with a time-dependent magneitc field:

\begin{equation}\label{eq:timedepBfield}
H(t) = \vec{B}(t) \cdot \vec{\sigma}
\end{equation}

where $$\vec{B}(t) = B(\sin\theta\cos\omega t, \sin\theta \sin \omega t, \cos\theta)$$ and $$\vec{\sigma} = (\sigma_x, \sigma_y, \sigma_z)$$ with $$\sigma_i$$ the Pauli matrices:

\begin{equation}\label{eq:paulis}
    \sigma_x = \left( \begin{array}{cc} 0 & 1 \\ 1 & 0\end{array} \right) \quad \sigma_y = \left( \begin{array}{cc} 0 & -i \\ i & 0\end{array} \right) \quad \sigma_z = \left( \begin{array}{cc} 1 & 0 \\ 0 & -1\end{array} \right).
\end{equation}

*(a) Find the instantaneous eigenstates $$\lvert +, t \rangle$$ and $$\lvert -, t \rangle$$ of $$H(t)$$ with eigenvalues $$+B$$ anf $$-B$$ respectively.*

*(b) Let $$\lvert \psi, t \rangle$$ obey the Schrodinger equation:*

\begin{equation}\label{eq:SE}
    i\hbar\frac{\partial}{\partial t}\lvert \psi, t \rangle = H(t)\lvert \psi, t \rangle
\end{equation}

*with $$\lvert \psi, 0 \rangle = \lvert +, 0 \rangle$$. Calculate $$P_+(t) \lvert \langle +, t \vert \psi, t \rangle \rvert^2$$ exctly. Hint: Expand $$\lvert \psi, t \rangle$$ in terms of $$\lvert +, t \rangle$$ and $$\lvert-, t \rangle$$ and find the equation for the expansion coefficients.*

*(c) What happens to $$P_+(t)$$ for $$\omega \ll B/\hbar$$? Explain.*

**Solution:** (a) From <a href="#problem-qm-spinhalfsg" name="#problem-qm-spinhalfsg"> Spin-1/2 and Stern-Gerlach </a> (taking $$\theta \to \theta$$, $$\phi = \omega t$$) we find:

$$
\color{blue}{\lvert +, t \rangle = \begin{pmatrix} \cos(\frac{\theta}{2}) \\ e^{i\omega t}\sin(\frac{\theta}{2}) \end{pmatrix} \quad \lvert -, t \rangle = \begin{pmatrix} -\sin(\frac{\theta}{2}) \\ e^{i\omega t}\cos(\frac{\theta}{2}) \end{pmatrix}.}
$$

(b) We expand:

$$
\lvert \psi, t \rangle = c_+\lvert +, t \rangle + c_-\lvert -, t \rangle
$$

which we substitute into the SE (with $$\hbar = 1$$) to obtain:

$$
i(\dot{c}_+\lvert +, t \rangle + c_+\dot{\lvert +, t \rangle} + \dot{c}_-\lvert -, t \rangle + c_-\dot{\lvert -, t \rangle}\right) = H(t)\left(c_+\lvert +, t\rangle + c_-\lvert -, t \rangle\right) = Bc_+\lvert + , t \rangle - B c_-\lvert -, t \rangle.
$$

We note that:

$$
\dot{\lvert +, t \rangle} = \begin{pmatrix} 0 \\ i\omega e^{i\omega t}\sin(\frac{\theta}{2}) \end{pmatrix} \quad \dot{\lvert -, t \rangle} = \begin{pmatrix} 0 \\ i\omega e^{i\omega t}\cos(\frac{\theta}{2}) \end{pmatrix}
$$

Now by multiplying both sides by $$\langle +, t \rvert$$ we obtain the equation for $$c_+$$:

$$
i(\dot{c}_+ + c_+\langle +, t \dot{\vert +, t \rangle} + c_-\langle +, t \dot{\vert -, t \rangle}) = B c_+
$$

where we have used the orthogonality of the instantneous eigenstates. An anlogous equation can be derived for $$\dot{c}_-$$, and evaluating the inner products we obtain a set of two coupled differential equations which can be expressed in matrix form:

$$
i\begin{pmatrix} \dot{c}_+ \\ \dot{c}_- \end{pmatrix} = \begin{pmatrix} B + \omega\sin^2(\frac{\theta}{2}) & \omega\sin(\frac{\theta}{2})\cos(\frac{\theta}{2}) \\ \omega\sin(\frac{\theta}{2})\cos(\frac{\theta}{2}) & -B + \omega\cos^2(\frac{\theta}{2}) \end{pmatrix}\begin{pmatrix} c_+ \\ c_- \end{pmatrix}.
$$

This can be solved via diagonalization (the matrix appearing on the RHS is Hermitian). The result (after solving and plugging in the initial condition of $$\lvert \psi, 0 \rangle = \lvert +, 0 \rangle$$) is:

$$
\lvert \psi, t \rangle = \left[\cos(\frac{\lambda t}{2}) - i\frac{(B - \omega\cos\theta)}{\lambda}\sin(\frac{\lambda t}{2})\right]\lvert +, t \rangle - i\frac{B}{\lambda}\sin\theta\sin(\frac{\lambda t}{2})\lvert -, t \rangle
$$

with $$\lambda = \sqrt{\omega^2 + B^2 - 2\omega B \cos\theta}$$. We can then calculate $$P_+(t)$$ as:

$$
P_+(t) = \lvert \cos(\frac{\lambda t}{2}) - i\frac{(B - \omega\cos\theta)}{\lambda}\sin(\frac{\lambda t}{2})\rvert^2.
$$

Thus we conbclude:
$$
\color{blue}{P_+(t) = \cos^2(\frac{\lambda t}{2}) + \frac{\omega^2\cos^2\theta + B^2 - 2\omega B \cos\theta}{\lambda^2}\sin^2(\frac{\lambda t}{2})}
$$

(c) if $$\omega \ll B$$, then:

$$
\frac{\omega^2\cos^2\theta + B^2 - 2\omega B \cos\theta}{\lambda^2} = \frac{\omega^2\cos^2\theta + B^2 - 2\omega B \cos\theta}{\omega^2 + B^2 - 2\omega B \cos\theta} \approx \frac{B^2}{B^2} = 1 
$$

thus:

$$
\color{blue}{P_+(t) \approx  \cos^2(\frac{\lambda t}{2}) +  \sin^2(\frac{\lambda t}{2}) = 1.}
$$

This is consistent with the adiabatic theorem - because in this limit the magnetic field direction (and hence Hamiltonian) changes slowly, the system remains in the ground state $$\lvert +, t \rangle$$ throughout the evolution.


#### Particle on a 1-D Lattice <a id="problem-qm-onedlattice" name="problem-qm-onedlattice"></a>
**Source:** MIT Spring 2002 Doctoral General Examination Quantum Q1

**Problem Statement:** *Consider a particle confined to move on a 1-D lattice. The Hilbert space is spanned by the orthonormal basis states $$\lvert n \rangle$$ where $$n \in \mathbb{Z}$$ denotes the lattice site and $$\langle n \vert m \rangle = \delta_{nm}$$.*

*(a) Consider the translation operator $$T$$ defined by:*

\begin{equation}\label{eq:transop}
T\lvert n \rangle = \lvert n + 1 \rangle.
\end{equation}

*What are the eigenstates and eigenvalues of $$T$$?*

*(b) Consider the Hamiltonian:*

\begin{equation}\label{eq:latticeH}
H\lvert n \rangle = -\frac{1}{2\Deelta^2}\left(\lvert n + 1 \rangle + \lvert n - 1 \rangle - 2 \lvert n \rangle\right).
\end{equation}

*Does $$T$$ commute with $$H$$? Let $$\lvert \psi_k \rangle$$ be given by:*

\begin{equation}\label{eq:latticeHeigs}
\rangle n \vert \psi_k \rangle = e^{ikn\Delta}.
\end{equation}

*Show that $$\lvert \psi_k \rangle$$ is an eigenstate of $$H$$. What is the relationship between the eigenvalue $$E_k$$ and $$k$$? What is $$E_k$$ as $$k \to 0$$?*

*(c) Add to the Hamiltonian a potential of height $$V$$ at lattice site $$n = 0$$. What is the translation probability through the barrier as a function of $$k, V$$, and $$\Delta$$?*

**Solution:** (a) Since $$T$$ translates by a lattice site, the eigenstates must be an equal weight superposition (up to a phase). For the eigenstates we propose:

$$
\color{blue}{\lvert \theta \rangle = \sum_{n} e^{in\theta}}
$$

with eigenvalue $$\color{blue}{e^{-i\theta}.}$$ As proof:

$$
T\lvert \theta \rangle = \sum_n e^{in\theta} T\lvert n \rangle = \sum_n e^{in\theta}\lvert n + 1 \rangle = \sum_n e^{-i\theta} e^{in\theta}\lvert n \rangle = e^{-i\theta}\lvert \theta \rangle.
$$

(b) We can rewrite:

$$
H = -\frac{1}{2\Delta^2}(T + T^\dagger - 2I)
$$

and since $$T$$ commutes with itself, its Hermitian conjugate, and the identity, we conclude that $$\color{blue}{[T, H] = 0.}$$ Now, verifying that $$\lvert \psi_k \rangle$$ is an eigenstate:

$$
H\lvert \psi_k \rangle = -\frac{1}{2\Delta^2}\sum_n e^{ikn\Delta}(T + T^\dagger - 2I)\lvert n \rangle = e^{ikn\Delta}(\lvert n + 1 \rangle + \lvert n - 1 \rangle  - 2\lvert n \rangle)
$$

Re-indexing the sum to collect terms:

$$
H\lvert \psi_k \rangle =  -\frac{1}{2\Delta^2}\sum_n (e^{i(n-1)k\Delta} + e^{i(n+1)k\Delta} - 2e^{ink\Delta})\lvert n \rangle = -\frac{1}{2\Delta^2}(e^{-ik\Delta} + e^{ik\Delta} - 2) \sum_n e^{ink\Delta}\lvert n \rangle = \frac{1 - \cos(k\Delta)}{\Delta^2} \lvert \psi_k \rangle
$$

where in the last equality we use Euler's identity. Thus the $$\lvert \psi_k \rangle$$ states are eigenstates with eigenvalue $$\color{blue}{\frac{1 - \cos(k\Delta)}{\Delta^2}}$$. The $$k$$ enters the eigenvalue through the cosine term. As $$k \to 0$$, $$\color{blue}{E_k \to 0.}$$

(c) In the presence of the barrier, the Hamiltonian $$H$ is modified:

$$
H = -\frac{1}{2\Delta^2}(T + T^\dagger - 2I) + V\lvert 0 \rangle \langle 0 \rvert
$$

And the eigenstates $$\lvert \psi_k \rangle$$ of (b) are modified to the scattering states $$\lvert S_k \rangle$$ with energy $$E_k$$, where:

$$
\langle n \vert S_k \rangle = e^{ikn\Delta} + Re^{-ikn\Delta} \quad n \leq 0
$$

$$
\langle n \vert S_k \rangle = Te^{ikn\Delta} \quad n \geq 0

$$
\langle 0 \vert S_k \rangle = 1 + R = T
$$

The first equation corresponds to a sum of an incoming wave $$e^{ikn\Delta}$$ and a reflected wave $$Re^{-ikn\Delta}$$ with reflection amplitude $$R$$. The second equation corresponds to the transmitted wave $$Te^{ikn\Delta}$$ with transmission amplitude $$T$$. The third equation has the interpretation of probability conservation through the barrier. Now, we take the eigenvalue equation $$H\lvert S_k \rangle = E_k \lvert S_k \rangle$$ and multiply it by $$\langle 0 \rvert$$, which yields:

$$
-\frac{1}{2\Delta^2}\left(\langle 1 \vert S_k \rangle + \langle - 1 \vert S_k \rangle - 2 \langle 0 \vert S_k \rangle \right) + V \rangle 0 \vert S_k \rangle = E_k \langle 0 \vert S_k \rangle
$$

Using the previously computed expression for $$E_k$$ in (b) and the coefficients of $$\lvert S_k \rangle$$ as defined above, we obtain an equation relating $$T, k, \Delta, V$$:

$$
-\frac{1}{2\Delta^2}\left(Te^{ik\Delta} + e^{-ik\Delta} + (1-T)e^{ik\Delta} - 2T) + VT = -\frac{1}{2\Delta^2}(e^{-ik\Delta} + e^{ik\Delta} - 2)T
$$

which solving for $$T$$ yields:

$$
T = \frac{i\sin k \Delta}{\sin k \Delta + \Delta^2 V}
$$

so we conclude the transmission probability to be:

$$
\color{blue}{\lvert T \rvert^2 = \frac{\sin^2 k \Delta}{\sin^2 k \Delta + \Delta^4 V^2}}
$$


#### Spin-1/2 and Stern-Gerlach <a id="problem-qm-spinhalfsg" name="problem-qm-spinhalfsg"></a>
**Source:** MIT Spring 2001 Doctoral General Examination Quantum Q1

**Problem Statement:** *Consider a spin-1/2 particle where $$S_j = \frac{\hbar}{2}\sigma_j$$ with $$\sigma_j$$ the Pauli matrices of Eq. \eqref{eq:paulis}.*

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

*(c) A beam of spin-1/2 particles enters a Stern-Gerlach filter which allows only particles whose spin is $$+\frac{\hbar}{2}$$ along the $$z$$ direction to pass. the particles then pass through a region where there is a magnetic field $$\vec{B} = (0, B, 0)$$ and spend time $$T$$ in this region. Then the particles enter a Stern-Gerlach filter which allows only particles whose spin is $$+\frac{\hbar}{2}$$ along the $$x$$ direction to pass. What fraction of the electrons which exit the first filter exit the second? Assume that the particles interact with the magnetic field via $$H = -\sum_j B_jS_j$$.* 

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
[a^\dagger, a] = [\frac{1}{\sqrt{2\hbar\omega}}(\omega x - ip), \frac{1}{\sqrt{2\hbar\omega}}(\omega x + ip)] = \frac{1}{2\hbar\omega}([\omega x, \omega x] + [\omega x, ip] - [ip, \omega x] - [ip, ip]) = -1
$$

where we have used the canonical commutation relation $$[x, p] = i\hbar$$. Thus the operator exponential identity of Eq. \eqref{eq:opexponential} applies. Now calculating the probability of measuring $$E_j = \hbar\omega(j + \frac{1}{2})$$ using the Born rule, we have:

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