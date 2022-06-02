---
layout: post
title: Four ways to Fibonacci
date: 2022-06-02
description: Finding the Fibonacci numbers through algorithms, linear algebra, and generating functions.
categories: math
hidden: false
---
**June 6, 2022.** *The Fibonacci numbers arise frequently (and often unexpectedly) in mathematics and in biological systems. In this post, we discuss four ways of calculating them: through brute force, through brute force (but in a more clever fashion), through linear algebra, and finally through the use of generating functions.*

The Fibonacci numbers are a sequence of integers defined recursively by $$f_0 = 0, f_1 = 1$$, and 

\begin{equation}\label{eq:fibonacci}
f_n = f_{n-1} + f_{n-2}
\end{equation}

for $$n > 1$$. If one has a computer on hand, this immediately invites a brute force recursive solution.

### Method 1: Brute force computation

Translating the definition of the Fibonacci numbers in Eq. \eqref{eq:fibonacci} directly into code (in this case, Python), we end up with:

{% highlight python linenos %}
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)
{% endhighlight %}

This solution is conceptually pretty as it makes evident use of the recursive structure of the numbers, but in practice performs very poorly. For one, Python has a recursion limit of 1000 by default and we should probably use a functional programming language (such as Haskell) instead which is better suited for handling recursion. However even beyond this technical limitation, as the input $$n$$ grows large the above method slows down considerably. Let us calculate how many operations are required to calculate the $$n$$th fibonacci number with the above algorithm. Let us make the ansatz that the the number of addition operations $$A(n)$$ required to produce the $$n$$th fibonacci number is $$A(n) = x^n$$ (for some $$x > 1$$). By the defining recursive formula of Eq. \eqref{eq:fibonacci}, we have (for $$n > 1$$) that:

$$
    A(n) = A(n - 1) + A(n - 2) + 1
$$

and so with our ansatz this becomes:

$$
    x^n = x^{n-1} + x^{n-2} + 1.
$$

Dividing out by $$x^{n-2}$$ and rearranging, we find:

$$
    x^2 - x - 1 - x^{2 - n} = 0.
$$

Since we are interested in the asymptotic (large $$n$$) number of additions required to calculate $$f_n$$, we have in this limit that $$x^{2 - n} \to 0$$ and hence:

$$
    x^2 - x - 1 \approx 0.
$$

Applying the quadratic formula to solve for $$x$$, we find:

$$
    x \approx \frac{1 \pm \sqrt{5}}{2}
$$

and taking the positive solution, we find that $$x$$ is precisely the golden ratio:

$$
\varphi = \frac{1 + \sqrt{5}}{2}
$$

and so we conclude:

$$
A(n) \approx \varphi^n = \left(\frac{1 + \sqrt{5}}{2}\right)^n.
$$

We will see very shortly that the golden ratio will come up when we solve for a closed-form expression for $$f_n$$. Before we try to find this, let us see if we can improve the above brute force algorithm (as the exponential time complexity we find above is quite terrible in practice). The inefficiency comes from the fact that we do a lot of redundant computations between the two branches of the recursive calls to `fibonacci(n)`. If we had some way to "remember" the computations we have already done, we could avoid this redundancy. To this end, we introduce memoization, where we store the results of past calls to the function and return them when they are again requested (instead of computing them all over again). 

### Method 2: Brute force computation (with memoization)

Our improved algorithm takes the form:

{% highlight python linenos %}
fib_dict = {}
fib_dict[0] = 0
fib_dict[1] = 1
def fibonacci_mem(n):
    if n not in fib_dict:
        fib_dict[n] = fibonacci_mem(n-1) + fibonacci_mem(n-2)
    return fib_dict[n]   
{% endhighlight %}

where we have defined a dictionary `fib_dict` that stores computed fibonacci numbers so we don't have to compute them all over again. Since checking if a key is in a dictionary and dictionary lookup are both $$O(1)$$ on average, this memoized algorithm is actually linear in time complexity, instead of exponential. 

Let us verify this claim that $$T(n) = O(n)$$ where $$T(n)$$ is the time complexity of calculating the $$n$$th Fibonacci number with the above improved algorithm. First, we have that $$T(0) = T(1) = O(1)$$. For $$n > 1$$, the time complexity $$T(n)$$ is equal (from Eq. \eqref{eq:fibonacci}) to the time complexity of calculating $$f_{n-1}$$ plus the time complexity of calculating $$f_{n-2}$$ plus an $$O(1)$$ addition operation of adding them together. Computing $$f_{n-1}$$ will be a $$T(n-1)$$ operation, but since the computation of $$f_{n-2}$$ will already be done (and recorded) in the computation of $$f_{n-1}$$, this will just be an $$O(1)$$ dictionary lookup. Hence:

$$
    T(n) = T(n - 1) + O(1) + O(1) = T(n - 1) + O(1)
$$

