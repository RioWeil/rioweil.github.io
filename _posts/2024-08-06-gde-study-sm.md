---
layout: post
title: "UChicago Graduate Diagnostic Exam Prep - Statistical Mechanics"
date: 2024-08-06
description: Interesting statistical mechanics problems solved while studying for the graduate diagnostic exam.
categories: physics uchicago
---
**July 18, 2024.** *Before the start of my PhD program at UChicago this fall, there is a diagnostic exam to test knowledge/ability in the core subjects of classical mechanics, electromagnetism, quantum mechanics, and statistical mechanics. Here, I share some interesting problems and solutions I came across while preparing for this exam. This is the second post in this series, where I go through statistical mechanics problems.*

### Contents
- <a href="#problem-sm-lennardjonescrystal" name="#problem-sm-lennardjonescrystal"> Lennard-Jones Crystal</a>
- <a href="#problem-sm-nonidealgas" name="#problem-sm-nonidealgas"> Non-Ideal Gas</a>
- <a href="#problem-sm-spin1" name="#problem-sm-spin1"> Spin-1 Paramagnet</a>
- <a href="#problem-sm-asymrandwalk" name="#problem-sm-asymrandwalk"> Asymmetric Random Walk</a>
- <a href="#problem-sm-bosefermigases" name="#problem-sm-bosefermigases"> Bose and Fermi Gases</a>

#### Lennard-Jones Crystal <a id="problem-sm-lennardjonescrystal" name="problem-sm-lennardjonescrystal"></a>
**Source:** UBC Spring 2024 Physics Qualifying Exam Q4

**Problem Statement:** *The interaction potential between atoms of mass $M$ is given by a Lennard-Jones potential:*
\begin{equation}\label{eq:lennardjones}
u(x) = \frac{A}{x^{12}} - \frac{B}{x^6}
\end{equation}
*Here $A$ and $B$ are positive constants. Consider a crystal formed from these atoms, with a cubic lattice structure. Calculate the density of the crystal. Give an expression for its specific heat capacity in the low temperature limit. Consider only the interactions of each atom with its six nearest neighbours. Calculate as well the approximate binding energy of the quantum mechanical ground state for the diatomic molecule formed from these atoms.*

**Solution:** We first find the equilibrium spacing $$x_0$$ that minimizes the potential energy. To this end we set the derivative of $$u(x)$$ to zero:

$$
\left.\frac{du}{dx}\right|_{x=x_0} = -12\frac{A}{x_0^{13}} + 6\frac{B}{x_0^7} = 0 \implies x_0 = \sqrt[6]{\frac{2A}{B}}
$$

At equilibrium the atoms in the crystal are all $$x_0$$ apart, and hence there is a single atom inside a cube of volume $$x_0^3$$; hence the number density of the crystal is:

$$
\color{blue}{\rho = \frac{N}{V} = \frac{1}{x_0^3} = \sqrt{\frac{B}{2A}}}
$$

and the mass density is obtained by multiplying the above by $$M$$, The high-temperature limit of the heat capacity is simple; each atom in the crystal has 6 degrees of freedom (3 translational and 3 vibrational) which contributes $$\frac{1}{2}kT$$ energy via the equipartition theorem, and thus the energy is $$U = 6 \frac{1}{2}NkT = 3NkT$$ and the specific heat capacity is $$C_V = \frac{dU}{dT} = 3Nk$$ (the Dulong-Petit Law). The low-temperature heat capacity requires more careful thought. First, since we consider the low-temperature limit, we can approximate the interatomic potential by Taylor expansion around the minimum $$x = x_0$$. This yields:

$$
u(x) \approx u(x_0) + \left.\frac{du}{dx}\right|_{x=x_0}(x - x_0) + \left.\frac{d^2u}{dx^2}\right|_{x=x_0}(x-x_0)^2 = -\frac{B^2}{4A} + 0 + \left(\frac{156A}{x_0^{14}} - \frac{42B}{x_0^8}\right)(x - x_0)^2
$$

