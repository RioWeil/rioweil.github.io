---
layout: post
title: Generalizing the qubit
date: 2022-07-12
description: A geometric visualization of density operators for two-state systems.
categories: physics quantum
---
**July 12, 2022.** *The density operator is discussed in quantum mechanics courses as a generalization of the state ket, allowing one to represent probabilistic mixtures and not just pure states. In this post, we provide a geometric visualization of this generalization, by showing how the correspondence of qubit state kets to points on the Bloch sphere extends to the correspondence of density operators to points on the Bloch ball.*

### The Qubit and the Bloch sphere
The qubit, or quantum bit (alternatively known as the quantum two-level system, or spin-1/2 system) is the simplest example of an interesting quantum system. Given computational basis states $$\lvert 0 \rangle$$ and $$\lvert 1 \rangle$$, a general qubit state is an arbitrary superposition of the basis states:

\begin{equation}\label{qubit}
\lvert \psi \rangle = \alpha \lvert 0 \rangle + \beta \lvert 1 \rangle
\end{equation}

Where the ambient Hilbert space in which the state lives is taken to be $$\mathcal{H} = \mathbb{C}^2$$. A helpful visualization of the qubit is as a vector on the surface of the unit ball in $$\mathbb{R}^3$$, known as the Bloch sphere. To obtain this, we make two observations. First, the qubit state $$\lvert \psi \rangle$$ must be normalized, enforcing:

$$
\lvert \alpha \rvert^2 + \lvert \beta \rvert^2 = 1
$$

with the above condition, we can without loss of generality let $$\lvert \alpha \rvert = \cos(\theta/2)$$, $$\lvert \beta \rvert = \sin(\theta/2)$$ for some $$0 \leq \theta \leq \pi$$. The second observation is that the global phase of a quantum state is irrelevant; since any quantum experiment can only measure probabilities (according to the Born rule) $$p(j) = \langle \psi \rvert \Pi_j \lvert \psi \rangle$$ (where $\Pi_j$ is the projector corresponding to outcome $$j$$), we can see that $$\lvert \psi \rangle$$ and $$e^{i\varphi}\lvert \psi \rangle$$ physically represent the same state as they yield the same probabilities:

$$p'(j) = \langle \psi \rvert e^{-i\varphi} \Pi_j e^{i\varphi}\lvert \psi \rangle = \langle \psi \rvert e^{-i\varphi}e^{i\varphi} \Pi_j \lvert \psi \rangle= \langle \psi \rvert \Pi_j \lvert \psi \rangle = p(j).$$ 

Since the global phase is irrelevant, we can WLOG take $$\alpha$$ to be real (by factoring out a phase). The two qubit state can then be written as:

\begin{equation}
    \lvert \psi \rangle = \cos(\theta/2)\lvert 0 \rangle + e^{i\varphi}\sin(\theta/2)\lvert 1 \rangle
\end{equation}

where $$0 \leq \varphi < 2\pi$$. Given this form, we conclude that $$\lvert \psi \rangle$$ can be viewed as a point on the two-sphere, parameterized by the polar angle $$\theta$$ and the azimuthal angle $$\varphi$$, as shown below.

<p align="center">
    <img src="/assets/img/qubit.pdf" alt = "Visualization of qubit state as a point on the 2-sphere." width= "50%" height="auto">
</p>


### Introducing the density operator
A first treatment of quantum mechanics tends to focus on the position space wavefunction $$\psi(\mathbf{r})$$ describing the position statistics of a quantum system. A level of abstraction then follows when one considers the quantum state kets $$\lvert \psi \rangle$$ which contains all such statistical information of a quantum system. However, there is one further level of abstraction/generalization in discussing quantum states, which is describing them in terms of density operators[^1] $$\rho$$.

[^1]: Note that a more rigorous/mathematical treatment of quantum mechanics, such as that presented in Frederic Shuller's [lecture series](https://www.youtube.com/watch?v=GbqA9Xn_iM0&list=PLPH7f_7ZlzxQVx5jRjbfRGEzWY_upS5K6) starts with quantum states as density operators, and in fact would argue against having the elements of the Hilbert space (i.e. vectors/kets) be described as the states. However, we here will stick with the conventional manner in which density operators are introduced in a standard physics curriculum.

