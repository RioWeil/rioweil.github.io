---
layout: post
title: Three ways of finding Fibonacci
date: 2000-01-01
description: Finding the Fibonacci numbers through force, through linear algebra, and through generating functions.
categories: math
hidden: true
---
**Date.** *The Fibonacci numbers arise frequently (and often unexpectedly) in mathematics and in biological systems. In this post, we discuss three ways of calculating them: through brute force, through linear algebra, and finally through the use of generating functions.*

The Fibonacci numbers are a sequence of integers defined recursively by $$f_1 = f_2 = 1$$, and 

\begin{equation}\label{eq:fibonacci}
f_n = f_{n-1} + f_{n-2}
\end{equation}

for $$n > 1$$. If one has a computer on hand and is aware of recursive functions, this immediately invites a brute force solution.

### Method 1: Brute Force Computation

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

This solution is conceptually pretty as it makes evident use of the recursive structure of the numbers, but in practice performs very poorly. For one, Python has a recursion limit of 1000 by default and we should probably use a functional programming language (such as Haskell) instead which is better suited for handling recursion. However even beyond this technical limitation, as the input $$n$$ grows large the above method slows down considerably. 


THIS PART PROBLEMATIC

Let us analyze the time complexity of the above algorithm. The algorithm is $$O(1)$$ for $$n = 0$$ and $$n = 1$$, and for $$n > 1$$ the time complexity $$T(n)$$ is given by:

$$
T(n) = T(n-1) + T(n - 2) + O(1)
$$

As to compute $$f_n$$ we compute $$f_{n-1}, f_{n-2}$$ and then add them together (an $$O(1)$$ operation). We claim that $$T(n) = O(2^n)$$. The base cases are clear with $$T(0) = O(1) = O(2^0)$$ and $$T(1) = O(1) = O(2^1)$$. For $$n > 1$$, with the induction hypothesis we have that:

$$
T(n) = O(2^{n-1}) + O(2^{n-2}) + O(1) = O(2^n)
$$

which proves the claim. 






However we are able to prove a more specific bound here; letting $$A(n)$$ be the number of addition operations required to produce the $$n$$th Fibonacci number, we find that $$A(0) = A(1) = 1$$, and for $$n > 1$$ that:

$$
A(n) = A(n - 1) + A(n-2).
$$

Making the ansatz that $$A(n) = a^n$$ for some positive base $$a$$, we find:

$$
a^n = a^{n-1} + a^{n-2}.
$$

And dividing out by $$a^{n-2}$$ and rearranging we obtain:

$$
a^2 - a - 1 = 0
$$

Applying the quadratic formula, we find that:

$$
a = \frac{1 \pm \sqrt{5}}{2}
$$

and taking the positive solution, we find that $$a$$ is precisely the golden ratio $$\phi$$, and so:

$$
A(n) = \phi^n = \left(\frac{1 + \sqrt{5}}{2}\right)^n.
$$

We will see very shortly that the golden ratio will come up when we solve for a closed-form expression for $$f_n$$. Before we try to find this, let us see if we can improve the above brute force algorithm (as an exponential time complexity is quite terrible in practice). The inefficiency comes from the fact that we do a lot of redundant computations between the two branches of the recursive calls to `fibonacci(n)`. If we had some way to "remember" the computations we have already done, we could avoid this redundancy. To this end, we introduce memoization, where we store the results of past calls to the function and return them when they are again requested (instead of computing them all over again). Our improved algorithm takes the form:

{% highlight python linenos %}
fib_dict = {}
fib_dict[0] = 0
fib_dict[1] = 1
def fibonacci_mem(n):
    if n not in fib_dict:
        fib_dict[n] = fibonacci_mem(n-1) + fibonacci_mem(n-2)
    return fib_dict[n]   
{% endhighlight %}

where we have defined a dictionary `fib_dict` that stores computed fibonacci numbers so we don't have to compute them all over again. Since checking if a key is in a dictionary and dictionary lookup are both $$O(1)$$ on average, this memoized algorithm is linear in time complexity, instead of exponential. 

THIS PART PROBLEMATIC


Let us verify this claim that $$T(n) = O(n)$$. We have that $$T(0) = T(1) = O(1)$$ as before, and for $$n > 1$$, computing $$f_{n-1}$$ is $$T(n - 1)$$ as before as well. However, the computation of $$f_{n-2}$$ has already been done in computing $$f_{n-1}$$, and so is just an $$O(1)$$ dictionary lookup. Hence:
$$
T(n) = T(n - 1) + O(1) + O(1) = T(n - 1) + O(1)
$$

For the base case, we have $$T(1) = O(1) = O(n)$$ (glossing over the possibly problematic $$O(0)$$). By the inductive hypothesis, we then have that:

$$
T(n) = O(n - 1) + O(1) = O(n)
$$

which proves the claim. Memoization is in general improvement for problems with recursive structure. Having explored the problem fairly thoroughly algorithmically, let us see if we can find insights through mathematical derivation.

### Method 2: Linear Algebra and Diagonalization
Write the recursion relation as a matrix equation:

$$\begin{bmatrix} f_{i} \\ f_{i-1} \end{bmatrix} = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} f_{i-1} \\ f_{i-2} \end{bmatrix}$$



### Method 3: Generating Functions
We define a power series $$F(x)$$ such that the coefficients are the Fibonacci numbers:

$$F(x) = \sum_{i=1}^\infty f_n x^n$$

Then the recursion relation 


### Acknowledgements
Yaniv Plan/Richard Anstee for Linalg approach, 3B1B for the generating function approach.