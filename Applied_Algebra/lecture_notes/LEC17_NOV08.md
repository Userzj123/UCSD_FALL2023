# Lec 17 Nov 8

*proposition*
$N \in M_n(\C)$, strictly upper triangular is similar to direct sum of Jordan blocks.

*proof*
Induction

Initial step n = 1

$$
N = [0] = J_1(0)
$$

Main induction step: Assume statement true for $n=r-1$, show for $n=r$

$N\in M_r(\C)$  strictly upper triangular. Write

$$
N= \begin{bmatrix}
0 & a^\top\\ 0 & N_1
\end{bmatrix}
$$

in which $N_1\in M_{r-1}(\C)$ is also strictly upper triangular matrix. So $\exists$ invertible $\hat{X}_1 = M_{r-1}(\C)$ and $m_1, \dots, m_k\ge 1 \st \hat{X}_1^{-1}\hat{N}_1 \hat{X}_1 = J_{m_1}(0)\oplus \dots \oplus J_{m_k}(0)$.

Then, let $X_1 = \begin{bmatrix}
    1 & 0\\ 0 & \hat{X_1}
\end{bmatrix}$, $X_1^{-1} = \begin{bmatrix}
    1 & 0\\ 0 & \hat{X}_1^{-1}
\end{bmatrix}$, we can get

$$
\begin{aligned}
    X_1^{-1} N X_1 &= \begin{bmatrix}
    0 & a^\top \\ 0 & \hat{X}_1^{-1} N_1\hat{X}_1
\end{bmatrix},\\
    & =\begin{bmatrix}
        0 & a_1^\top & a_2^\top\\
        0 & J_{m_1}(0) & 0 \\
        0 & 0 & J
    \end{bmatrix},
\end{aligned}
$$


In order to prove that this is a sum of Jordan block, we need to try using similarity transform to make $(1, 3)$ block to be $0$ and $(1, 2)$ block to be $e_1^\top$ or $0^\top$.

Use Gaussian elimination matrices,

$$
E_0 = \begin{bmatrix}
    1 & z^\top & 0 \\
    0 & I_{m_1} & 0\\
    0 & 0 & I
\end{bmatrix}, E_0^{-1}
\begin{bmatrix}
     1 & -z^\top & 0 \\
    0 & I_{m_1} & 0\\
    0 & 0 & I   
\end{bmatrix},
$$

Then, we have

$$
\begin{aligned}
    E_0^{-1} X_1^{-1}N X_1 E_0 &= \begin{bmatrix}
        0 & a_1^\top - z^\top J_{m_1}(0) & a_2^\top\\
        0 & J_{m_1}(0) & 0\\
        0 & 0 & J
    \end{bmatrix}
\end{aligned}
$$

Let $z = J_{m_1}(0)a_1$, then we could further simplify the expression since $a_1 - J_{m_1}(0)^\top z = \underbrace{(I-J_{m_1}(0)^\top J_{m_1}(0))}_{e_1 e_1^\top} a_1 =(e_1^\top a_1)e_1 $

$$
E_0^{-1} X_1^{-1}N X_1 E_0 = \begin{bmatrix}
    0 & (e_1^\top a_1)e_1 & a_2^\top\\
    0 & J_{m_1}(0) & 0\\
    0 & 0 & J
\end{bmatrix}.
$$


Case 1.
$e_1^\top a_1 = 0$

$$
E_0^{-1}X_1^{-1}N X_1 E_0 = \begin{bmatrix}
    0 & 0 & a_2^\top\\
    0 & J_{m_1}(0) & 0 \\
    0 & 0 & J
\end{bmatrix}
$$

Let permutation matrix 

$$
P = P_{12}P_{23}\dots P_{m_1, m_1+1},
$$

then 

$$
P^\top E_0^{-1}X_1^{-1}N X_1 E_0 P = \begin{bmatrix}
    J_{m_1}(0) & 0 &  0 \\
    0 & 0 & a_2^\top\\
    0 & 0 & J
\end{bmatrix}.
$$

So $\exists \hat{X}_2$ invertible $\st$

$$
\hat{X}_2^{-1} \begin{bmatrix}
    0 & a_2^\top \\
    0 & J
\end{bmatrix} \hat{X}_2,
$$

is direct sum of Jordan blocks. Let $X_2 = \begin{bmatrix}
    1 & 0 \\ 0 & \hat{X}_2
\end{bmatrix}$, then

$$
X_2^{-1}P^\top E_0^{-1}X_1^{-1}N X_1 E_0 P X_2 = \begin{bmatrix}
    J_{m_1}(0) & 0 \\ 0 & \hat{X}_2^{-1} \begin{bmatrix}
    0 & a_2^\top \\
    0 & J