We can drop the constant term (it will not matter for the heat capacity) and define $$\frac{1}{2}k = \left(\frac{156A}{x_0^{14}} - \frac{42B}{x_0^8}\right)$$. Now, in a significant approximation we calculate the heat capacity assuming that each of atoms in the crystal can be treated as independent Harmonic oscillators (this is the so-called ``Einstein model'' of solids - a more accurate low-$T$ picture can be obtained using the Debye theory of solids (as discussed in the PHYS 502 lecture notes [here](/notes/)) but this seemed too complicated/esoteric to be derived in an exam setting, so we take the simpler approach). In particular, each atom oscillates independently in $x, y, z$ and so we have $3N$ harmonic oscillators in the crystal in total, with energies given by:

$$
E_n = \hbar\omega\left(n + \frac{1}{2}\right)
$$

with $$\omega = \sqrt{k/M}$$. We drop the zero-point energy as it does not contribute to the heat capacity. The partition function for a single one of these oscillators is then:

$$
Z = \sum_{n=0}^\infty \exp(-\beta E_n) = \sum_{n=0}^\infty \exp\left(-\hbar\omega\left(n + \frac{1}{2}\right)\right) = \frac{\exp(-\beta \hbar \omega/2)}{1 - \exp(-\beta\hbar\omega)}
$$

where $$\beta = \frac{1}{kT}$$ and we use the geometric series in the last equality. The mean energy per oscillator is then:

$$
U = -\frac{d\ln Z}{d\beta} = \frac{\hbar\omega}{2} + \frac{\hbar\omega}{\exp(\beta\hbar\omega) - 1}
$$

so the mean total energy of the crystal is:
$$
U = 3N \left(\frac{\hbar\omega}{2} + \frac{\hbar\omega}{\exp(\beta\hbar\omega) - 1}\right)
$$

and thus we can obtain the heat capacity:

$$
C_V = \frac{\partial U}{\partial T} = -k\beta^2 \frac{\partial U}{\partial \beta} = 3Nk\frac{(\beta\hbar\omega)^2\exp(\beta\hbar\omega)}{(\exp(\beta\hbar\omega) - 1)^2}
$$

which in the low $$T$$ limit becomes:

$$
\color{blue}{C_V = 3Nk(\beta\hbar\omega)^2\exp(-\beta\hbar\omega).}
$$

The binding energy for the quantum mechanical ground state for the diatomic molecule formed by these atoms is simply the energy needed to break apart the atoms from the equilibrium distance $x_0$ to infinity. The energy at the equilibrium distance was calculated in the Taylor expansion to be $$-\frac{B^2}{2A}$$, and to this we can add the zero point energy of $$\frac{1}{2}\hbar\omega$$. At infinity we have $$\lim_{x \to \infty}u(x) = 0$$ and so the binding energy is simply the ground state energy:

$$
\color{blue}{E_0 = -\frac{B^2}{2A} + \frac{1}{2}\hbar\omega.}
$$

#### Non-Ideal Gas <a id="problem-sm-nonidealgas" name="problem-sm-nonidealgas"></a>
**Source:** UChicago 2014 Statistical Mechanics Graduate Diagnostic Exam Q1

**Problem Statement:** *Consider a gas with the equation of state relating the pressure $$P$$ to the volume $$V$$, temperature $$T$$ and the number of moles $$N$:*

\begin{equation}\label{eq:nonidealgas}
    p = \frac{NkT}{V + a/T^2}.
\end{equation}

*where $$a$$ is a constant. Compute $$\left(\frac{\partial E}{\partial V}\right)_{T}$$ for this gas, comparing your answer to that for an ideal gas.*

**Solution:** 


We recall from the first law of thermodynamics that $$E = W + Q$ and then from the definitions of work/entropy that 

$$
dE = dW + dQ = -PdV + TdS. 
$$

taking the partial derviative with respect to volume, holding $$T$$ constant we obtain:

$$
\left(\frac{\partial E}{\partial V}\right)_{T} = -P\left(\frac{\partial V}{\partial V}\right)_{T} + T\left(\frac{\partial S}{\partial V}\right)_{T} = -P + T\left(\frac{\partial S}{\partial V}\right)_{T}
$$

The problem reduces to computing the partial derivative of the entropy. To this end recall the expression for the free energy $$F = U + TS$$ and its differential change:

$$
dF = dU - TdS - SdT = (-PdV + TdS) - TdS - SdT = -pdV - SdT.
$$

From this expression we find that $$\left(\frac{\partial F}{\partial T}\right)_V = -S$$ and $$\left(\frac{\partial F}{\partial V}\right)_T = -P$$, and via the equality of partial derivatives we obtain the Maxwell relation:

$$
\left(\frac{\partial S}{\partial V}\right)_{T} = \left(\frac{\partial P}{\partial T}\right)_{V}.
$$

The RHS we can compute for Eq. \eqref{eq:nonidealgas} via the quotient rule:

$$
\left(\frac{\partial P}{\partial T}\right)_{V} = Nk\left(\frac{V + \frac{3a}{T^2}}{(V + \frac{a}{T})^2}\right)
$$

so by substituting into our initial expression we conclude:

$$
\color{blue}{\left(\frac{\partial E}{\partial V}\right)_{T} = -P + NkT\left(\frac{V + \frac{3a}{T^2}}{(V + \frac{a}{T})^2}\right).}
$$

In the case of an ideal gas, we have that $$\color{blue}{\left(\frac{\partial E}{\partial V}\right)_{T} = 0}$$ as the internal energy of an ideal gas only depends on temperature; we can also recover this from the general expression we have derived by setting $$a=0$$:

$$
\left(\frac{\partial E}{\partial V}\right)_{T} = -P + NkT\frac{V}{V^2} = -P + P = 0.
$$

In comparison with the ideal result, for $$a > 0$$ we find that the energy decreases with increasing volume at fixed temperature, due to the interactions between atoms.

#### Spin-1 Paramagnet <a id="problem-sm-spin1" name="problem-sm-spin1"></a>
**Source:** UChicago 2014 Statistical Mechanics Graduate Diagnostic Exam Q2

**Problem Statement:** *Consider a system of $$N$$ non-interacting quantum spins coupled to a magnetic field $$B$$ pointing in the $$z$$ direction. Each spin has $$s = 1$$ and can be in three states, $$s_z = \{-1, 0, 1\}$$, with energy $$E = -\mu s_z B$$. We ignore all degrees of freedom except spin.*

*(a) Calculate the partition function $$Z$$ of the spin system as a function of the temperature $$T$$ and magnetic field $$B$.*

*(b) Find the energy $$E$$ and heat capacity $$C$$ of the spin system as a function of $$T$$ and $$B$$.*

*(c) Find the entropy $$S$$ of the spin system and discuss its behavior in the limit $$T \to 0$$ and $$T \to \infty$$.*

*(d) Find the total magnetization $$M_z = \mu \sum_{i=1}^N \langle s_z^i \rangle$$ of the spin system. Show that the zero field susceptibility $$\chi = \left[\frac{\partial M_z}{\partial B}\right]_{B=0}$$ obeys the Curie law $$\chi = \frac{c}{T}$$ and find the constant of proportionality.*

**Solution:** We first calculate the partition function for a single spin:

$$
Z_1 = \sum_i e^{-\frac{E_i}{k_B T}} = e^{-\frac{\mu B}{k_B T}} + 1 + e^{\frac{\mu B}{k_B T}} = 1 + 2\cosh(\frac{\mu B}{k_B T})
$$

since the spins are non-interacting, the $$N$$-spin partition function is obtained by taking the $$N$$-fold product over the single spin partition function:

$$
\color{blue}{Z = (Z_1)^N = \left(1 + 2\cosh(\frac{\mu B}{k_B T})\right)^N}
$$

(b) The average energy is given by:

