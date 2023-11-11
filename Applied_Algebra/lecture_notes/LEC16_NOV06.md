# Lec 16 Nov 06
Let $A\in M_n(\C)$, and $\series{\lambda}{k}$ are distinct eigenvalues and $\series{m}{k}$ are the corresponding multiplicities. Then $A$ is similar to $T_1 \oplus \dots \oplus T_k$, where $T_i\in M_{m_i}(\C)$ are upper triangular and have only one eigenvalue $\lambda_i, \forall 1\le i \le k$.

Note we can write that $T_i = \lambda_i I_{m_i}+N_i$, where $N_i$ is strictly upper triangular (upper triangular and $0$ on the diagonal).

*definition*
$N_i$ is **nilpotent**, if 

$$
\exists l \ge 1 \st N_i^l = 0.
$$

Here, $N_i^{m_i-1} = 0$.

Note, nilpotent matrix have all eigenvalues $0$ and vice versus.

## Jordan blocks
*definition*
A **Jordan block** of order $m$ is $J_m(\lambda) \in M_{m}(\C)$ and 

$$
J_m(\lambda) = \begin{bmatrix}
    \lambda & 1 & \dots & & 0\\
    & \lambda & 1 & & \\
    & & \ddots & \ddots & \\
    & & & \lambda& 1 \\
    & & & & \lambda
\end{bmatrix}
$$

*property*
1. $J_m(0) = J_m(\lambda) - \lambda I_m$ and $\rank(J_m(0)) = m-1$
2. $\lambda\in \sigma(J_m(\lambda))$ and $\am(\lambda) = m$
3. For $J_m(\lambda), \gm(\lambda) = 1$ from rank-nullity theorem.
4. $$
    J_m(0)e_j = \begin{cases}
    0, & j = 1\\
    e_{j-1}, & \forall 2\le j\le m
    \end{cases}
    $$
    
    so 

    $$
    J_m(0)^p = \begin{bmatrix}  0_{1, p-1} & J_{m-p+1}(0)\\ 0 & 0 \end{bmatrix}
    $$

    Note $J_m(0)^m = 0$ and $J_m(0)^p \neq 0 $ for $p\lt m$. Also 
    
    $$
    \rank(J_m(0)^p) = \begin{cases}
        m - p, & \text{ for } p\le m\\
        0, & \text{ for } p \gt m
    \end{cases}
    $$

    so 

    $$
    \rank(J_m(0)^{p-1}) - \rank(J_m(0)^p) = \begin{cases}
        1, & \text{ if } p\le m,\\
        0, & \text{ if } p \gt m,
    \end{cases}
    $$

    Thus,

    $$
    \rank(J_m(0)^{p-1}) - \rank(J_m(0)^p) = 1 \Longleftrightarrow p \le m
    $$

5. $J_m(0)^\top J_m(0) = \begin{bmatrix}0 & 0 \\ 0 & I_{m-1} \end{bmatrix}$, and $I_m - J_m(0)^\top J_m(0) = e_1 e_1^\top$.
6. $J_{m+1} (0) = \begin{bmatrix} 0 & e_1^\top \\ 0 & J_m(0)\end{bmatrix}$


*tool*
**elementary permutation matrix** 

$$
P_{ij} = I - ww^T \in M_n(\R)
$$

where $w = e_i - e_j$.


$P_{ij}x$ swaps the $i, j$ entries of $x$ and leving the rest of the vector same as before.

*Note*
1. For $B\in M_n(\C)$, then $P_{ij}B$ swaps the $i, j$ rows of $B$, while $BP_{ij}$ swaps the $i, j$ columns of $B$.


2. $P_{ij}$ is an orthogonal matrix, since $ww^\top = (e_i - e_j) (e_i - e_j)^\top$, $I-ww^\top$ is the identity matrix with $i, j$ rows swapped.

3. $P_{ij}^2 = I$ and $P_{ij} = P_{ij}^\top = P_{ij}^{-1}$
4. $P_{ij}^{-1} AP_{ij} = P_{ij}AP_{ij}$, RHS means that swap $i, j$ columns of $A$ and then swap $i, j$ rows.

We now define a **permutation matrix** $P$ to be a finite product of **elementary permutation matrices**, e.g.

$$
P = P_{25}P_{15}P_{24}P_{13}.
$$



Note: permutation matrices are orthogonal but $P^2\neq I$ in general for $P$ permutation matrix, e.g.

$$
P^{-1} = P_{13}^\top P_{24}^\top P_{15}^\top P_{25}^\top \neq P
$$


*proposition*
For $N \in M_n(\C)$, strictly upper triangular, there exists $X\in M_n(\C)$ nonsingular and $\series{m}{k} \ge 1 \st$

$$
X^{-1} NX = J_{m_1}(0)\oplus \dots\oplus J_{m_k}(0).
$$



*proof*
Next lecture.


---

So for $T_i = \lambda_i I_{m_i} + N_i$, then $\exists X_i \in M_{m_i}(\C)$ and $m_{i1}, \dots, m_{ir_i} \ge 1, \st$

$$
\begin{aligned}
    X_i^{-1}T_iX_i &= \lambda_i I_{m_i} + X_i^{-1}N_i X_i\\
    & = \lambda_i I_{m_i} + (J_{m_{i1}}(0) \oplus \dots \oplus J_{m_{ir_i}}(0))\\
    & = J_{m_{i1}}(\lambda_i) \oplus \dots \oplus J_{m_{ir_i}}(\lambda_i)\\
    & :=  J_i
\end{aligned}
$$

Then with $X = X_1 \oplus \dots \oplus X_k$, we can get $A$ similar to $J_1 \oplus \dots \oplus J_k$.