---
layout: post
title: Generalizing the qubit
date: 2000-01-01
description: A geometric visualization of density operators for two-state systems.
categories: physics quantum
hidden: true
---
**Date.** *The density operator is discussed in quantum mechanics courses as a generalization of the state ket, allowing one to represent probabilistic mixtures. In this post, we provide a geometric visualization of this generalization, by showing how the qubit state ket on the Bloch sphere extends to the Bloch ball in the density operator formalism.*

### The Qubit and the Bloch sphere
The qubit, or quantum bit is the simplest example of an interesting quantum system. Given computational basis states $$\lvert 0 \rangle$$ and $$\lvert 1 \rangle$$, a general qubit state is an arbitrary superposition of the basis states:

$$
\lvert \psi \rangle = \alpha \lvert 0 \rangle + \beta \lvert 1 \rangle.
$$

A helpful visualization of the qubit comes in the form of the Bloch sphere. To see this form, we make two observations. First, the qubit state $$\lvert \psi \rangle$$ must be normalized, enforcing:

$$
\lvert \alpha \rvert^2 + \lvert \beta \rvert^2 = 1
$$

with the above condition, we can without loss of generality let $$\lvert \alpha \rvert = \cos(\theta/2)$$, $$\lvert \beta \rvert = \sin(\theta/2)$$ for some $$0 \leq \theta \leq \pi$$. The second observation is that the global phase of a quantum state is irrelevant; since any quantum experiment can only measure probabilities $$p(j) = \lvert \langle j \vert \psi \rangle \rvert^2$$, we can see that $$\lvert \psi \rangle$$ and $$e^{i\phi}\lvert \psi \rangle$$ physically represent the same state as they yield the same probabilities:

$$p'(j) = \lvert \langle j \rvert e^{i\phi} \lvert \psi \rangle \rvert^2 = \langle j \rvert e^{i\phi} \lvert \psi \rangle \langle \psi \rvert e^{-i\phi} \lvert j \rangle = e^{i\phi}e^{-i\phi}\langle j \rvert \psi \rangle \langle \psi\lvert j \rangle = \langle j \rvert \psi \rangle \langle \psi\lvert j \rangle = \lvert \langle j \lvert \psi \rangle \rvert^2 = p(j)$$ 

Since the global pha





### Introducing the density operator
A first undergraduate course focuses on the position space wavefunction $$\psi(\mathbf{r})$$ in position space as governed by 

A good example is 

### Properties of the density operator


### The Bloch ball