$$
E = \frac{\sum_i E_i e^{-\frac{E_i}{k_B T}}}{Z} = k_B T^2\frac{\partial \ln Z}{\partial T}
$$

Therefore we compute:

$$
E = k_B T^2 \frac{\partial}{\partial T}\left(N\ln\left(1 + 2\cosh(\frac{\mu B}{k_B T})\right)\right) = -k_B T^2 \frac{\mu B}{k_B T^2} N \frac{2\sinh(\frac{\mu B}{k_B T})}{1 + 2\cosh(\frac{\mu B}{k_B T})}
$$

thus we conclude:

$$
\color{blue}{E = -2\mu B N\frac{\sinh(\frac{\mu B}{k_B T})}{1 + 2\cosh(\frac{\mu B}{k_B T})}}
$$

We also compute the heat capacity:

$$
\color{blue}{C = \frac{\partial E}{\partial T} = \frac{2\mu^2B^2N}{k_B T^2}\frac{\cosh(\frac{\mu B}{k_B T}) + 2\cosh^2(\frac{\mu B}{k_B T}) - 2\sinh^2(\frac{\mu B}{k_B T})}{(1 + 2\cosh(\frac{\mu B}{k_B T}))^2}}
$$

(c) We compute the entropy from the free energy:

$$
S = \frac{\partial F}{\partial T} = \frac{\partial}{\partial T}\left(k_B T \ln Z\right)
$$

which substituting in $$Z$$ and carrying out the computation we obtain:

$$
S = Nk_B\left[\ln(1 + 2\cosh(\frac{\mu B}{k_B T})) - \frac{2\mu B}{k_B T}\frac{\sinh(\frac{\mu B}{k_B T})}{1 + 2\cosh(\frac{\mu B}{k_B T})}\right]
$$

As $$T \to 0$$ we find that $$\cosh(\frac{\mu B}{k_B T}) \to \frac{e^{\frac{\mu B}{k_B T}}}{2}$$, $$\sinh(\frac{\mu B}{k_B T}) \to \frac{e^{\frac{\mu B}{k_B T}}}{2}$$ and the above becomes:

$$
\color{blue}{\lim_{T \to 0}S = Nk_B\left(\frac{\mu B}{k_B T} - \frac{\mu B}{k_B T}\right) = 0}
$$

which makes physical sense as at $$T = 0$$ all the spins are in the ground state of $$s_{z} = 1$$ with unit probability and therefore each has entropy zero. As $$T \to \infty$$, $$\cosh(\frac{\mu B}{k_B T}) \to 1$$ and $$\sinh(\frac{\mu B}{k_B T}) \to \frac{\mu B}{k_B T} \to 0 $$ and so taking the limit:

$$
\color{blue}{\lim_{T \to \infty}S = Nk_B\left(\ln(1 + 2) - 0\right) = Nk_B\ln 3}
$$

which also makes physical sense as at $$T \to \infty$$, all three spin states are equally probable and thus each spin contributes $$k_B \ln(3)$$ of entropy (the entropy of a classical ``trit'').

(d) Since $$E^i = -\mu B s_z^i$$, $$s_z^i = -\frac{E_i}{\mu B}$$ and so computing the magnetization amounts to the average energy with a prefactor:

$$
\color{blue}{M_z = 2\mu N\frac{\sinh(\frac{\mu B}{k_B T})}{1 + 2\cosh(\frac{\mu B}{k_B T})}}
$$

Taking the derivative w.r.t. $$B$$ and then setting $$B = 0$$, we find:

$$
\color{blue}{\chi = \left[\frac{\partial M_z}{\partial B}\right]_{B=0} = \frac{2\mu^2 N}{3k_B T}}
$$

so the Curie law is satisfied with $$\color{blue}{c = \frac{2}{3}\frac{\mu^2N}{k_B}.}$$

#### Asymmetric Random Walk <a id="problem-sm-asymrandwalk" name="problem-sm-asymrandwalk"></a>
**Source:** UChicago 2014 Statistical Mechanics Graduate Diagnostic Exam Q3

