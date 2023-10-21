# LEC09
Non-defective matrix $A\in M_n(\C)$  has $n$ linear independent eigenvectors and is diagonalizable.

Suppose $A$ diagonalizable, $\exists X \in M_n(\C)$ invertible s.t. $X^{-1}AX = \Lambda$, so columns of $X$ are eigenvectors since $Ax_j = \lambda_j x_j$ and columns are linearly independent.

Since $\gm(\lambda)\le \am(\lambda)$, $\sum_{\lambda \in \sigma(A)} \am(\lambda) = n$ and $\sum_{\lambda \in \sigma(A)} \gm(\lambda) = n$ (there are $n$ linearly independent eigenvectors), then 

$$
\Rightarrow \gm(\lambda) = \am (\lambda) \text{ for all }\lambda \in \sigma(A)\\
\Rightarrow A \text{ nondefetive}
$$

Altogether, we have TFAE
- $A$ nondefective
- $A$ has $n$ linearly independent eigenvectors
- $A$ is diagonalizable.

(defective matrix cannot be diagonalized)??

If $A$ diagonalizable then 

$$
X^{-1}AX = \Lambda,
$$

in which rows of $X^{-1}$ are Hermitian transpose of left eigenvector and columns of $X$ are the eigenvectors,

$$
\begin{aligned}
    X^{-1}X &= I\\
    \begin{bmatrix} y^H_1\\y^H_2\\\vdots\\y^H_n \end{bmatrix}
    \begin{bmatrix} x_1 & x_2 & \dots & x_n \end{bmatrix} & = I\\
    \begin{bmatrix}
        y^H_1x_1 & y^H_1x_2 & \dots &  y^H_1x_n\\
        \vdots & \vdots &  & \vdots\\
        y^H_nx_1 & y^H_nx_2 & \dots & y^H_n x_n 
    \end{bmatrix}&= I,
\end{aligned}
$$

so $y^H_ix_j = 0, \;\if i\neq j$. Thus, left and right eigenvectors satisfy bi-orthogonal relationship.

Furthermore, if $A$ diagonalizable, then

$$
\begin{aligned}
    A = X\Lambda X^{-1} & = \sum_{i=1}^n \lambda_i x_i y^H_i,
\end{aligned}
$$
 
which is a sum of **principle components**.


Usage of diagonal matrix:
*example* power method basis
$A$, suppose eigenvalues $|\lambda_1|\ge |\lambda_2| \ge \dots |\lambda_n|$ and corresponding eigenvectors. Assuming $A$ diagonalizable, pick $x=\sum_{i=1}^n \alpha_i x_i$, then 

$$
\begin{aligned}
A^kx & = \sum_{i=1}^n \alpha_i A^k x_i\\
& = \sum_{i=1}^n \alpha_i \lambda_i^k x_i\\
& \approx \alpha_i \lambda_i^k x_i, \text{ as } k\rightarrow \infty
\end{aligned}
$$

Consider other $X^{-1}A X = B$, we want:
- B still nice
- A general
- X nice

We called $A\in M_n(\C)$ a **block upper triangular** matrix iff 

$$
A = \begin{bmatrix}
    A_{11} & A_{12} & \dots & A_{1k}\\
    & A_{22} & \dots & A_{2k}\\
    & & \ddots & \vdots\\
    0& & & A_{kk}
\end{bmatrix},
$$

where $A_{ii}\in M_{n_i}(\C)$ and $n_1 + n_2 + \dots + n_k = n$.

$n_i=1$ for all $1\le i\le k \Rightarrow$ A is **upper triangular** matrix. Same for **block lower triangular** and **lower triangular**.

If A is either block upper or lower matrix, then we call $A$ **block triangular** and similarly for **triangular**.

If $A$ block triangular, then

$$
\sigma(A) = \sigma(A_{11})\cup\sigma(A_{22})\cup\dots \cup \sigma(A_{kk}),
$$

since 

$$
\det(A-\lambda I) = \det(A_{11}-\lambda I)\dots \det(A_{kk}-\lambda I)\\
P_A(\alpha) = P_{A_{11}}(\alpha)\dots P_{A_{kk}}(\alpha)
$$


We define $A, B \in M_n(\C)$ to be **unitarily equivalence** if $B = U^HAU$, where $U$ is a **unitary matrix**, meaning $U^{-1} = U^H$ or $U$ has orthonormal columns.

**Principle of deflation**
Let $A\in M_n(\C)$, and $\sigma(A) = \{\series{\lambda}{n}\}$, as multiset. Then $\exists$ unitary $Q$ s.t.

$$
Q^{-1}AQ = \begin{bmatrix}
    \lambda_1 & b^H\\ 0 & \hat{A}
\end{bmatrix}
$$


*proof*
Let $x_1$ be an eigenvector of $\lambda_1$ satisfying $x_1^Hx_1 = 1$. Now extend to orthonormal basis, $\begin{bmatrix} x_1 & U \end{bmatrix} = Q$. Note:
- $U^Hx_1 = 0$
- $U^HU = I$

Then 

$$
\begin{aligned}
Q^HAQ &= \begin{bmatrix}x_1^H\\ U^H\end{bmatrix} A  \begin{bmatrix}x_1 & U^H\end{bmatrix} \\
& = \begin{bmatrix}
    x_1^HAx_1 & x_1^HAU\\
    U^HAx_1 & U^HAU
\end{bmatrix}\\
& = \begin{bmatrix}
    \lambda_1 & x_1^HAU\\ 0 & U^HAU
\end{bmatrix}
\end{aligned}
$$

Repeated use of deflation leads to

$$
Q^HAQ = \begin{bmatrix}
    \lambda_1 & \dots & & \alpha_{ij} \\
    & \lambda_2 & \dots & \\
    & & \ddots & \vdots\\
    & & & \lambda_n
\end{bmatrix}
$$