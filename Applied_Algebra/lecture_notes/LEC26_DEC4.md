# Lec 26 Dec 4
Given nonsingular matrix $A\in M_n(\C)$, and vector norm $\|\cdot\|$, then we can define another vector norm

$$
\|x\|_{\|\cdot\|, A} = \|Ax\|
$$

which is called the vector norm induced by $A$.

Note if $A$ is singular, then $\|x\|_{\|\cdot\|, A}$ is still a seminorm.


*example*

$$
\|x\|_{\|\cdot\|_2, A} = \|Ax\|_2 = \sqrt{x^HA^HAx}
$$


If $A\in M_n(\C)$ is positive definite,  then we can define

$$
\|x\|_A = \sqrt{x^HAx},
$$

which is called the **elliptic norm**.

In fact, $\|x\|_A = \sqrt{x^HAx} = \sqrt{x^HA^{\frac{1}{2}}A^{\frac{1}{2}}x} = \|x\|_{\|\cdot\|_2, A^{\frac{1}{2}}}$. 


Elliptic norm is an example of a norm that is not absolute.

---
(Above is the content for final.)

**Matrix Powers**

Study $A^k$ for large $k$, e.g., $e^A$ or convergence of iterative methods



There is a close relation between matrix norms and the spectrum radius $\displaystyle\rho(A) = \max_{\lambda\in \sigma(A)} |\lambda|$.

*Notation*
we call $\mu \in \sigma(A)$ is **dominant eigenvalue** of $A$ if $|\mu| = \rho(A)$.

*proposition*

Let $A \in M_n(\C)$ and let $\|\cdot\|$ be a consistent matrix norm, then

$$
\rho(A)\le \|A\|.
$$

*proof*
Find a vector $\nu$ that is compatible with $\|\cdot \|$,

$$
\nu(Ax) \le \|A\| \nu(x).
$$

For $(\lambda, x)$ eigenpair, we get

$$
\nu(Ax) = \nu(\lambda x) = |\lambda|\nu(x).
$$

so 

$$
\|A\| \ge \rho(A) = \max_{\lambda\in \sigma(A)} |\lambda|.
$$

Is there a norm that satisfies the equality:

$$
\rho(A) = \|A\|.
$$

No because spectrum radius is not a norm since $\rho(J_n(0)) = 0, \, \forall n\gt 1$.

For fixed matrix $A\in M_n(\C)$, we can get closed to equality.


*proposition*
Let $A\in M_n(\C)$ and real number $\epsilon \gt 0$, then exists consistent matrix norm $\|\cdot\|_{A, \epsilon} \st$

$$
\|A\|_{A, \epsilon} \le \rho(A) + \epsilon.
$$

Also if the dominant eigenvalues of $A$ are non-defective, then exists consistent matrix norm $\|\cdot\|_A \st$

$$
\|A\|_A = \rho(A).
$$

*proof*
We study matrix norm of the form

$$
\|B\| = \|C^{-1} BC \|_\infty \text{ for chosen } C\in M_n(\C) \text{ non-singular}.
$$

Take Schur decomposition of $A$,

$$
Q^HAQ = \Lambda + N.
$$


Now consider, for $\eta \gt 0$,

$$
D = 1 \oplus \eta \oplus \dots \oplus \eta^{n-1} \in M_n(\C).\\
D^{-1} = 1 \oplus \eta^{-1} \oplus \dots \oplus \eta^{1-n} \in M_n(\C).
$$


Study 

$$
D^{-1} \Lambda D =  \Lambda.
$$

$D^{-1}ND$ is still strictly upper triangular, possible nonzero entries $i\lt j$, $i$ row $j$ column.

$$
(D^{-1}ND)_{ij} = \eta^{-(i-1)} N_{ij} \eta^{j-1} = \eta^{j-i}N_{ij} \rightarrow 0 \text{ as } \eta \rightarrow 0.
$$


This means $\|D^{-1}ND\|_\infty \le \epsilon$ for some chosen $\eta\gt 0$.



With this choice of $\eta$,

$$
\begin{align}
    \|D^{-1}Q^HA\underbrace{QD}_{C}\| & = \|D^{-1}(\Lambda + N)D\|_\infty\\
    & \le \|\Lambda \|_\infty + \|D^{-1}ND\|_\infty\\
    & \le \rho(A) + \epsilon.
\end{align}
$$

If the dominant eigenvalues of $A$ are nondefective, then Jordan canonical form says

$$
E^{-1}AE = \Lambda_1 \oplus (\Lambda_2 + N_2)
$$

in which $\Lambda_1\in M_m(\C)$ is diagonal with all dominant eigenvalues since it is non-defective and $N_2$ is strictly upper triangular.


Define 

$$
\Delta = I_m\oplus D.
$$

Then

$$
\begin{align}
    \|\Delta ^{-1} E^{-1} A \underbrace{E\Delta}_{C}\|_\infty & = \|\Lambda_1 \oplus D^{-1}(\Lambda_2 + N_2)D\|_\infty\\
    & = \max\{\rho(A), \|D^{-1}(\Lambda_2 + N_2)D\|_\infty\}
\end{align}
$$

But 

$$
\|D^{-1}(\Lambda_2 + N_2)D\|_\infty \rightarrow \|\Lambda_2\| \text{ as }\eta \to 0.
$$

choose $\eta \st$

$$
\|\Delta ^{-1} E^{-1} A \underbrace{E\Delta}_{C}\|_\infty = \rho(A).
$$

We will find a norm s.t.,

$$
\|A^k\| \le (\rho(A) + \epsilon)^k.
$$

Thus, when $\rho(A) \lt 1$, this goes to 0 as $k\rightarrow \infty$.