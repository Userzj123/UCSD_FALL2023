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
   Note: $\nu(x)\ge 0, \, \forall x$ because,
   
   $$
    \begin{align}
    2 \nu &= \nu(x) + \nu(x)\\
    & = \nu(x) + \nu(-x)\\
    & = \nu(x-x)\\
    & = \nu(0)\\
    & = \nu(0 \cdot x)\\
    & = 0
    \end{align}
   $$

3. A norm is a function $\nu:V\rightarrow \R$ satisfying 
   $$
   \nu(x+y) \le \nu(x)+\nu(y)\\
   \nu(\alpha x) = |\alpha|\nu(x)\\
   \nu(x) = 0 \Longleftrightarrow x = 0
   $$

*example*
Over $\C^n$, we commonly use 

$$
\begin{align}
    \nu(x) = \|x\|_2 &= \sqrt{x^Hx}\\
    \|x\|_1 & = \sum_{i=1}^n |x_i|\\
    \|x\|_p & = \left(\sum_{i=1}^n |x_i|^p\right)^\frac{1}{p}, \quad p\in \mathbb{N}\setminus\{0\}\\
    \|x\|_\infty & = \max_{1\le i\le n} |x_i|
\end{align}
$$

for finite dimension vector space $V$, fix basis $B$, we can get

$$
\|x\|_p = \|[x]_B\|_p,\\
\|x\|_\infty = \|[x]_B\|_\infty.
$$

For inner product space $V$, we can get $\|x\| = \sqrt{\langle x, x\rangle}$ and have Cauchy-Schmwarz $|\langle x, y\rangle| \le \|x\|\|y\|$. For orthonormal basis $B$,

$$
|\langle x, y \rangle| = [y]_B^H [x]_B \le \|x\|_2\|y\|_2.
$$

---
Can use norms to measure distances. 

A **metric** $\rho: V\times V \rightarrow \R$ satisfies $\forall x, y, z\in V$, 

$$
\rho(x, y) \ge 0\\
\rho(x, y) = 0 \Longleftrightarrow x=y,\\
\rho(x, y) = \rho(y, x),\\
\rho(x, z) \le \rho(x, y) + \rho(y, z)
$$


For norm $\|\cdot\|$ over $V$, then $\rho(x, y) = \|x-y\|$ is a metric.


*proposition* Let $V$ finite dimension vector space with basis $B$ and norm $\|\cdot\|_2$. Then any norm $\|\cdot\| : V\rightarrow \R$ is a continuous function with respect to the metric arising from $\|\cdot\|_2$. 

$\forall x \in V$, given $\epsilon \gt 0$, $\exist \delta \gt 0 \st \|x-y\|_2 \lt \delta \Rightarrow |\|x\|-\|y\|| \lt \epsilon, \, \forall y\in V$.

*proof*


$$
\begin{align}
    \|x\| &= \|x - y + y\| \le \| x-y\| + \|y\|\\
    \begin{cases}
    \|x\|-\|y\| \le \|x - y\|\\
    \|y\|-\|x\| \le \|y - x\|
    \end{cases} & \Rightarrow|\|x\|-\|y\|| \le \|x-y\|
\end{align}
$$

Now let $\alpha = [x-y]_B$, then

$$
\begin{align}
    |\|x\| -\|y\|| &\le \|x-y\|\\
    & = \left\| \sum_{i=1}^n \alpha_i \underbrace{x_i}_{\text{basis}}\right\|\\
    & \le \sum_{i=1}^n |\alpha_i| \|x_i\|\\
     & \le \|\alpha\|_2 \|\beta\|_2\\
     & = \|\beta\|_2 \|x-y\|_2
\end{align}
$$

where $\beta = \begin{bmatrix}\|x_1\| \\ \vdots \\ \|x_n\|\end{bmatrix} $.

Given $\epsilon \gt 0, \exists \delta = \frac{\epsilon}{2\|\beta\|_2} \st$, 

$$
\|x-y\|_2 \lt \underbrace{\frac{\epsilon}{2\|\beta\|_2}}_{\delta} \Rightarrow |\|x\|-\|y\|| \le \frac{\epsilon}{2}\lt \epsilon
$$



*proposition*
Let $V$ finite dimension vector space with basis $B$ and norm $\|\cdot \|_2$. Then any norm $\|\cdot\|$ has real numbers $c_1, c_2 \gt 0 \st$

$$
c_1\|x\|_2 \le \|x\| \le c_2 \|x\|_2,
$$

for all $x\in V$.