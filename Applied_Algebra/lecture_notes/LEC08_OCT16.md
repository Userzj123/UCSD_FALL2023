# Lec08

*sidenote*
If $T\in $ inner product space $\mathcal{L}(X, X)$, then

$$
\langle T(x), y \rangle = \langle x, T^*(y)\rangle,
$$

in which $T^*\in \mathcal{L}(X, X)$ is the adjoint of $T$.

Let $X \in \C^n$, $T$ matrix is the same as multiplied by $A$,

$$
\langle Ax, y \rangle = \langle x, A^H y\rangle,
$$

in which $A^H$ is the hermitian adjoint of $A$. Furthermore, eigenvectors of $A$ satisfy $Ax = \lambda x$ is **right eigenvector** of $A$. Eigenvectors of $A^H$ satisfy $A^Hx=\lambda x$ is the **left eigenvector** of $A$.

*Pf or determinant properties*:

- $P_A(\alpha) = (\lambda_1 - \alpha)(\lambda_2 - \alpha) \dots (\lambda_n - \alpha) = \det(A-\lambda I)$
- $\displaystyle\det(A) = P_A(0) = \prod_{\lambda \in \sigma(A)}\lambda$


Also from complex analysis, if $A \in M_n(\R)$ then $P_A(\alpha)=0$ has real coefficients. Then the nonreal eigenvalues come in complex conjugate pairs.

Given $\lambda$ eigenvalue, its eigenvectors all belong to null space of $(A-\lambda I)$

*definition*
We define **geometric multiplicity**,

$$
\gm(\lambda) = \dim(\null(A-\lambda I)),
$$

which refers to the number of linear independent eigenvectors there are for $\lambda$.

*note*: corresponding left and right eigenvalues will have same geometric multiplicity.

*example* 
$A = \begin{bmatrix}
    1 & 1\\ 0 & 1
\end{bmatrix} $ has $\am(1) = 2, \gm(1) = 1$.

*proposition*
$\gm(\lambda) \le \am(\lambda)$ for $\lambda$ an eigenvalue of $A\in M_n(\C)$.

*proof*
let $r = \gm(\lambda)$, then $\exists$ basis $x_1, \dots, x_r$ of $\null(A-\lambda I)$. Let $X_1 = \begin{bmatrix} x_1, \dots, x_r \end{bmatrix}\in M_{n, r}(\C)$.  Extend this basis to all of $\C^n$: $\exists X_2\in M_{n, n-r}(\C)$, s.t. $X = [X_1, X_2]$ has linear independent columns.

Note $AX_1 = \lambda X_1I_r$, so 

$$
AX = \begin{bmatrix} AX_1 & AX_2\end{bmatrix} =\begin{bmatrix} \lambda X_1I_r & AX_2 \end{bmatrix} = \begin{bmatrix} X_1 & X_2 \end{bmatrix}\begin{bmatrix} \lambda I_r & B_{12}\\ 0 & B_{22} \end{bmatrix}
$$

so 

$$
X^{-1}AX = \begin{bmatrix} \lambda I_r & B_{12}\\ 0 & B_{22}\end{bmatrix}.
$$

$\am(\lambda)\ge r$ for $X^{-1}AX$ but $\sigma(A) = \sigma(X^{-1}AX)$, so $\am(\lambda) \ge r$ for $A$.

**Rank Multiplicity Theorem**
$\rank(A-\lambda I) \ge n - \am(\lambda)$ for an eigenvalue $\lambda$ of $A\in M_n(\C)$.


We call $\lambda \in \sigma(A)$ a **defective eigenvalue** if $\am(\lambda)\gt \gm(\lambda)$. Otherwise, **nondefective**.


We call $A\in M_n (\C)$ **defective** if it has at least one defective eigenvalue. Otherwise, **nondefective**.

*example*

- defective $\begin{bmatrix} 1 & 1\\ 0 & 1\end{bmatrix}$ 
- nondefective $\begin{bmatrix} 1 & 0\\ 0 & 1\end{bmatrix}$

*proposition*
Let $A\in M_n(\C)$ and suppose $\series{x}{n}$ are eigenvectors correspond to $\series{\lambda}{n}$, all distinct. Then, $\series{x}{n}$ are linear independent.

*proof*
Induction on k
- Initial induction step: k=1

    Only one eigenvector $x_1$ is nonzero and linear independent.

- Main induction step: True for $k=r-1$, show $k=r$ is true.

    *Contradiction*: $\series{x}{n}$ correspond to distinct $\series{\lambda}{n}$ are linear dependent.

    $\exists \series{\alpha}{r}$ not all zero s.t. $\sum_{i=1}^r \alpha_r x_r=0$ but none of $\series{\alpha}{n}$ are zero. so $\displaystyle x_r = \sum_{j=1}^{r-1} \beta_j x_j$ where $\beta_j\neq 0$ for all $1\le j\le r-1$. But 
    
    $$
    \begin{aligned}
        Ax_r & = \sum_{j=1}^{r-1}\beta_j Ax_j\\
        \lambda_r x_r & = \sum_{j=1}^{r-1} \beta_j \lambda_j x_j\\
        \lambda_r \sum_{j=1}^{r-1}\beta_j x_j & = \sum_{j=1}^{r-1} \beta_j \lambda_j x_j\\
        \sum_{j=1}^{r-1}\beta_j (\lambda_r - \lambda_j)x_j &= 0,
    \end{aligned}
    $$

    Induction hypothesis says $\beta_j(\lambda_r - \lambda_j) = 0$ for all $1\le j \le r-1$. In this case, $\lambda_r = \lambda_j$, which contradicts the assumption of distinct eigenvalues.

---
*Note*
1. If $A$ has distinct eigenvalues $\series{\lambda}{n}$ then corresponding eigenvectors $\series{x}{n}$ are linear independent and unique up to scalar multiplication.
2. $\series{\lambda}{n}$ distinct and corresponding eigenvectors are linear independent ( might have more than one corresponding eigenvectors for one eigenvalue).
3. Number of linear independent eigenvectors of $A$ refers to $\displaystyle \sum_{\lambda \in\sigma(A)}\gm(\lambda)$.
4. A non-defective matrix have n linear independent eigenvectors. 

    In this case, $X = \begin{bmatrix} x1 & x_2 & \dots & x_n\end{bmatrix}$ invertible. Then, $AX = \begin{bmatrix} \lambda_1 x_1 & \lambda_2x_2 & \dots & \lambda_nx_n \end{bmatrix} = X\Lambda$, so $X^{-1}AX =\Lambda$ diagonal.