A good motivating example for density operators is the Stern-Gerlach experiment. Recall in this experiment that a beam of silver atoms (with unpaired 47th electron, contributing a net spin of 1/2 to the atoms) is prepared in an oven, then sent through an inhomogenous magnetic field that deflects the atoms (in one of two opposite directions) with the deflection corresponding to the measured spin. After the measurement, the spin states of the atoms are totally clear, being one of two spin eigenstates. However, how are we to describe the state of the atoms *before* they are measured?

A first attempt at a description would be as follows. Suppose the Stern-Gerlach apparatus measured the $$z$$-component of the spin of the atoms. Then, there is a 50% chance of measuring $$+\hbar/2$$ (corresponding to a post measurement state of $$\lvert 0 \rangle$$), and a 50% chance of measuring $$-\hbar/2$$ (corresponding to a post-measurement state of $$\lvert 1 \rangle$$). Therefore, the state before the measurement should reflect these measurement statistics, giving us:

$$
\lvert \psi \rangle = \frac{1}{\sqrt{2}}\lvert 0 \rangle + \frac{1}{\sqrt{2}} \lvert 1 \rangle.
$$

However, there is an immediate problem with this conclusion; the above state is just the Pauli-X eigenstate $$\lvert + \rangle$$. If this was indeed the pre-measurement state, then if we had done a measurement of the $$x$$-component of spin, then we would only measure the outcome $$+\hbar/2$$ (i.e. there would be only one dot on the measurement screen). However, this is not the case; the atoms released by the oven are totaly unpolarized, so no matter what direction of the spin we measure, we should see a 50/50 split between measurement outcomes. So, our conclusion must be incorrect. Our mistake was subtle; we wanted to represent our state as a *probabilistic mixture* of the $$\lvert 0 \rangle$$ and $$\lvert 1 \rangle$$ states, and not as a coherent superposition of them. However, our current state ket formalism only allows for the latter. What we therefore consider is an *ensemble* of states. An ensemble of states is defined as a set of tuples $$\mathcal{E} = \{ (p_i, \lvert \psi_i \rangle)\}_{i}$$ where the $$p_i$$s correspond to the probability that one has the state $$\lvert \psi_i \rangle \in \mathcal{H}$$. Note that the $p_i$s are real and sum to 1, as they are probabilities. For our example with the Stern-Gerlach experiment pre-measurement state, one possible ensemble that describes this is:

$$
\mathcal{E} = \{(1/2, \lvert 0 \rangle), (1/2, \lvert 1 \rangle)\}
$$

where we have the desired probabilistic mixture of the $$\lvert 0 \rangle$$ and $$\lvert 1 \rangle$$ states. In order to be able to do quantum mechanics with these ensembles, we now define the density operator $$\rho_\mathcal{E}$$. For an ensemble $$\mathcal{E}$$, the corresponding density operator that describes the system is defined as:

\begin{equation}
    \displaystyle \rho_{\mathcal{E}} = \sum_{i} p_i \lvert \psi_i \rangle \langle \psi_i \rvert.
\end{equation}

For our example with the Stern-Gerlach pre-measurement state, we have:

$$
\rho_\mathcal{E} = \frac{1}{2}\lvert 0 \rangle \langle 0 \rvert + \frac{1}{2} \lvert 1 \rangle \langle 1 \rvert = \frac{1}{2}\left(\lvert 0 \rangle \langle 0 \rvert + \lvert 1 \rangle \langle 1 \rvert \right) = \frac{I}{2}.
$$

We remark that there is not a unique ensemble associated with a given density operator. For example, $$\mathcal{E}' = \{(1/2, \lvert + \rangle), (1/2, \lvert - \rangle)\}$$ would yield the same $$\rho$$ as above. The action of unitary evolution and measurement on a quantum system generalizes to the density operator picture. In the state ket formalism, unitary evolution was given as:

$$\lvert \psi \rangle \mapsto U \lvert \psi \rangle$$ 

where $$U$$ is some unitary operator. In the density operator formalism this takes the form:

$$
\rho \mapsto U \rho U^\dagger.
$$

In the state ket formalism, the Dirac projection postulate was given as:

$$
\lvert \psi \rangle \mapsto \frac{\Pi_j \lvert \psi \rangle}{\sqrt{\langle \psi \rvert \Pi_j \lvert \psi \rangle}}
$$