\end{bmatrix} \hat{X}_2
\end{bmatrix}.
$$


Case 2. $e_1^\top a_1\neq 0$, then consider

$$
S^{-1}= \begin{bmatrix}
    \frac{1}{e_1^\top a_1} & 0 & 0 \\ 0 & I_m & 0\\ 0 & 0 & \frac{1}{e_1^\top a_1}I
\end{bmatrix}
$$

and its inverse as,

$$
S= \begin{bmatrix}
    e_1^\top a_1 & 0 & 0 \\ 0 & I_m & 0\\ 0 & 0 & e_1^\top a_1 I
\end{bmatrix}
$$

Then,

$$
\begin{aligned}
    S^{-1} E_0^{-1}X_1^{-1}N X_1 E_0 S &= \begin{bmatrix}
    0 & e_1^\top & a_2^\top\\
    0 & J_{m_1}(0) & 0\\
    0 & 0 & J
\end{bmatrix}\\
& = \begin{bmatrix}
    J_{m_1+1}(0) & e_1 a_2^\top\\
    0 & J
\end{bmatrix}
\end{aligned}

$$


Let $E_1 = \begin{bmatrix}
    I_{m_1+1} & Z \\ 0 & I
\end{bmatrix}$, $E_1^{-1} = \begin{bmatrix}
    I_{m_1+1} & -Z \\ 0 & I
\end{bmatrix}$, then

$$
E_1^{-1} S^{-1} E_0^{-1}X_1^{-1}N X_1 E_0 S E_1 = \begin{bmatrix}
    J_{m_1+1}(0) & J_{m_1+1}(0)Z + e_1a_2^\top - ZJ\\
    0 & J
\end{bmatrix}
$$

Take $Z = - e_2 a_2^\top$, then the $(1,2)$ block becomes 

$$
J_{m_1+1}(0)Z + e_1a_2^\top - ZJ = -\cancel{e_1 a_2^\top} + \cancel{e_1a_2^\top} + e_2a_2^\top J.
$$

Take $E_2 = \begin{bmatrix}
    I_{m_1 + 1} & -e_3a_2^\top J\\
    0 & I
\end{bmatrix}$, then

$$
E_2^{-1} E_1^{-1} S^{-1} E_0^{-1}X_1^{-1}N X_1 E_0 S E_1 E_2 = \begin{bmatrix}
    J_{m_1+1}(0) & e_3a_2^\top J^2\\
    0 & J
\end{bmatrix}
$$

For $E_i = \begin{bmatrix}
    I_{m_1 + 1} & -e_ia_2^\top J^{i-1}\\
    0 & I
\end{bmatrix}$, we can get $J^p = 0$, then 

$$
E_p^{-1} \dots E_2^{-1} E_1^{-1} S^{-1} E_0^{-1}X_1^{-1}N X_1 E_0 S E_1 E_2 \dots E_p= \begin{bmatrix}
    J_{m_1+1}(0) & 0\\
    0 & J
\end{bmatrix},
$$

which is a sum of Jordan blocks.




*Consequence*
**Jordan Canonical Form**
Let $A\in M_n(\C)$ with distinct eigenvalues $\series{\lambda}{k}$ with multiplicity $\series{m}{k}$ with $\sum_i m_i = n$. Then $\exists m_{ij}, 1\le i\le k, 1\le j\le r_i$, with $m_i = \sum_{j=1}^{r_i} m_{ij}$ and nonsingular $X\in M_n(\C) \st$ 

$$
X^{-1}AX = J = J_1\oplus \dots \oplus J_k
$$

in which $J_i = J_{m_{i1}}(\lambda_i) \oplus \dots \oplus J_{m_{ir_i}}(\lambda_i)$.

*example*

$$
J = \begin{bmatrix}
    0 & 1 & & & & & &\\
    0 & 0 & & & & & &\\
    & & 1 & & & & & &\\
    & & & 1 & 1& & & &\\
    & & & 0 & 1& & & &\\
    & & & & & 2& 1& 0&\\
    & & & & & 0& 2& 1&\\
    & & & & & 0& 0& 2&\\
\end{bmatrix}
$$


structure of J:

Define $r_p(\lambda_i) = \rank((J-\lambda_iI)^p)$, then

$$
r_{p-1}(\lambda_i) - r_p(\lambda_i) = \#\{j | m_{ij}\ge p\}\\
r_{p+1}(\lambda_i) - 2r_p(\lambda_i) + r_{p-1}(\lambda_i) = \# \{j|m_{ij} = p\}
$$