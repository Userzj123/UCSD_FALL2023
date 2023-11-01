# Lec12
*definition*

- $(B, X)$ is called an **eigenpair** or **right eigenpair** of $A$ if $X$ has linear independent columns and $ AX = XB$.
    It is of order $k$ if $X$ has $k$ columns.
    Also the $X$ is called an **eigenbasis** of $A$ and $B$ is called an **eigenblock** of $A$.
    Also we call $(B, X)$ **orthonormal** if $X$ has orthonormal columns.
    An invariant subspace of $A$ is also called an **eigenspace** of $A$.
    Furthermore, the eigenspace is called **simple** if
    $$
    \sigma(B) \cap (\sigma(A)\setminus\sigma(B)) = \phi
    $$

- $(B, Y)$ is called an **left eigenpair** of $A$ if $Y$ has linear independent columns and $ Y^HA  = BY^H$ or $A^HY = YB^H$.
    It is of order $k$ if $Y$ has $k$ columns.
    $\range(Y)$ is called a **left invariant subspace** or **left eigenspace** of $A$ satisfying $A^H\range(Y)\subseteq \range(Y)$.


*example*

$$
AX = XB
$$

Consider extension of columns of $X$ to orthonormal basis of $\C^n$ through Gram-Schmidt.

Put orthonormal basis as columns of unitary matrix $U = \begin{bmatrix} U_1 & U_2 \end{bmatrix}$, s.t. $U_1$ has the same span as $X$. Then, $(T_{11}, U_1)$ is an eigenpair of $A$ while $(T_{22}, U_2)$ is a left eigenpair of $A$,

$$
\begin{aligned}
    U^HAU &= \begin{bmatrix} T_{11} & T_{12} \\ 0 & T_{22} \end{bmatrix}\\
    \begin{bmatrix} AU_1 & AU_2 \end{bmatrix} &= \begin{bmatrix} U_1 & U_2\end{bmatrix}\begin{bmatrix} T_{11} & T_{12} \\ 0 & T_{22}\end{bmatrix},\\
    AU_1 & = U_1 T_{11} \Longleftrightarrow (T_{11}, U_1) \text{ is an eigenpair of A}
\end{aligned}
$$


$$
\begin{aligned}
    U^HAU &= \begin{bmatrix} T_{11} & T_{12} \\ 0 & T_{22} \end{bmatrix}\\
    \begin{bmatrix} U_1^H\\ U_2^H \end{bmatrix}A &= \begin{bmatrix} T_{11} & T_{12} \\ 0 & T_{22}\end{bmatrix}\begin{bmatrix} U_1^H \\ U_2^H\end{bmatrix},\\
    U_2^HA & = T_{22} U_2^H \Longleftrightarrow (T_{22}, U_2) \text{ is a left eigenpair of A}\\
\end{aligned}
$$


So $\range(U_2)$ is a left invariant subspace of $A$, which satisfies $ \range(U_2) = \range(U_1)^\perp$. And if $S\subseteq \C^n$ is an eigenspace of $A$, then $S^\perp$ is a left eigenspace of $A$. We call $S^\perp$ the **complementary left eigenspace** of $S$.


Why would we want the upper block triangular instead of upper triangular?
-> When we only want the real component in the triangular matrix.

*lemma*
Let $A\in M_n(\R)$, $(\lambda, x)$ be one of its eigenpairs, then write $x = u + \ii v$, where $u, v \in \R^n$. Then, we have
- $(\bar{\lambda}, \bar{x})$ is an eigenpair of $A$
- If $\lambda \in \R$, then $(\lambda, u )$ is an eigenpair of $A$ if $u\neq 0$, and $(\lambda, v )$ is an eigenpair of $A$ if $v\neq 0$.
- If $\lambda \notin \R$, then
  1. $u, v \neq 0$
  2. $u, v$ are linearly independent


*proof*
1. 
   $$
   \begin{aligned}
        Ax &= \lambda x\\
        \overline{Ax} & = \overline{\lambda x}\\
        \bar{A}\bar{x} & = \bar{\lambda} \bar{x}\\
        A \bar{x} & = \bar{\lambda} \bar{x}
   \end{aligned}
   $$

2. Consider $u = \frac{x + \bar{x}}{2}, v = \ii\frac{\bar{x} - x}{2}$, and since $\lambda \in R$, then $A\bar{x} = \bar{\lambda} \bar{x} = \lambda \bar{x}$. Thus, we have

    $$
    \begin{aligned}
        Au = \frac{Ax + A\bar{x}}{2} = \lambda u\\
        Av = \ii\frac{A\bar{x} - Ax}{2} = \lambda v\\
    \end{aligned}
    $$

3. Suppose if $u = 0$ or $v = 0$, then 

    $$
    \begin{aligned}
    x = \begin{cases}
        \ii v, & \if u = 0 \\ u, & \if v=0
    \end{cases}
    & \Rightarrow 
    \bar{x} = \begin{cases}
        - \ii v, & \if u = 0\\
        u, & \if v=0
    \end{cases}\\
    A\bar{x} & = \lambda \bar{x}\\
    \text{However } A\bar{x} & = \bar{\lambda}\bar{x} \text{ as well, so } \lambda = \bar{\lambda}\\
    \Rightarrow \lambda \in \R\text{, which contradicts.}
    \end{aligned}
    $$


    Assume $u, v$ linearly dependent, then $v = \alpha u$ for some $\alpha\neq 0, \alpha \in \C$. But then $x = u+ \ii v = u(1+\ii\alpha)$, then $(\lambda, u)$ is also an eigenpair, while $u$ is real, which contradicts.

BTW, if $\lambda \in R$, we usually consider real valued eigenvectors for it.

**Real Schur Decomposition**
Let $A \in M_n(\R)$, then $\exists$ orthogonal $Q\in M_n(\R)$ s.t.,

$$
Q^TAQ = T = \begin{bmatrix}
    T_{11} & & \dots & & \\
    & T_{22} &  \dots & &\\
    & & \ddots & & \\
    0 & & & & T_{kk}
\end{bmatrix}
$$

which has following properties:

- $T_{jj} \in M_1(\R) \text{ or } M_2(\R)$ and if $T_{jj}\in M_2(\R)$ then its eigenvalues are not real but complex conjugate pairs.