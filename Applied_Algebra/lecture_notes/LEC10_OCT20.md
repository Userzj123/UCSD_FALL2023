# Lec10
## Schur Decomposition
```{prf:definition} **Schur Decomposition**
If $A \in M _n(\C)$, $\series{\lambda}{n}$ are chosen as eigenvalues of $A$, then $\exists$ unitary $Q\in M_n(\C)$ s.t. $Q^HAQ = T$ for $T$ as a upper triangular matrix and $t_{ii} = \lambda_i$, for all $1\le i\le n$.

The columns of $Q$ are called **Schur vectors**.
```


Consider $A\in M_n(\C)$, vector space (dimension is $n^2$). Take $I, A, A^2, \dots, A^{n^2}$, $n^2+1$ elements in total, which are linearly dependent. So $\exists \series{\alpha}{n^2}$ not all zero s.t. the matrix polynomial equal to zero, $\sum_{j=1}^{n^2} \alpha_j A^j =0$.


What about smaller degree polynomials?
````{prf:definition} **Cauchy-Hamilton Theorem**
Let $A \in M_n(\C)$ with $\sigma(A) = \{\series{\lambda}{n}\}$ and consider the  characteristic polynomial $P_A(\alpha) = \det(A-\alpha I)$. Then, 

$$
P_A(A) = 0.
$$

```{prf:proof}
Let $Q^HAQ = T$ be the Schur decomposition of $A$ where $t_{ii} = \lambda_i$ for all $1\le i \le n$. Then $A = QTQ^H$ and 

$$
\begin{aligned}
    P_A(A) &= (\lambda_1 I - QTQ^H)\dots (\lambda_n I - QTQ^H)\\
    & = Q(\lambda_1 I - T) Q^H\dots Q(\lambda_n I - T)Q^H\\
    & = Q\underbrace{(\lambda_1 I - T) \dots (\lambda_n I - T)}_{P_A(T)}Q^H,
\end{aligned}
$$

Given any $x\in \C^n$, show $P_A(A) x = 0$ to prove that $P_A(A) = 0$. Define $x_0 = Q^H x, x_{i+1} = (\lambda_{n-i}I - T)x_i$, then we have

$$
\begin{aligned}
    x_1 = (\lambda_n I -T) x_0 = \begin{bmatrix} \vdots \\ 0 \end{bmatrix},\\
    x_2 = (\lambda_{n-1} I -T) x_1 = \begin{bmatrix} \vdots \\ 0\\0 \end{bmatrix},\\
    x_n = \begin{bmatrix} 0 \\ \vdots \\0 \end{bmatrix},
\end{aligned}
$$


so $P_A(A)x = Qx_n = 0$.

*Consequence*

$$
P_A(A) = \beta_0 I + \beta_1 A + \dots + \underbrace{\beta_n}_{(-1)^n}A^n = 0,
$$

so they are linearly dependent and $A^n$ can be written as a linear combination of $I, A, \dots, A^{n-1}$, 

$$
\begin{aligned}
    (-1)^n A^n + \beta_{n-1} A^{n-1} + \dots + \beta_0 I &= 0\\
    A((-1)^n A^{n-1} + \beta_{n-1} A^{n-2} + \dots + \beta_1) & = -\beta_0 I\\
    A^{-1} & = \frac{((-1)^n A^{n-1} + \beta_{n-1} A^{n-2} + \dots + \beta_1)}{-\beta_0}
\end{aligned}
$$
```
````

### Summary

- If A nondefective then $\exists X$ invertible s.t. $X^{-1}AX = \Lambda$.
- For any $A$, $\exists$ unitary $Q$ s.t. $Q^HAQ = T$, in which $T$ is a upper triangular matrix.


### 2.4.4 Sylvester's theorem on linear matrix equations
```{prf:definition} Invariant
For $A \in M_n(\C)$ and a subspae $S\subseteq \C^n$, we call $S$ **invariant** iff 

$$
x\in S \Rightarrow Ax \in S.
$$
```

```{prf:example}
Eigenspaces of eigenvalues $\lambda: \null(A-\lambda I)$ are invariant under $A$, since if $x\in \null(A-\lambda I), Ax = \lambda x \in \null(A-\lambda I)$. In fact, the span of any set of linearly independent eigenvectors is also an invariant subspace.

Given $x_1,\dots, x_k$ a basis for subspace $S$, then

$$
S\text{ invariant } \Longleftrightarrow Ax_j \in S, 1\le j\le k.
$$
```


Let $X = [\series{x}{k}]\in M_{n, k}(\C)$, so we can write

$$
AX = XB
$$

so $\range(X)$ invariant $\Longleftrightarrow \exists B$ s.t. $AX=XB$.

*Interpretation*
$X$ invertible and $n\times n$, 

$$
AX = XB \Longleftrightarrow X^{-1}AX = B
$$

Also relations to ${_{B_1}}[T]_{B_1 = \{\series{x}{k}\}}$.

In fact, $y = [X, \hat{X}]$ invertible ($X$ has linearly independent columns), then 

$$
\begin{aligned}
    AY &= A[X, \hat{X}]\\
    & = Y \begin{bmatrix}
        B & Y_{12} \\ 0 & Y_{22}
    \end{bmatrix}\\
    Y^{-1}AY &= \begin{bmatrix} B & Y_{12} \\ 0 & Y_{22} \end{bmatrix},
\end{aligned}
$$

right hand side of which is a block upper triangular matrix, so that $\sigma(A) = \sigma(B) \cup \sigma(Y_{22})$ as multi-sets.