where $\Pi_j$ is the projector corresponding to the measurement outcome $$j$$. The corresponding probability of measurement was given by the Born rule as:

$$
p(j) = \langle \psi \rvert \Pi_j \lvert \psi \rangle.
$$

In the density operator formalism, the Dirac projection postulate reads:

$$
\rho \mapsto \frac{\Pi_j \rho \Pi_j^\dagger}{\mathrm{Tr}(\Pi_j \rho)}
$$

with measurement probabilities given by the Born rule as:

$$
p(j) = \mathrm{Tr}(\Pi_j \rho).
$$

In the case where $$\rho = \lvert \psi \rangle \langle \psi \rvert$$ for some $$\lvert \psi \rangle \in \mathcal{H}$$, we say that $$\rho$$ is *pure* (and corresponds to a unique state ket $$\lvert \psi \rangle$$, up to an irrelevant global phase). So it is immediately evident that the density operator formalism is capable of representing all quantum systems that could be represented in the state ket formalism. However, it is also capable of describing a larger class of states (i.e. probabilistic mixtures). It is therefore a broader generalization of the previous formalism. 

However, it is not immediately clear how the Bloch sphere visualization of a two-level system generalizes to the case when the system is described by a density operator rather than a state ket. It turns out that there is an extremely natural generalization of the previously derived geometric description; namely that a density operator for a two-level system can be associated with a point somewhere on the (closed) Bloch *ball*. In other words, density operators correspond to systems not just *on* the 2-sphere (the Bloch sphere/the surface of the unit ball in $$\mathbb{R}^3$$) but to systems located anywhere on the 3-dimensional unit ball. To see how this is the case, we first must prove some properties about density operators. 


### Properties of density operators
We will prove three properties, namely:
1. Density operators are Hermitian, that is $$\rho^\dagger = \rho$$. 
2. Density operators are normalized; that is, they satisfy $$\mathrm{Tr} (\rho) = 1$$.
3. Density operators satisfy $$\mathrm{Tr} (\rho^2) \leq 1$$ in general, with equality if and only if $$\rho$$ is pure. 

**Proof of 1:** Let $$\rho_\mathcal{E} = \sum_{i} p_i \lvert \psi_i \rangle \langle \psi_i \rvert$$. We then have:

$$
\rho_\mathcal{E}^\dagger = \left(\sum_{i} p_i \lvert \psi_i \rangle \langle \psi_i \rvert\right)^\dagger = \sum_i p_i^* (\lvert \psi_i \rangle \langle \psi_i \rvert)^\dagger = \sum_{i} p_i \lvert \psi_i \rangle \langle \psi_i \rvert = \rho_\mathcal{E}
$$

where in the second equality we use the linearity of the adjoint, and in the third equality we use that the $p_i$s correspond to (real) probabilities and hence $$p_i^* = p_i$$. The claim is therefore proven. $$\square$$

**Proof of 2:** Again let  $$\rho_\mathcal{E} = \sum_{i} p_i \lvert \psi_i \rangle \langle \psi_i \rvert$$. We then have:

$$
\mathrm{Tr}(\rho_\mathcal{E}) = \sum_{i} p_i \mathrm{Tr}(\lvert \psi_i \rangle \langle \psi_i \rvert) = \sum_i p_i = 1
$$

where in the first equality we use the linearity of the trace, in the second equality we use that $$\mathrm{Tr}(\lvert \psi \rangle \langle \psi \rvert) = 1$$ (simply take the trace by summing over any ONB containing $$\lvert \psi \rangle$$), and in the final equality we use that the probabilities sum to unity. $$\square$$

**Proof of 3:** Since $\rho$ is Hermitian, it may be diagonalized; that is, there exists an orthonormal basis $$\{ \lvert \phi_j \rangle \}_j$$ such that $$\rho = \sum_j \lambda_j \lvert \phi_j \rangle \langle \phi_j \rvert$$ We then have that:

