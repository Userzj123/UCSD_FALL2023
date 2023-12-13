# Lec 21 Nov 22

## Non-square Matrix
```{prf:remark}
Let $A \in M_{m, n}(\C)$, then

1. $A^HA \in M_n(\C)$ is **positive semi-definite** because 
   
   $$
   x^HA^HAx = (Ax)^HAx \ge 0
   $$

2. $\rank(A^HA) = \rank(A)$
3. $\rank(A) = \#\{\lambda \gt 0 | \underbrace{\lambda \in \sigma(A^HA)}_{\text{multiset}}\}$

All results can be applied to $A^H$ to get properties on $AA^H$.
```


```{prf:proposition}
Let $A \in M_{m,n}(\C)$, then

$$
\{\lambda \gt 0 | \lambda \in \sigma(A^HA)\} = \{\lambda \gt 0 | \lambda \in \sigma(AA^H)\}
$$

as multiset. 
```
This follows from 

````{prf:lemma}
Let $A \in M_{m,n}(\C), B\in M_{n,m}(\C)$, then

$$
\{\lambda \neq 0 | \lambda \in \sigma(BA)\} = \{\lambda \neq 0 | \lambda \in \sigma(AB)\}
$$

```{prf:proof}

Note 

$$
\begin{bmatrix}I & 0 \\ A & I\end{bmatrix}\begin{bmatrix} BA & B \\ 0 & 0\end{bmatrix}\begin{bmatrix}I & 0 \\ -A & I\end{bmatrix} 
=
\begin{bmatrix}0 & B \\ 0 & AB\end{bmatrix}
$$

Thus, $\begin{bmatrix} BA & B \\ 0 & 0\end{bmatrix} \sim \begin{bmatrix}0 & B \\ 0 & AB\end{bmatrix}$.
```
````


## Singular Value Decomposition

````{prf:theorem}
Given $A\in M_{m,n}(\C)$ with $\rank(A) = r$, then there exist unitary $U\in M_{m}(\C)$ and $V\in M_n(\C) \st$

$$
U^HAV = S\in M_{m, n}(\R),
$$

where $S = \begin{bmatrix}S_1 & 0 \\ 0 & 0\end{bmatrix}$, for $S_1 = \sigma_1\oplus\dots \oplus \sigma_r \in M_r(\R)$, and $\sigma_1 \ge \dots \ge \sigma_r\gt 0$.

```{prf:proof}
Consider $A^HA$ which has $r$ positive eigenvalues, and $n-r$ are zero eigenvalues. We use notation:

$$
\lambda_1(A^HA) \ge \dots \ge \lambda_r(A^HA) \gt \lambda_{r+1}(A^HA) = \dots = \lambda_n(A^HA) = 0.
$$

Now $A^HA$ is Hermitian so unitarily diagonalizable, so $\exists$ unitary matrix $ V\in M_{n}(\C) \st$

$$
V^HA^HAV = \begin{bmatrix}
    \lambda_1(A^HA) & & & & & \\
    & \ddots & & & & 0\\
    & & \lambda_r(A^HA) & & & \\
    & 0 & & & & 0
\end{bmatrix}
= \begin{bmatrix}
    S_1^2 & 0 \\0 & 0
\end{bmatrix}
$$

in which $S_1\in M_r(\R)$.

Now write $V = \begin{bmatrix}V_1 & V_2 \end{bmatrix}$ where $V_1 \in M_{n,r}(\C)$ then get

$$
V^HA^HAV = \begin{bmatrix}
    V_1^HA^HAV_1 & V_1^HA^HAV_2\\
    V_2^HA^HAV_1 & V_2^HA^HAV_2
\end{bmatrix}
= \begin{bmatrix}
    S_1^2 & 0 \\ 0 & 0
\end{bmatrix}.
$$


Note $V_2^HA^HAV_2 = (AV_2)^HAV_2 = 0 \Rightarrow AV_2 = 0$.

Thus, 

$$
\trace((AV_2)^HAV_2) = \sum_{i}\sum_{j} |(AV_2)_{ij}|^2 \Rightarrow (AV_2)_{ij} = 0, \forall i, j.
$$

---
Let $U_1 = AV_1 S_1^{-1}$, note $U_1^HU_1 = S_1^{-1}V_1^HA^HAV_1 S_1^{-1} = I$, so $U_1$ has orthonormal columns. Also, 

$$
U_1^HAV_1 = S_1^{-1} V_1^HA^HAV_1 = S_1.
$$

Let $U= \begin{bmatrix}U_1 & U_2\end{bmatrix}\in M_m(\C)$ unitary, then

$$
U^HAV = \begin{bmatrix} U_1^HAV_1 & U_1^HAV_2 \\ U_2^HAV_1 & U_2^HAV_2\end{bmatrix} = \begin{bmatrix} S_1 & 0 \\ U_2^HAV_1 & 0 \end{bmatrix}
$$


Lastly, $U_2^HAV_1 = U_2^HU_1S_1 = 0$, then

$$
U^HAV = \begin{bmatrix}
    S_1 & 0 \\ 0 & 0
\end{bmatrix}.
$$

Note since $A = USV^H$, we get that 

$$
AA^H = USV^HVS^\top U^H = USS^\top U^H.
$$

Note 
$S, S_1, r, \sigma_1, \dots, \sigma_r$ are uniquely determined, since

$$
V^HA^HAV = \begin{bmatrix}
    \lambda_1(A^HA) & & & & & \\
    & \ddots & & & & 0\\
    & & \lambda_r(A^HA) & & & \\
    & 0 & & & & 0
\end{bmatrix}.
$$

Also $\sigma_1, \dots, \sigma_r$ are unitarily invariant. If $\hat{U}, \hat{V}$ unitary, then $\sigma_1, \dots, \sigma_r$ of $A$ are the same of those of $\hat{U}^HA\hat{V}$. This is because $\sigma(A^HA) = \sigma(\hat{U}^HA^H\hat{V}\hat{V}^HA\hat{U})$.

Finally note, proof works for $A\in M_{m,n}(\R)$ with $U\in M_m(\R), V\in M_n(\R)$ orthogonal to get **real SVD**.

```
````

```{prf:definition} Real SVD
Given $A\in M_{m,n}(\R)$, $\exists U\in M_m(\R), V\in M_n(\R)$ orthogonal, $r = \rank(A)$ such that

$$
A=USV^T
$$

where

$$
S = \begin{bmatrix}
    \sigma_1 \oplus \dots \oplus \sigma_r & 0 \\ 0 & 0
\end{bmatrix}
$$

where $\sigma_j = \lambda_j(A^\top A)$.
```