*Consider a particle moving in one dimension that can take random steps to the left or right of unit length. The probability of taking the step to the right is $$p$$ and to the left is $$q = 1 - p$$. Assume that the steps are statistically independent and call the total number of steps $$N$$.*

*(a) Calculate the probability of taking $$n_R$$ steps to the right and $$n_L = N - n_R$$ steps to the left in any order.*

*(b) Calculate the average values $$\langle n_R \rangle, \langle n_R^2 \rangle$$, and the dispersion $$\langle \Delta n_R^2 \rangle = \langle (n_R - \langle n_R \rangle)^2 \rangle$$.*

*(c)Show that for very large $$N$$ the probability of taking $$n_R$$ steps to the right has the form:*

\begin{equation}\label{eq:Gaussianrwalk}
    C\exp(-\frac{(n_R - x)^2}{y})
\end{equation}

*and determine $$C, x, y$$ in terms of $$N, p$$. You may find Stirling's approximation useful:*

\begin{equation}\label{eq:Stirling}
    \log N! \approx N\log N  N, \quad N \gg 1
\end{equation}

**Solution:** (a) Note that throughout we abuse notation and use $$n_R$$ to denote both a number of steps right and the random variable corresponding to the number of steps right. It will be generally clear from context which is meant. There are $$\binom{N}{n_R}$$ ways to choose $$n_R$$ steps out of $$N$$ to be to the right, and each has probability $$p^{n_R}(1-p)^{N - n_R}$$. Thus:

$$
\color{blue}{P(n_R) = \frac{N!}{n_R!(N-n_R)!}p^{n_R}(1-p)^{N - n_R}}
$$

(b) Define the random variable $$n_j$$ such that $$n_j = 1$$ if the $$j$$th step is to the right and 0 otherwise. Then, $$P(n_j = 1) = p$$ and $$P(n_j = 0) = 1-p$$. The expectation of $$n_j$$ is then simply:

$$
\langle n_j \rangle = 1 \cdot p + 0 \cdot (1-p) = p.
$$

Furthermore, since each step is independent we can write the random variable corresponding to the total number of right steps is $$n_R = \sum_{j=1}^N n_j$$. Then by the linearity of expectation:

$$
\langle n_R \rangle = \sum_{j=1}^N \langle n_j \rangle = \sum_{j=1}^N p
$$

and so:

$$
\color{blue}{\langle n_R \rangle = pN.}
$$

Next, we consider the random variable $$n_in_j$$ which is one if $$n_i = n_j = 1$$ and $$0$$ if either are zero. Then $$P(n_in_j = 1) = p^2$$ and $$P(n_in_j) = 1-p^2$$ if $$i \neq j$$, and $$P(n_i^2 = 1) = P(n_i = 1) = p$$ and $$P(n_i^2 = 0) = P(n_i = 0) = 1-p$$. Thus:

$$
\langle n_in_j\rangle = 1 \cdot p^2 + 0 \cdot (1-p^2) = p^2
$$


$$
\langle n_in^2\rangle = 1 \cdot p + 0 \cdot (1-p) = p
$$

Thus computing $$\langle n_R^2 \rangle$$ using the linearity of expectation again:

$$
\langle n_R^2 \rangle = \sum_{i=1}^N \sum_{j=1}^N \langle n_i n_j \rangle = \sum_{i=1}^N \langle n_i^2 \rangle + \sum_{i \neq j} \sum_{j=1}^N \langle n_i n_j \rangle = \sum_{i=1}^N p + \sum_{i \neq j} \sum_{j=1}^N p^2
$$

Thus:

$$
\color{blue}{\langle n_R^2 \rangle = Np + N(N-1)p^2 = N^2p^2 + Np(1-p).}
$$

Finally, for the dispersion we note that:

$$
\langle \Delta n_R^2 \rangle = \langle (n_R - \langle n_R \rangle)^2 \rangle =  \langle n_R^2 - 2\langle n_R \rangle n_R + \langle n_R \rangle^2 \rangle = \langle n_R^2 \rangle - \langle n_R \rangle^2
$$

