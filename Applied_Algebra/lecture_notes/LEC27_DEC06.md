# Lec 27 Dec 06

Given $A\in M_n(\C), \epsilon \gt 0, \exists$ consistent norm $\|\cdot \| \st$,

$$
\rho(A) \le \|A\|\le \rho(A) + \epsilon.
$$

*corollary*
Given $A\in M_n(\C), \epsilon \gt 0, \exists$ consistent norm $\st,$


$$
\rho(A)^k \le \|A\|^k \le (\rho(A) + \epsilon)^k,
$$

because,

$$
\rho(A)^k \le \rho(A^k) \le \|A^k\| \le \|A\|^k \le (\rho(A)+\epsilon)^k.
$$

$A \in M_n(\C)$, if $(A)_{ij} \rightarrow 0$ as $k \rightarrow \infty$, $\forall i \le i, j\le n$, then we say $A$ is **convergent**.


Note $A$ is convergent $\displaystyle\Longleftrightarrow \lim_{k\rightarrow \infty} \|A^k\|_\infty =  0 \Longleftrightarrow \lim_{k\to \infty} \|A^k\| = 0$ for any matrix norm $\|\cdot\|$. 


Thus,

*corollary*

A matrix is convergent $\Longleftrightarrow$ its spectral radius is strictly less than $1$.


### Linear Functional
Back to vector norm, remember Cauchy-Schwarz inequality,

$$
|y^Hx| \le \|x\|_2 \|y\|_2, \, \forall x, y \in \C^n.
$$


> What about for other norms? Could we get similar equations?


A **linear functional** on $\C^n$ is a linear transformation $f:\C^n\to \C$. The set of the linear functionals $\mathcal{L}(\C^n, \C)$ is called the **dual space** of $\C^n$.

### Riesz Representation
THe set of all linear functionals is a vector space and for each lienar functional $f$, $\exists$ unqiue $y\in \C^n \st$ 

$$
f(x) = y^Hx, \, \forall x\in \C^n.
$$

*proof*

Consider the standard orthonormal basis $B = \{\series{e}{n}\}$. Set $y^H = {_{\langle 1\rangle}}[f]_B \in M_{1, n}(\C)$ for $y\in \C^n$, then

$$
\begin{align}
    f(x) & = [f(x)]_{\langle 1\rangle}\\
    & = {_{\langle 1\rangle}}[f]_B [x]_B\\
    & = y^Hx
\end{align}
$$

and uniqueness of representation says $y$ is unique.


The **magnitude** of a linear functional is defined, for given norm $\nu:\C^n \to \R$, to be 

$$
\begin{align}
\nu^*(f) &= \max_{\substack{\nu(x) = 1\\ x\in \C^n}} |f(x)|,\\
& = \max_{\substack{x\neq 0\\ x\in \C^n}} \frac{|f(x)|}{\nu(x)}.
\end{align}
$$

Equivalently, we may define,

$$
\begin{align}
\nu^*(y) &= \max_{\substack{\nu(x) = 1\\ x\in \C^n}} |y^Hx|,\\
& = \max_{\substack{x\neq 0\\ x\in \C^n}} \frac{|y^Hx|}{\nu(x)}.
\end{align}
$$

where $f(x) = y^Hx$.

In fact, $\nu^*$ is a vector norm of $\C^n$, we call it the **dual norm** of $\nu$.

Note:

$$
\nu^*(y)\ge \frac{|y^Hx|}{\nu(x)}, \, \forall x\in \C^n
$$

which means

$$
|y^Hx| \le \nu(x)\nu^*(y),
$$

which is the **generalized Cauchy-Schwarz inqueality**.

Also, if the max in dual norm is achieved at $x=x^*$ with $\nu(x^*)=1$, then

$$
\nu^*(y) = \frac{|y^Hx^*|}{\nu(x^*)}\\
|y^Hx^*| = \nu(x^*)\nu^*(y)
$$

We call $x^*$ a vector **dual** to y with respect to $\nu$.

Note: Dual vector is not unique!

Consider $e^{\ii \theta} x^*$ for some $\theta \in [0, 2\pi) \st$

$$
\nu(e^{\ii \theta} x^*) = 1\\
|y^He^{\ii \theta} x^*| = |y^Hx^*| = \nu(x^*)\nu^*(y)= \nu(e^{\ii \theta} x^*)\nu^*(y)
$$

so $e^{\ii \theta} x^*$ is also dual to $y$.


---

Equivalent definition of dual norm,
1. $|y^Hx|\le \nu(x)\nu^*(y), \, \forall x, y\in \C^n$.
2. Given $y\in \C^n, \exists x^*$ with $\nu(x^*) = 1, \st |y^Hx^*| = \nu(x^*)\nu^*(y)$.

---

Would like to say dual of $\nu^*$ is $\nu$ but there are some difficulties. The statement is true: $\nu^{**} = \nu$ but the prof is complicated and uses Hahn-Benach Theorem.

*proposition*
The dual norm of the 2-norm is the 2-norm, which means that 2-norm is **self-dual**.

*proof*
Cauchy-Schwarz gives,

$$
|y^Hx| \le \|x\|_2\|y\|_2, \, \forall x, y\in \C^n.
$$

For fixed $y\in \C^n$, consider $x = \alpha y$ for $\alpha \in \C$ with $\|x\|_2=1$,

so 

$$
\begin{align}
    |y^H\alpha y| & = |\alpha||y^Hy|,\\
    & = |\alpha| \|y\|_2^2,\\
    & = \|\alpha y\|_2 \|y\|_2.
\end{align}
$$

$x^*=\alpha y$, for $\|x\|_2 = 1 \Longleftrightarrow \alpha = \frac{1}{\|y\|_2}$, is dual to $y\in \C^n\setminus \{0\}$.

*proposition*
The dual norm of the $infty$-norm is the $1$-norm.

$$
|y^Hx| \le \|x\|_\infty\|y\|_1.
$$