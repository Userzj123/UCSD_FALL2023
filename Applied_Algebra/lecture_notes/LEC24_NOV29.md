# Lec 24 Nov 29

For $A\in M_{m,n}(\C)$ with $m\ge n$, then SVD can look like

$$
A = Q\begin{bmatrix} S_1\\0\end{bmatrix} V^H
$$

where $Q, V$ unitary and $S_1\in M_n(\R)$ with non-negative decreasing diagonal elements.

Let $Q = \begin{bmatrix}Q_1 & Q_2\end{bmatrix}$ where $Q \in M_{m,n}(\C)$, then

$$
A = \begin{bmatrix} Q_1 & Q_2\end{bmatrix}
$$

then

$$
\begin{align}
A &= \begin{bmatrix} Q_1 & Q_2\end{bmatrix}\begin{bmatrix} S_1\\0\end{bmatrix}V^H\\
& = Q_1 S_{11}V^H\\
& = \underbrace{Q_1 V^H}_{U}\underbrace{VS_{11}V^H}_{H}
\end{align}
$$

Note $H$ is Hermitian and it is positive semi-definite. Also $U^HU = VQ_1^HQ_1 V^H = I_n$, so $U$ has orthonormal columns. $A = UH$ with $U\in M_{m,n}(\C)$ orthonormal columns, $H \in M_n(\C)$ positive semi-definite, is the **polar decomposition** of $A$.

If $A = UH$ polar decomposition, then 

$$
A^HA = HU^HUH = H^2\\
H = (A^HA)^{\frac{1}{2}} = |A|
$$

So 

$$
A = U|A|
$$

if $n = m=1$  then

$$
z = e^{\ii \theta} |z|.
$$

Note if $A\in M_n(\C)$ non-singular, then $U$ unqiue.


Analogy: $n = m = 1, z \neq0$ so that exist unique $\theta$ solution.

Also, for $m\le n$, get related decomposition

$$
A = KU
$$

in which $K$ is the module $|A|$ and $U\in M_{m,n}(\C)$ is the orthonormal basis.



## Norms
Finite dimension vector space $V (\C^n)$ over scalar field $\R $ or $\C$.

*definition*
1. A **quasi-seminorm** is a function $\nu: V\to \R$ satisfying $\nu(x+y)=\nu(x)+\nu(y), \nu(\alpha x) = \alpha \nu(x)$, for all $x, y \in V, \alpha\ge 0, \alpha \in \R$.
2. A **seminorm** is a function $\nu: V\to \R$ satisfying $\nu(x+y)\le \nu(x)+\nu(y), \nu(\alpha x) = |\alpha| \nu(x)$, for all $x, y \in V, \alpha \in \C$.
   Note: 
   
   $$

   $$


[Missing]

<!-- ??Hanbana -->

*example*
Over $\C^n$, we commonly use 

$$
\begin{align}
    \nu(x) = \|x\|_2 &= \sqrt{x^Hx}\\
    \|x\|_1 & = \sum_{i=1}^n |x_i|\\
    \|x\|_p & = \left(\sum_{i=1}^n |x_i|^p\right)^\frac{1}{p}, \quad p\in \mathbb{N}\setminus\{0\}\\
    \|x\|_\infty & = 
\end{align}
$$

[Missing]

*proposition* Let $V$ finite dimension vector space with basis $B$ and norm $\|\cdot\|_2$

[Missing]