and therefore using our two prior results:

$$
\color{blue}{\langle n_R^2 \rangle = N^2p^2 + Np(1-p) - (Np)^2 = Np(1-p).}
$$

(c) We define $$n = 2n_R - N$$ so that $$n_R = \frac{N + n}{2}$$ and $$N - n_R = \frac{N - n}{2}$$, as well as $$r = p - \frac{1}{2}$$ so that $$p = \frac{1}{2} + r$$ and $$1-p = \frac{1}{2} - r$$. Then our result from part (a) becomes:

$$
P(n) = \frac{N!}{\left(\frac{N + n}{2}\right)!\left(\frac{N - n}{2}\right)!}\left(\frac{1}{2} + r\right)^{\frac{N + n}{2}}\left(\frac{1}{2} - r\right)^{\frac{N - n}{2}}
$$

Taking the logarithm:

$$
\ln(P(n)) = \ln N! - \ln \left(\frac{N + n}{2}\right)! - \ln\left(\frac{N - n}{2}\right)! + \frac{N + n}{2}\ln(\frac{1}{2} + r) + \frac{N-n}{2}\ln(\frac{1}{2} - r)
$$

Using the Sterling approximation, the above becomes:

$$
\ln(P(n)) = N\ln N - \frac{N + n}{2}\ln(\frac{N + n}{2}) - \frac{N - n}{2}\ln(\frac{N - n}{2}) + \frac{N + n}{2}\ln(\frac{1}{2} + r) + \frac{N-n}{2}\ln(\frac{1}{2} - r)
$$

where we note the cancellation of $$N - \frac{N + n}{2} - \frac{N - n}{2} = 0$$.  Now using the second-order Taylor expansion of the logarithm, we note that:

$$
\ln(\frac{N \pm n}{2}) \approx \ln(\frac{N}{2}) \pm \frac{n}{N} - \frac{1}{2}\left(\frac{n}{N}\right)^2
$$

Thus, $$\ln(P(n))$$ reduces to:

$$
\ln(P(n)) \approx -\frac{n^2}{2N} + N\ln(2) + \frac{N + n}{2}\ln(\frac{1}{2} + r) + \frac{N - n}{2}\ln(\frac{1}{2} - r)
$$

Again we make use of the Taylor expansion of the logarithm, noting that:

$$
\ln(\frac{1}{2} \pm r) \approx -\ln(2) \pm 2r - \frac{1}{2}(2r)^2 = -\ln(2) \pm 2r - 2r^2
$$

so $$\ln(P(n))$$ further simplifies:

$$
\ln(P(n)) \approx -\frac{n^2}{2N} + 2nr - 2Nr^2
$$

Thus:

$$
P(n) \approx \exp(\frac{-(n - 2Nr)^2}{2N})
$$

or converting back to $$n_R, p$$:

$$
\color{blue}{P(n) = \exp(\frac{-(n_R - Np)^2}{\frac{N}{2}})}
$$

so the claim is proven, with:

$$
\color{blue}{C = 1, \quad x = Np, \quad y = \frac{N}{2}.}
$$

#### Bose and Fermi Gases <a id="problem-sm-bosefermigases" name="problem-sm-bosefermigases"></a>
**Source:** UChicago 2014 Statistical Mechanics Graduate Diagnostic Exam Q4

*(a) To begin, consider a general many-particle system in thermal equilibrium. Let $$F$$ denote the free energy $$F = -k_B T\ln Z$$ where:*

\begin{equation}\label{eq:grandcanonicalpartition}
Z = \sum_{\text{states}} e^{-E_{\text{tot}}/k_B T}
\end{equation}

*is the (grand) partition function. Using the fact that hte entropy is given by $$S = -\frac{\partial F}{\partial T}$$, show that the expectation value $$\langle E_{\text{tot}} \rangle$$ of the total energy of the system can be written as $$\langle E_{\text{tot}} \rangle = F + TS$$.*

