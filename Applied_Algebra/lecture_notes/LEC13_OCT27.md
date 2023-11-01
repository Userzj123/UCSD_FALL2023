# Lecture 13
*proof* Real Schur Decomposition
We show one step of deflation, for an arbitrary eigenvalue. Let $\lambda \in \sigma(A)$, 
- If $\lambda$ real, then $\exists x \in \R^n$ eigenvector for $\lambda$, s.t.

$$
Ax = \lambda x\\
A \begin{bmatrix} x & \dots \end{bmatrix} = \begin{bmatrix} x & \dots \end{bmatrix}\begin{bmatrix} \lambda & \dots \\ 0 & \ddots \end{bmatrix}
$$

- If $\lambda$ not real then $\lambda = \alpha + \ii \beta$ and have eigenpairs $(\lambda , x), (\bar{\lambda}, \bar{x})$. Write $x = u +\ii v$, 

$$
\begin{aligned}
    Ax &= \lambda x\\
    Au + \ii Av & = \alpha u - \beta v + \ii (\beta u + \alpha v)\\
    A \begin{bmatrix} u & v \end{bmatrix} & = \begin{bmatrix} u & v \end{bmatrix} \underbrace{\begin{bmatrix} \alpha & \beta \\ - \beta & \alpha \end{bmatrix}}_{T_{11}}\\
    A \begin{bmatrix} u & v & \dots \end{bmatrix} &= \begin{bmatrix} u & v & \dots\end{bmatrix} \begin{bmatrix} T_{11} & \hat{T}_{12}\\0 & \hat{A} \end{bmatrix}
\end{aligned}

$$

Use Gram-Schimidt to find $Q$ orthogonal s.t.

$$
Q^TAQ = \begin{bmatrix} \lambda & \dots \\ 0 & \ddots \end{bmatrix} \text{ or } \begin{bmatrix} T_{11} & \dots \\ 0 & \ddots \end{bmatrix} 
$$

in which $T_{11}\sim\begin{bmatrix} \alpha & \beta \\ -\beta & \alpha \end{bmatrix}$. And then, repeat the process...


*Consequence*
If $A$ has $n$ real eigenvalues, then $\exists Q$ orthogonal s.t. $Q^TAQ = T$ upper triangular.


## Unitarily Diagonalizable
*definition*
$A\in M_n(\C)$ is called **Hermitian** if 

$$
A = A^H.
$$

With Schur decomposition, get

$$
\begin{aligned}
    Q^HAQ &= T \\
    Q^HA^HQ &= T^H\\
    Q^HAQ &= T^H\\
    T & = T^H\\
    \Rightarrow T & = \Lambda \text{ diagonal}\\
    \Rightarrow Q^HAQ & = \Lambda,
\end{aligned}
$$

Thus, $A$ is diagonalizable and **unitarily diagonalizable**. Furthermore, $\Lambda \in M_n(\R)$ eigenvalue of $A$ is real.

*Notation*
$A = Q\Lambda Q^H$ is called the **spectral** or **eigen decomposition** of $A$.

We can also write 

$$
A = \sum_{j=1}^n \lambda_j q_j q_j^H.
$$

If $A \in M_n(\R)$ and Hermitian, then $A$ is called **symmetric**: $A = A^T$. Then it turns out that $\exists Q\in M_n(\R)$ orthogonal s.t.,

$$
Q^TAQ = \Lambda.
$$

What other matrices are unitarily diagonalizable?
If $A$ is unitarily diagonalizable then 

$$
A = Q\Lambda Q^H.
$$

Then, we could have

$$
\begin{aligned}
    AA^H & = Q\Lambda Q^H Q \Lambda^H Q^H\\
    & = Q\Lambda \Lambda^H Q^H\\
    & = Q\Lambda^H \Lambda Q^H\\
    & = A^HA
\end{aligned}
$$

*definition*
We call $A\in M_n(\C)$ **normal** if 

$$
AA^H = A^HA.
$$

If $A$ normal, then Schur decomposition gives $A = QTQ^H $. Then, 

$$
\begin{aligned}
    AA^H = QTT^HQ^H\\
    A^HA = QT^HTQ^H\\
    A \text{ normal} \Longleftrightarrow AA^H = A^HA \Longleftrightarrow TT^H = T^HT \Longleftrightarrow T \text{ normal}
\end{aligned}
$$

*lemma*
If $T\in M_n(\C)$ is upper triangular and normal, then $T$ diagonal.

*proof*
Induction on row $i$ being that of a diagonal matrix.

Initial induciton: step i = 1

$$
T = \begin{bmatrix}
    \alpha & b^H \\ 0 & T_{22}
\end{bmatrix},
\quad
T^H = \begin{bmatrix}
    \alpha^H & 0 \\ b & T_{22}^H
\end{bmatrix},
$$

Then,

$$
\begin{aligned}
    (TT^H)_{11} & = (T^HT)_{11}\\
    \alpha \alpha^H + b^Hb &= \alpha \alpha^H\\
    \|b\|_2 & = 0\\
    b &= 0
\end{aligned}
$$

so 

$$
T = \begin{bmatrix}
    \alpha & 0 \\ 0 & T_{22}
\end{bmatrix}.
$$


Main induction step: Statement true for $i = k-1$, show true for $i = k$

$$
T = \begin{bmatrix}
    D_{11} & 0 & 0 \\ 0 & \alpha & b^H\\ 0 & 0 & T_{33}
\end{bmatrix}.
$$

Then, 

$$
\begin{aligned}
    (TT^H)_{kk} & = (T^HT)_{kk}\\
    \alpha \alpha^H + b^Hb &= \alpha \alpha^H\\
    \|b\|_2 & = 0\\
    b &= 0
\end{aligned}
$$

*proposition*
$A\in M_n(\C)$ normal $\Longleftrightarrow$ $A$ unitarily diagonalizable.


*example* 
- Hermitian matrices: $A = A^H$,
- Skew hermitian matrices : $A = -A^H$,
- Unitary matrices: $A^H = A^{-1}$,

and others.