Now recursively applying this formula $$n-1$$ times, we find:

$$
T(n) = T(n - (n-1)) + (n-1)O(1) = T(1) + (n-1)O(1) = O(1) + (n-1)O(1) = O(n)
$$

which proves the claim. Memoization is in general improvement for problems with recursive structure. Having explored the problem fairly thoroughly algorithmically, let us see if we can find insights through mathematical derivation.

### Method 3: Linear algebra and diagonalization
In this next approach, we will use some techniques from linear algebra to obtain a closed form expression for the Fibonacci numbers. To start, we make the observation that we can write the recursion relation of Eq. \eqref{eq:fibonacci} as a matrix equation:

$$
\begin{bmatrix} f_{n} \\ f_{n-1} \end{bmatrix} = A\begin{bmatrix} f_{n-1} \\ f_{n-2} \end{bmatrix}
$$

where:

$$
A = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix}.
$$

By recursive application of this formula, we can write the LHS in terms of $$f_1 = 1$$ and $$f_0 = 0$$:

$$
\begin{bmatrix} f_{n} \\ f_{n-1} \end{bmatrix} = A^{n-1}\begin{bmatrix} f_{1} \\ f_{0} \end{bmatrix} =A^{n-1} \begin{bmatrix} 1 \\ 0 \end{bmatrix}.
$$

If we can obtain a closed form expression for $$A^{n-1}$$, we can easily evaluate the left hand side of the above equation to find $$f_n$$. To do this, we diagonalize $$A$$. Solving for the eigenvalues of $$A$$, we have:

$$
\det(A - \lambda I) = \det \begin{bmatrix} 1 - \lambda & 1 \\ 1 & -\lambda \end{bmatrix} = (1-\lambda)(-\lambda) - 1 = \lambda^2 - \lambda - 1.
$$

Applying the quadratic formula, we find that $$\lambda_1 = \frac{1 + \sqrt{5}}{2}$$, $$\lambda_2 = \frac{1 - \sqrt{5}}{2}$$. Note that the golden ratio again emerges here, and we may write $$\lambda_1 = \varphi$$, $$\lambda_2 = 1 - \varphi$$. Solving for the corresponding eigenvectors, we have:

$$
(A - \lambda_1 I)\mathbf{v}_1 = \mathbf{0} \implies \begin{bmatrix} 1 - \varphi & 1 \\ 1 & -\varphi\end{bmatrix}\mathbf{v}_1 = \mathbf{0} \implies \mathbf{v}_1 = \begin{bmatrix} \varphi \\ 1 \end{bmatrix}
$$

$$
(A - \lambda_2 I)\mathbf{v}_2 = \mathbf{0} \implies \begin{bmatrix} \varphi & 1 \\ 1 & \varphi - 1 \end{bmatrix}\mathbf{v}_2 = \mathbf{0} \implies \mathbf{v}_2 = \begin{bmatrix} 1 - \varphi \\ 1 \end{bmatrix}
$$

If we then let:

$$
D = \begin{bmatrix} \lambda_1 & 0 \\ 0 & \lambda_2 \end{bmatrix} = \begin{bmatrix} \varphi & 0 \\ 0 & 1-\varphi \end{bmatrix}
$$

$$
V = \begin{bmatrix} \mathbf{v}_1 & \mathbf{v}_2 \end{bmatrix} = \begin{bmatrix} \varphi & 1-\varphi \\ 1 & 1 \end{bmatrix}
$$

we can diagonalize $$A$$ as:

$$
A = VDV^{-1}
$$

where $$V^{-1}$$ is obtained by inverting $$V$$:

$$
V^{-1} = \frac{1}{\varphi \cdot 1 - (1 - \varphi) \cdot 1}\begin{bmatrix} 1 & -(1-\varphi) \\ -1 & \varphi\end{bmatrix} = \frac{1}{2\varphi - 1}\begin{bmatrix}1 & -(1-\varphi) \\ -1 & \varphi\end{bmatrix}.
$$

Powers of $$A$$ can be easily obtained in this form:

$$
A^{n-1} = (VDV^{-1})(VDV^{-1})\ldots(VDV^{-1}) = VD^{n-1}V^{-1}
$$

where

$$
D^{n-1} = \begin{bmatrix} \lambda_1^{n-1} & 0 \\ 0 & \lambda_2^{n-1} \end{bmatrix} = \begin{bmatrix} (\varphi)^{n-1} & 0 \\ 0 & (1-\varphi)^{n-1} \end{bmatrix}.
$$

Therefore by matrix-vector multiplication we have:

$$
\begin{bmatrix} f_{n} \\ f_{n-1} \end{bmatrix} = VD^{n-1}V^{-1}\begin{bmatrix} 1 \\ 0 \end{bmatrix} = \frac{1}{2\varphi - 1}\begin{bmatrix}\varphi^n - (1-\varphi)^n \\ \varphi^{n-1} - (1-\varphi)^{n-1} \end{bmatrix}
$$