$$
\rho^2 = \left(\sum_j \lambda_j \lvert \phi_j \rangle \langle \phi_j \rvert\right)\left(\sum_{j'} \lambda_{j'} \lvert \phi_{j'} \rangle \langle \phi_{j'} \rvert\right) = \sum_j \sum_{j'} \lambda_j \lambda_{j'}\lvert \phi_j \rangle\langle \phi_{j'}\lvert \delta{jj'} = \sum_j \lambda_j^2 \lvert \phi_j \rangle \langle \phi_j \rvert
$$

where in the second equality we use the orthonormality of the $$\lvert \phi_j \rangle$$s. We may now take the trace using the $$\{ \lvert \phi_j \rangle \}_j$$ basis, which yields:

$$
\mathrm{Tr}(\rho^2) = \sum_j \lambda_j^2.
$$

However, since $$\mathrm{Tr}(\rho) = \sum_j \lambda_j = 1$$, it follows that each of the $$\lambda_j$$s are less than or equal to $$1$$. Hence $$\lambda_j^2 \leq \lambda_j$$ for each $$j$$, so:

$$
\mathrm{Tr}(\rho^2) = \sum_j \lambda_j^2 \leq \sum_j \lambda_j = 1
$$

which proves the general claim. The above inequality is an equality only if one of the $$\lambda_j$$s is one and the rest zero, i.e. $$\rho = \lvert \phi_j \rangle \langle \phi_j \rvert$$ for some $$\lvert \phi_j \rangle$$, and hence $$\rho$$ is pure. This concludes the only if direction. Conversely, if $$\rho$$ is pure, then $$\rho = \lvert \psi \rangle \langle \psi \rvert$$ for some $$\lvert \psi \rangle \in \mathcal{H}$$, so:

$$
\rho^2 = (\lvert \psi \rangle \langle \psi \rvert)(\lvert \psi \rangle \langle \psi \rvert) = \lvert \psi \rangle \langle \psi \rvert \psi \rangle \langle \psi \rvert = \lvert \psi \rangle \langle \psi \rvert = \rho
$$

Hence $$\mathrm{Tr}(\rho^2) = \mathrm{Tr}(\rho) = 1$$ using the normalization property. This concludes the proof. $$\square$$

### The Bloch ball
We now have all of the necessary tools to prove our claim about associating two-level system density operators $$\rho$$ to points on the Bloch ball. We will show that any density operator $$\rho$$ corresponding to a two-level quantum state can be written as:

$$
\rho = \frac{I + \mathbf{r} \cdot \mathbf{\sigma}}{2}
$$

where $$\mathbf{\sigma} = (\sigma_x, \sigma_y, \sigma_z)^T$$ (where $$\sigma_i$$ are the Pauli operators) and $$\mathbf{r} \in \mathbb{R}^3$$ such that $$\lvert \mathbf{r}\rvert \leq 1$$. This $$\mathbf{r}$$ is the proposed Bloch ball vector visualization of the quantum state!

**Proof.** First, we observe that $$I$$ (the identity), $$\sigma_x, \sigma_y, \sigma_z$$ are linearly independent (on the vector space of 2x2 complex matrices). Therefore, any such element of this vector space (including $$\rho$$) can be written as:

$$
\rho = r_I I + r_x \sigma_x + r_y \sigma_y + r_z \sigma_z
$$

Where $$r_I, r_x, r_y, r_z$$ are complex numbers. Now, since we know that $$\rho$$ is Hermitian, we have:

$$
r_I I + r_x \sigma_x + r_y \sigma_y + r_z \sigma_z = \rho = \rho^\dagger = r_I^* I^\dagger + r_x^* \sigma_x^\dagger + r_y^* \sigma_y^\dagger + r_z^* \sigma_z^\dagger = r_I^* I + r_x^* \sigma_x + r_y^* \sigma_y + arz^* \sigma_z
$$

where in the last equality we use the Hermicity of $$I$$ and each of the Pauli operators. From this we conclude that $$a_i^* = a_i$$ for each $$i$$ and hence each coefficient is real. Next, since we know that $$\rho$$ is normalized, we have that:

$$
1 = \mathrm{Tr}(\rho) = r_I\mathrm{Tr}(I) + r_x\mathrm{Tr}(\sigma_x) + r_y\mathrm{Tr}(\sigma_y) + r_z\mathrm{Tr}(\sigma_z) = 2r_I
$$

