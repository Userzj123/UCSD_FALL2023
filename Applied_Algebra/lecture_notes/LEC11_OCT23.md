# LEC 11
## Invariant subspace


If **invariant subspace** $S\subseteq \C^n$ has basis $X = \begin{bmatrix} x_1 & \dots & x_k \end{bmatrix} \in M_{n, k}(\C)$, then $AX=XB$. Note $S = \range(X)$. According to LEC10, $\sigma(B)\le \sigma(A)$. Then, for each eigenvalue $\lambda \in \sigma(B)$, there exists $v\in \range(X)$ that is an eigenvector of $A$ corresponding to $\lambda$.

*proof*
If $\lambda$ is eigenvalue of $B$, then there exists an eigenvector $w$ of $B$ corresponding to $\lambda$. Then we could have

$$
\begin{aligned}
    Bw &= \lambda w\\
    XBw & = \lambda Xw\\
    AXw & = \lambda Xw\\
    Av & = \lambda v, \text{ in which } v = Xw \in \range(X)
\end{aligned}
$$

Thus, $(\lambda, v)$ is an eigen-pair of A.


Suppose $\series{y}{k}$ as another basis of S, 

$$
Y = \begin{bmatrix} y_1 & \dots & y_k \end{bmatrix} \in M_{n, k}(\C)
$$

then, $\underbrace{X = YC}_{\C^{n, k} = \C^{n, k} * \C^{k, k}}$, in which $C$ is invertible. so 

$$
AX = XB \Longleftrightarrow AYC = YCB \Longleftrightarrow AY = YCBC^{-1},
$$

in which $CBC^{-1}$ is similar to $B$ so $\sigma(B) = \sigma(CBC^{-1})$. Thus, eigenvalues of $A$ over $S$ is well-defined.

*Summary*
$\range(X)$, where $X$ has linearly independent columns, is **invariant** i.f.f. $\exists B$ s.t. 

$$
AX = XB, \;\& \; \sigma(B) \subseteq \sigma(A).
$$

*proposition*
Let $\{\series{\lambda}{k}\}\subseteq \sigma(A)$ as multisets, then $\exists$ an invariant subspace such that $A$ over it has eigenvalues $\series{\lambda}{k}$.


*proof*
According to Schur Decomposition, we have

$$
Q^HAQ = T,
$$

where $t_{ii} = \lambda_i$ for $1\le i \le k$. Now partition $Q = \begin{bmatrix}Q_1 & Q_2\end{bmatrix}$, then 

$$
\begin{aligned}
    AQ & = QT\\
    A \begin{bmatrix}Q_1 & Q_2\end{bmatrix} & = \begin{bmatrix}Q_1 & Q_2\end{bmatrix}  T
\end{aligned}
$$

so $AQ_1 = Q_1 T_{11}$. Thus, $\range(Q_1)$ invariant and eigenvalues of $A$ over $\range(Q_1)$ are $\sigma(A_{11}) = \{\series{\lambda}{k}\}$.


One consequence of this is:

*proposition*
Given $A\in M_n(\C)$, and multiset $w = \{\series{\lambda}{t}\}$ satisfying $w\subseteq \sigma(A)$ and $w \cap (\sigma(A)\setminus w) = \phi$. Then exists a unique invariant subspace over which $A$ has eigenvalues of $w$.



*proof*
suppose basis $\series{x}{k}$ for invariant subspace and if $X = \begin{bmatrix} x_1 & \dots x_k \end{bmatrix}$, then $AX = XB$ and $\sigma(B) \subseteq \sigma(A)$.

Consider two invariant subspaces $\range(X), \range(Y)$, where $X, Y$ have linearly independent columns. Note $\range(X)\cap\range(Y)$ is also an invariant subspace.

So take a basis as columns of $\hat{Z}$ of $\range(X)\cap\range(Y)$. And extend basis to columns of $\begin{bmatrix} \hat{X} & \hat{Z} \end{bmatrix}$ a basis of $\range(X)$. Extend basis $\hat{Z}$ to columns of $\begin{bmatrix} \hat{Z} & \hat{Y} \end{bmatrix}$ whose columns are a basis of $\range(Y)$. Then, look at linearly independent columns $\begin{bmatrix}\hat{X} & \hat{Z} & \hat{Y} \end{bmatrix}$, we have

$$
A\begin{bmatrix}\hat{X} & \hat{Z} & \hat{Y} \end{bmatrix} = \begin{bmatrix}\hat{X} & \hat{Z} & \hat{Y} \end{bmatrix} \underbrace{\begin{bmatrix} B_{11} & 0 & 0 \\ B_{21} & B_{22} & B_{23}\\ 0 & 0 & B_{33} \end{bmatrix}}_{B}.
$$

Thus, the spectrum of $B$ satisfies,

$$
\sigma(B) = \underbrace{\sigma(B_{11}) \cup \sigma(B_{22}) \cup \sigma(B_{33})}_{\{\series{\lambda}{k}\}}.
$$

Thus, 

$$
\range(X) \cap \range(Y) = \range(X) = \range(Y)
$$


*example*
$A$ has eigenvalues 

$$
1, 1, 2, 3, 4, 4, 4, 5.
$$

Then, $1, 1, 2$ has unique invariant subspace while $2,3,4,4$ perhaps not.



Changing to unitary basis. For $S$ an invariant subspace, let $\series{u}{k}$ be basis, the first k columns of unitary matrix $U$, 

$$
U = \begin{bmatrix}
    u1 & \dots &u_k & U_2,
\end{bmatrix}
$$

in which $U_1 = \begin{bmatrix} u1 & \dots &u_k \end{bmatrix}$.

**Block deflation**
Let $A\in M_n(\F)$, with $\F = \R$ or $\C$, then get 

$$
U^HAU = \begin{bmatrix}
    T_{11} & T_{12}\\ 0 & T_{22}
\end{bmatrix}
$$

where $\sigma(T_{11}) \subseteq \sigma(A)$, $\sigma(A) = \sigma(T_{11}) \cup \sigma(T_{22})$.

Can continue this deflation on $T_{22}$ to get more blocks.