from which we conclude the closed form solution of $$f_n$$ to be:

$$
f_n = \frac{\varphi^n - (1-\varphi)^n}{2\varphi - 1}.
$$

In the limit of large $$n$$, since $$1 - \varphi < 0$$ we have $$(1 - \varphi)^n \to 0$$. In this limit we therefore have:

$$
f_n \approx \frac{\varphi^n}{2\varphi - 1}.
$$

A notable observation is that the *value* of $$f_n$$ has the same asymptotic growth as the time complexity/number of operations required to calculate it per the brute force algorithmic approach!


### Method 4: Generating functions
For a final approach, we introduce the notion of a generating function, where an infinite sequence of numbers is encoded in the coefficients of a power series. A common application of generating functions is in probability theory, where moment generating functions of a random variable $$X$$, defined as:

$$
M_X(s) = \mathbf{E}(e^{sX})
$$

(with $$\mathbf{E}$$ denoting expectation) encodes the moments of the distribution of $$X$$, with:

$$
\mathbf{E}(X^k) = \left. \frac{\mathrm{d}}{\mathrm{d}s} M_X(s) \right|_{s = 0}.
$$

Another application is in statistical mechanics, where the derivatives of the logarithm of a system's partition function encodes the mean energy (and other related quantities) of the system. Surprisingly, this tool comes in useful for combinatorics problems, such as solving for the Fibonacci numbers! To this end, we define a power series $$F(x)$$ such that the coefficients are the Fibonacci numbers:

$$
F(x) = \sum_{n=0}^\infty f_n x^n.
$$

We can then apply the recursion relation Eq. \eqref{eq:fibonacci} termwise to obtain the expression:

$$
\sum_{n=0}^\infty f_n x^n = \sum_{n=0}^\infty f_{n-1}x^n + \sum_{n=0}^\infty f_{n-2}x^{n} + x
$$

where we let $$f_{-2} = f_{-1} = 0$$, and the extra $$x$$ on the right hand side is present to enforce $$f_1 = 1$$. Factoring some powers of $$x$$, we find:

$$
\sum_{n=0}^\infty f_n x^n = x\sum_{n=0}^\infty f_{n-1}x^{n-1} + x^2\sum_{n=0}^\infty f_{n-2}x^{n-2} + x
$$

and re-indexing the series on the left hand side and applying the definition of the Fibonacci generating function, we find:

$$
F(x) = xF(x) + x^2F(x) + x.
$$

We may then isolate $$F(x)$$ to obtain:

$$
F(x) = \frac{x}{1 - x - x^2} = \frac{-x}{x^2 + x - 1}
$$

$$x^2 + x - 1$$ has the two roots $$x = \frac{-1 \pm \sqrt{5}}{2}$$, or in terms of the golden ratio, $$x = \varphi - 1$$ and $$x = -\varphi$$. We may then write:

$$
F(x) = \frac{-x}{(x - (\varphi - 1))(x + \varphi)}.
$$

By partial fraction decomposition, we have:

$$
F(x) = \frac{-\frac{\varphi - 1}{2\varphi - 1}}{x - (\varphi - 1)} + \frac{-\frac{\varphi}{2\varphi - 1}}{x + \varphi} = \frac{-1}{2\varphi - 1}\left(\frac{1}{\frac{x}{\varphi - 1} - 1} + \frac{1}{\frac{x}{\varphi} + 1}\right).
$$

Using the identity $$\varphi - 1 = \frac{1}{\varphi}$$, we may rewrite this as:

$$
F(x) = \frac{-1}{2\varphi - 1}\left(\frac{1}{\varphi x - 1} + \frac{1}{(\varphi - 1)x + 1}\right) = \frac{1}{2\varphi - 1}\left(\frac{1}{1 - \varphi x} - \frac{1}{1 - (1 - \varphi)x}\right).
$$

Now using the geometric series formula for both terms:

$$
F(x) = \frac{1}{2\varphi - 1}\left(\sum_{n=0}^\infty (\varphi x)^n - \sum_{n=0}^\infty ((1-\varphi)x)^n \right) = \sum_{n=0}^\infty \frac{\varphi^n - (1-\varphi)^n}{2\varphi - 1} x^n.
$$

Since the coefficients of $$F(x)$$ are the Fibonacci numbers by definition, we conclude that:

$$
f_n = \frac{\varphi^n - (1-\varphi)^n}{2\varphi - 1}
$$

which we can see agrees with our previous result from the linear algebra approach.

### Acknowledgements
Thank you to Yaniv Plan/Richard Anstee for presenting the clever diagonalization approach in MATH 223 (Honours Linear Algebra), and to 3Blue1Brown for his [fantastic video](https://www.youtube.com/watch?v=bOXCLR3Wric) on using generating functions to solve problems in combinatorics.