---
layout: post
title: Three ways of finding Fibonacci
date: 2000-01-01
description: Finding the Fibonacci numbers through force, through linear algebra, and through generating functions.
categories: math
hidden: true
---
**Date.** *The Fibonacci numbers arise frequently (and often unexpectedly) in mathematics and in biological systems. In this post, we discuss three ways of calculating them: through brute force, through linear algebra, and finally through the use of generating functions.*

The Fibonacci numbers are a sequence of integers defined recursively by $$F_0 = 0, F_1 = 1$$, and 

\begin{equation}\label{eq:fibonacci}
F_n = F_{n-1} + F_{n-2}
\end{equation}

for $$n > 1$$. If one has a computer on hand and is aware of recursive functions, this immediately invites a brute force solution.

### Method 1: Brute Force Computation

The following function below 

{% highlight python linenos %}
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)
{% endhighlight %}

Some comment about this being $$O(2^n)$$, python's recursion limit of 1000 (should use a functional language for this).

### Method 2: Linear Algebra and Diagonalization
Write the recursion relation as a matrix equation:

$$\begin{bmatrix} f_{i} \\ f_{i-1} \end{bmatrix} = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} f_{i-1} \\ f_{i-2} \end{bmatrix}$$


### Method 3: Generating Functions
We define 