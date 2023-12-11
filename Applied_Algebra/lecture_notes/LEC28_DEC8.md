# Lec 28 Dec 8

*proposition*
The dual norm of the $\infty$-norm is the $1$-norm.

$$
|y^Hx| \le \|x\|_\infty\|y\|_1.
$$


*proof*

$$
\begin{align}
    |y^Hx| & = |\sum_{i=1}^n \overline{y_i} x_i|\\
    & \le \sum_{i=1}^n |\overline{y_i}x_i| \\
    & = \sum_{i=1}^n |y_i||x_i| \\
    & \le \|x\|_\infty\|y\|_1.
\end{align}
$$

For $y\in \R^n$, let $x_i = \pm 1$ and $x_i y_i \ge 0$. Then,

$$
|y^Hx | = \sum_{i=1}^n |y_i| = \|y\|_1.
$$


*proposition*
Dual norm of $1$-norm is the $\infty$-norm.

*proof*
Fixed $x$, find $\|y\|_1 = 1 \st |y^Hx| = \|x\|_\infty$. 

If $\|x\|_\infty = |x_k|$, the equality is satisfied with $y = e_k$.

Note:
1. Dual of $\|\cdot\|_A$ is $\|\cdot\|_{A^{-1}}$ for $A$ is positive definite.
2. Dual of $\|\cdot\|_p$ is $\|\cdot\|_q$ for $\frac{1}{p}+\frac{1}{q} = 1$.




We can also define a **linear functional** $f$ on a subspace $V \subseteq \C^n$ of dim $m$ as linear transformation, $f:V\to \C^n$.

We can find $y\in \C^n$ s.t.,

$$
f(x) = y^Hx, \, \forall x\in V.
$$

Since, let $B_1'$ be a basis of $V$, $B_1$ basis of $\C^n$ extends $B_1^\prime$. $B_2$ extended over basis of $\C^n$. Then, for $x\in V$,

$$
\begin{align}
    & \because [x]_{B_1}  = \underbrace{P}_{\begin{bmatrix}I_m & 0\end{bmatrix}}[x]_{B_1} = P{_{B_1}}[I_n]_{B_2} [x]_{B_2}\\
    & \therefore f(x)  = [f(x)]_{\{1\}}  = {_{\{1\}}} [f]_{B_1^\prime} [x]_{B_1^\prime} = {_{\{1\}}}[f]_{B_1^\prime} P{_{B_1}}[I_n]_{B_2} [x]_{B_2} = y^Hx
\end{align}
$$

We can extend linear functional $f:V\to \C$ to $F:\C^n \to \C$, where $F(x)=f(x), \forall x\in V$ by using $F(x) = y^Hx, \, \forall x\in \C^n$. But there are other extensions as well: any extension $F$ will satisfy $F(x) = (y+z)^Hx$, where $z\in V^\perp$. But we can pick the best extension, which is non-increase in the norm of extension.



### Hahn-Banach Theorem

Let $\|\cdot\|$ be a seminorm of $\C^n$, subspace $V\subseteq \C^n$, $f:V\to \C$ linear functional satisfying $f(x)\le \|x\|, \forall x \in V$.

Then exists a linear functional $F:\C^n\to \C$ s.t.,

1. $F(x) = f(x), \, \forall x\in V$
2. $|F(x)| \le \|x\|, \forall x \in \C^n$

Note if $\exists \mu\in \R$, s.t., $|f(x)|\le \mu \|x\|, \forall x \in V$. Then can get extension $F:\C^n \to \C$ satisfying $|F(x)|\le \mu \|x\|, \forall x\in \C^n$. (**bounded linear functional**)


*sketch of proof*
1. Prove for quasi-seminorm with $\F = \R$.
2. Prove for quasi-seminorms with $\F = \C$ with $|\RE f| \le \|x\|$ and $|\RE F| \le \|x\|$.
3. Prove for seminorm and $\F=\C$.


*proposition*
For norm $\nu(\cdot)$ of $\C^n$ we have that $\nu^{**}(x) = \nu(x), \, \forall x \in \C^n$.

*proof*

For $x = 0 \Rightarrow $ Done.

For $x\neq 0 \Rightarrow$ Given $y \in \C^n$, 

$$
\begin{align}
    \because |y^Hx| &\le \nu^*(y)\nu(x)\\
    \therefore \nu^{**}(x) & = \max_{\nu^*(y)=1} |x^Hy| \le \max_{\nu^*(y)=1} \nu^*(y)\nu(x) = \nu(x)
\end{align}
$$


Fix $x\neq 0 \Rightarrow$ define linear functional $f:\span{x} \to \C, \alpha x \to \alpha \nu(x)$. Then, 

$$
|f(\alpha x)| = |\alpha \nu(x)| = ||\alpha|\nu (x)| = |\nu(\alpha x)| = \nu(\alpha x).
$$

And so $\exists$ linear functional $F:\C^n \to \C \st$, 

$$
F(\alpha x) = f(\alpha x), \forall \alpha \in \C,\\
|F(w)|\le \nu(w), \forall w\in \C^n.
$$

Now exists $z\in \C^n \st$

$$
F(w) = z^Hw, \forall w\in \C^n.
$$


So

$$
\nu^*(z) = \max_{w\neq 0} \frac{|z^Hw|}{\nu(w)} = \max_{w\neq 0} \frac{|F(w)|}{\nu(w)} = 1.
$$

Also

$$
z^Hx = F(x) = f(x) = \nu(x)
$$

so

$$
\nu(x) = z^Hx = |z^Hx|.
$$

so

$$
\nu^{**}(x) = \max_{y\neq 0} \frac{|y^Hx|}{\nu(y)} \ge \frac{z^Hx}{\nu^*(z)} = \nu(x).
$$



so $\nu^{**}(x) = \nu(x), \forall x \in \C^n$.

## Summarize

1. Vector spaces, linear transformation -> matrices
2. Basis, diagonalization, defective, unitarily diagonalization (normal), Schur Decomposition, 
3. Block upper triangular, block diagonal, invariant subspace, Jordan canonical form, 
4. eigenvalues, of Hermitian matrices, Crank-fisher
5. Non-square matrices, Singular Value Decomposition, polar decomposition, Crank-fisher for singular value
6. Norms of vectors and matrices, equivalence of norm, classic matrix norms, (Matrix power, spectral radius, dual norm)