where we use that the Pauli operators are traceless. From this we conclude that $$r_I = \frac{1}{2}$$. Finally, we will use the property that $$\mathrm{Tr}(\rho^2) \leq 1$$. First calculating $$\rho^2$$, we find:

$$
\rho^2 = \frac{I + r_x^2\sigma_x^2 + r_y^2\sigma_y^2 + r_z^2\sigma_z^2 + r_xr_y(\sigma_x\sigma_y + \sigma_y\sigma_x) + r_yr_z(\sigma_y\sigma_z + \sigma_z\sigma_y) + r_zr_x(\sigma_z\sigma_x + \sigma_x\sigma_z)}{4}.
$$

Using that $$\sigma_i\sigma_j + \sigma_j\sigma_i = 2\delta_{ij}I$$, the above simplfiies to:

$$
\rho^2 = \frac{(1 + r_x^2 + r_y^2 + r_z^2)I}{4}
$$

So applying the trace condition we have:

$$
\mathrm{Tr}(\rho^2) = \frac{1 + r_x^2 + r_y^2 + r_z^2}{2} \leq 1 \implies r_x^2 + r_y^2 + r_z^2 \leq 1.
$$

Defining $$\mathbf{r} = (r_x, r_y, r_z)^T$$, we can conclude that $$\lvert \mathbf{r} \rvert \leq 1$$ from the above equation, concluding the proof. $$ \square$$

From the above argument, we have found that we can associate a point in the Bloch ball (The closed unit ball in $$\mathbb{R}^3$$) with any density operator for a quantum two-level system (i.e. the generalized qubit). As a final consistency check, it will be instructive to verify whether this result is consistent with the earlier state ket visualization we found earlier. Namely, in the case that $$\rho$$ is a pure state, do we obtain the correct point on the Bloch sphere (the surface of the Bloch ball)?

First, we observe in the last line of the proof above that the equality is saturated if and only if $$\rho$$ is a pure state, and hence if $$\rho$$ is pure than $$\lvert \mathbf{r} \rvert = 1$$. So we find that pure states indeed lie on the Bloch sphere, as before (note that fully mixed states with $$\rho = I/2$$ lie in the center of the Bloch ball, in comparison). Furthermore, take a pure qubit state $$\lvert \psi \rangle = \cos(\theta/2)\lvert 0 \rangle + e^{i\varphi}\sin(\theta/2)\lvert 1 \rangle$$. The density operator corresponding to this state is:

$$
\rho = \lvert \psi \rangle \langle \psi \rvert = \cos^2(\theta/2)\lvert 0 \rangle \langle 0 \rvert + \cos(\theta/2)\sin(\theta/2)e^{-i\varphi}\lvert 0 \rangle \langle 1 \rvert + \cos(\theta/2)\sin(\theta/2)e^{i\varphi}\lvert 1\rangle \langle 0\rvert + \sin^2\left(\theta/2\right)\lvert 1 \rangle \langle 1 \rvert
$$

Additionally, expanding out $$\rho = \frac{I + \mathbf{r} \cdot \mathbf{\sigma}}{2}$$ using computational basis states, we find:

$$
\rho = \frac{1 + r_z}{2}\lvert 0 \rangle \langle 0 \rvert + \frac{r_x - ir_y}{2}\lvert 0 \rangle \langle 1 \rvert + \frac{r_x + ir_y}{2}\lvert 1 \rangle \langle 0 \rvert + \frac{1 - r_z}{2}\lvert 1 \rangle \langle 1 \rvert
$$

Solving for $$r_x, r_y, r_z$$$ by equating the two expressions for $$\rho$$ (using Euler's formula and $$\sin(2\theta) = 2\cos(\theta)\sin(\theta)$$), we find:

$$
r_x = \cos(\varphi)\sin(\theta), \quad r_y = \sin(\varphi)\sin(\theta), \quad r_z = 2\cos^2\left(\theta/2\right) - 1 = \cos(\theta)
$$

which are the correct expressions for the Cartesian coordinates of points on a unit sphere (in $$\mathbb{R}^3$$) expressed in terms of spherical coordinates. This shows that the state ket visualization and the density operator visualizations are consistent with each other.

### References
- Michael A. Nielsen and Isaac L. Chuang. *Quantum Computation and Quantum Information.* Cambridge University Press, 2000.
    - Much of this post was motivated by Problem 2.72 in the text.