*(b) Consider a photon gas confined to a box of volume $$V$$. Recall that photons have a dispersion relation $$E = \hbar c \lvert \vec{k} \rvert$$. Write down an integral expression for the free energy $$F_{ph}$$ of hte photon gas of the form:*

\begin{equation}\label{eq:photongasF}
    F_{ph} = \int d^3 \vec{k} g(\lvert \vec{k} \rvert)
\end{equation}

*and find the function $$g$$. You do not need to evaluate the resulting integral, but you should carry out any other sums that appear in your result.*

*(c) Now consider a gas of electrons and positrons confined to a box of volume $$V$$. Assume the temperature satisfies $$k_B T \gg m_e c^2$$, where $$m_e$$ is the mass of the electron, so that electrons and positrons can be treated as ultra-relativistic particles with dispersion relation $$E = \hbar c \lvert \vec{k} \rvert$$. Suppose also that both particles are at vanishing chemical potential $$\mu_{e^-} = \mu_{e^+} = 0$$. As in part (b), write down an integral expression for the free energy $$F_e$$ of the electron/positron gas of the form:*

\begin{equation}\label{eq:epgasF}
F_e(V, T) = \int d^3\vec{k} h(\lvert \vec{k} \rvert)
\end{equation}

*and find the function $$h$$. You can treat the electrons and positrons as non-interacting particles.*

*(d) With a little work, the above integrals can be evaluated as:*

\begin{equation}\label{eq:gasFs}
F_{ph}(V, T) = -\frac{\pi^2}{45}\frac{(k_BT)^4}{(\hbar c)^3}V, \quad F_{e}(V, T) = -\frac{7\pi^2}{180}\frac{(k_BT)^4}{(\hbar c)^3}V,
\end{equation}

*Imagine we have a box containing a mixture of electrons, positrons, and photons with $$\mu_{e^-} = \mu_{e^+} = 0$$. We slowly compress the box from an initial volume $$V_i$$ to a final volume $$V_f$$, while keeping it thermally insulated during the process. Suppose that the initial temperature satisfies $$k_BT_i \ll m_e c^2$$ so that only photons significantly contribute to its contents, while the final temperature satisfies $$k_B T_f \gg m_e c^2$$ so that the final mixture includes both photons and ultra-relativistic electrons and positrons. Find the final temperature $$T_f$$.*

**Solution:** (a) We recall from (b) of <a href="#problem-sm-spin1" name="#problem-sm-spin1"> Spin-1 Paramagnet</a> that:

$$
\langle E_{\text{tot}} \rangle = k_B T^2\frac{\partial \ln Z}{\partial T}
$$

We also compute, using the definition of the free energy and entropy:

$$
F + TS = -k_B T \ln Z + T \left(-\frac{\partial}{\partial T}\left(-k_B T \ln Z\right)\right) = -k_B T \ln Z + k_B T\ln Z + k_B T^2\frac{\partial \ln Z}{\partial T} = k_B T^2\frac{\partial \ln Z}{\partial T}
$$

thus:

$$
\color{blue}{\langle E_{\text{tot}} \rangle = F + TS}
$$

(b) Denoting $$n_{\alpha}(\vec{k})$$ as the number of photons with polarization $$\alpha$$ and wavevector $$\vec{k}$$, the Hamiltonian of the system can be written as:

$$
H = \sum_{\{n_\alpha(\vec{k})\}} \hbar c \lvert \vec{k} \rvert \left(n_{\alpha}(\vec{k}) + \frac{1}{2}\right)
$$

The (grand) partition function for this system is then:

$$
Z = \sum_{\{n_\alpha(\vec{k})\}}\exp(-\frac{\hbar c}{k_B T}\lvert \vec{k} \rvert \left(n_{\alpha}(\vec{k})+ \frac{1}{2}\right))
$$

