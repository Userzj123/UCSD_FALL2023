$_{B_2}[T]_{B_2} = S^{-1} {_{B_1}}[T]_{B_1}S$

THe same linear transormation can have many different matrix represnetation but if $A$ is one(matrix representation), then the others are $S^{-1}AS$, for some $S\in M_n(\F)$ invertible.

$_{B_2}[T]_{B_2}$ is similar to $S^{-1} {_{B_1}}[T]_{B_1}S$.

*Similarity* is an equivalence relation,
- reflexity: $A \sim A$
- symmetry: $A\sim B \rightarrow B\sim A$
- transitivity: $A\sim B, B\sim C \rightarrow A\sim C$


Thus, $A\in M_n(\F)$ lives in an *equivalent class*

$$
\{B\in M_n(\F)| B~A\} = \{S^{-1}AS|S\in M_n(\F) \text{ invertible}\}
$$

*Which representation is "best"?*
Perhaps "best" means
- $S^{-1}AS$ easy to get information from
- S has nice properties

Ex. if possible, would like $S^{-1}AS = D$ diagonal matrix.
Given $AS=SD$, if $S=[S_1\dots S_2]$, then we have $AS_j = \lambda_j S_j \forall 1\le j\le n$. Note $S_j\neq 0$.

Thus, this motivates us to find the eigenvalue and eigenvectors of matrix $A$ to obtain the diagonal equivalent matrix.

## Eigenvalues and Eigenvectors
$A\in M_n(\F)$ for $F = \R$ or $\C$. We call $(\lambda, x)$, for $\lambda \in \F, x\neq 0, x\in \F^n$ in *eigenpairs* of $A$ if $Ax=\lambda x$.

In this, $\lambda$ is called the *eigenvalue* and $x$ is called the *eigenvectors*.

Thus, $\lambda $ is an eigenvalue iff $\null(A-\lambda I) \neq \{0\}$ ($ \Rightarrow$ iff $A=\lambda I$ singular).
$x\in \null(A-\lambda I)\setminus \{0\}$ is an eigenvector.

Note: $T(x)= \lambda x \Longleftrightarrow _B[T]_B[x]_B = \lambda [x]_B$ for any basis $B$ of $X$.

$[T(x)]_B = _B[T]_B [x]_B$
$[\lambda x]_B = \lambda [x]_B$

So eigenvalues are the same under change of basis.

*proposition*
$A\in M_n(\C)$ has at lease one eigenpair.

*proof*
Fix $x\in \C^n, x\neq 0$, then $\{x, Ax, A^2x, \dots, A^nx\}$ is linear dependent. That means, there are $\alpha_0, \dots, \alpha_n$ not all zero s.t. $\sum_{j=0}^n \alpha_j A^jx = 0$. Form $B = \sum_{j=0}^n \alpha_j A^j$. Fundamental theorem of algebra says that <span style='color:red'>$B = \beta (A-\lambda_k I)\dots(A-\lambda_1I)$</span>. Then, we know $Bx=0$.

*definition*
$A\in M_n(\F)$
- A right eigenvecotr of $A$ corresponding to a right eigenvalue $\lambda$ is a nonzero $x$ s.t. $Ax=\lambda x$
- A left eigenvecotr of $A$ corresponding to a left eigenvalue $\lambda$ is a nonzero $y$ s.t. $y^HA =\lambda y^H$

*Equivalencies*:
- $y^HA = \lmabda y^H \Longleftrightarrow A^Hy = \lambda ^H y = \bar{\lambda}y$, then $(\lambda^H, y)$ beging an eigenpair of $A^H \Longleftrightarrow y$ being left eigenvector of $A$ corresponding to $\lambda$
- there exists $x\neq 0$ s.t. $(A-\lambda I)x = 0 \Longleftrightarrow $ there exists $x\neq 0$ s.t. $x\in \null(A-\lambda I) \Longleftrightarrow \det(A-\lambda I)=0$. Similarily, there exists $y\neq 0$ s.t. $(A^H-\lambda^H I)y=0$ $\Longleftrightarrow $ there exists $y\neq0$ s.t. $y\in \null(A^H - \lamda^HI) \Longleftrightarrow \det(A^H-\lambda^HI)=0$. But $0=\det(A-\lambda I) \Longleftrightarrow 0 = $


*definition*

*definition*
The characteristic polynomial of $A$ is 

$$
P_A(\alpha) = \det(A-\alpha I),
$$

eigenvalues are roots of this polynomial.