where we note that photons have zero chemical potential (as they can be created/destroyed at no cost) and as such this term is absent from $$Z$$. We can convert the above to a product over polarizations/wavevectors and a sum over occupation numbers, noting that photons are bosons and thus each state can be occupied by an arbitrary number of photons:

$$
Z = \prod_{\alpha, \vec{k}} \sum_{n=0}^\infty \exp(-\frac{\hbar c}{k_B T}\lvert \vec{k} \rvert \left(n+ \frac{1}{2}\right))
$$

which we evaluate using the geometric series:

$$
Z = \prod_{\alpha, \vec{k}} \frac{\exp(-\frac{\hbar c}{2k_B T}\lvert \vec{k} \rvert)}{1 - \exp(-\frac{\hbar c}{k_B T}\lvert \vec{k} \rvert)}
$$

Now we can compute the free energy:

$$
F_{ph}(V, T) = -k_B T \ln(\prod_{\alpha, \vec{k}} \frac{\exp(-\frac{\hbar c}{2k_B T}\lvert \vec{k} \rvert)}{1 - \exp(-\frac{\hbar c}{2k_B T}\lvert \vec{k} \rvert)}) = -k_B T \sum_{\alpha, \vec{k}}\left[-\frac{\hbar c}{2 k_B T}\lvert \vec{k} \rvert - \ln(1 - \exp(-\frac{\hbar c}{k_B T}\lvert \vec{k} \rvert))\right]
$$

We sum over the two polarization states (which incurs a factor of two) and convert the sum over wavevectors into an integral $$\sum_{\vec{k}} \to \frac{V}{(2\pi)^3}\int d^3\vec{k}$$ from which we obtain:

$$
\color{blue}{F_{ph}(V, T) = \int d^3\vec{k}\frac{2V}{(2\pi)^3}\left[\frac{\hbar c \lvert \vec{k} \rvert}{2} + k_B T \ln(1 - \exp(-\frac{\hbar c}{k_B T}\lvert \vec{k} \rvert))\right]}
$$

with the integrand identified as $$g(\lvert \vec{k} \rvert)$$. 

(c) The derivation is identical to (b), only now that (i) there is a prefactor of two in the energy as we have the (equal) contributions from the electrons and positrons and (ii) electrons/positrons are fermions, so the occupation number sum is only over $$n = 0, 1$$:

$$
\sum_{n=0}^1  \exp(-\frac{2 \hbar c}{k_B T}\lvert \vec{k} \rvert \left(n+ \frac{1}{2}\right)) = \exp(-\frac{\hbar c}{k_B T}\lvert \vec{k} \rvert)\left[1 + \exp(-\frac{2\hbar c}{k_B T}\lvert \vec{k} \rvert)\right]
$$

Our final result is:

$$
\color{blue}{F_e(V, T) = \int d^3\vec{k}\frac{2V}{(2\pi)^3}\left[\hbar c \lvert \vec{k} \rvert + k_B T \ln(1 + \exp(-\frac{2\hbar c}{k_B T}\lvert \vec{k} \rvert))\right]}
$$

with the integrand as $$h(\lvert \vec{k} \rvert)$$. 

(d) Since the box is kept thermally insulated through the compression, $$\Delta F = 0$$ through the evolution. We use Eq. \eqref{eq:gasFs} for the free energies. At the initial temperature/pressure we just have the photon contribution:

$$
F_i = -\frac{\pi^2}{45}\frac{(k_B T_i)^4}{(\hbar c)^3}V_i
$$

and at the final temperature/pressure we have the photon and electron/positron contribution:

$$
F_f = -\frac{\pi^2}{45}\frac{(k_B T_f)^4}{(\hbar c)^3}V_f -\frac{7\pi^2}{180}\frac{(k_B T_f)^4}{(\hbar c)^3}V_f
$$

equating $$F_i$$ and $$F_f$$ and solving for $$T_f$$ we conclude:

$$
\color{blue}{T_f = T_i\sqrt[4]{\frac{4}{11}\frac{V_i}{V_f}}.}
$$
