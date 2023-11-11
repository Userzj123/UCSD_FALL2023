# Lecutre 15 Nov 3
There is a result called **Roth's Ramaul Rule**,

$$
W^{_1}\begin{bmatrix} T_{11} & T_{12}\\ 0 & T_{22} \end{bmatrix} W = \begin{bmatrix} T_{11} & 0 \\ 0 & T_{22}\end{bmatrix}\\
\Longleftrightarrow \begin{bmatrix} I & -Z \\ 0 & I \end{bmatrix}\begin{bmatrix} T_{11} & T_{12}\\ 0 & T_{22} \end{bmatrix}\begin{bmatrix} I & Z \\ 0 & I \end{bmatrix} \text{ for some } Z
$$

Also read as $T_{11}Z - ZT_{22} = -T_{12}$, or alternatively $T_{11}Y - YT_{22} = T_{12}$.

*proposition*
For $A\in M_m(\C), B\in M_n(\C)$, $\lambda$ is an eigenvalue of $S:M_{m,n}(\C) \rightarrow M_{m,n}(\C) ( X \rightarrow AX-XB)$ iff $\lambda = \alpha - \beta$, where $\alpha \in \sigma(A), \beta \in \sigma(B)$.


---

*definition*
Define the **Kronecker or tensor product** of matrices $C, E$ as

$$
C\otimes E = \begin{bmatrix}
    c_{11}E & \dots & c_{1n}E\\
    \vdots & \ddots & \vdots\\
    c_{n1}E & \dots & c_{nn}E
\end{bmatrix}.
$$

---

According to the definition of Kronecker production of two matrices, we have the matrix representation of $S$ as

$$
I_n \otimes A - B^\top\otimes I_m \in M_{mn}(\C)
$$


from basis elements, $E_{ij}\in M_{m, n}(\C)$, the $(i, j)$ entry of which, equal to $1$, is the only non-zero element. And 

$$
X = \sum_{i, j} \alpha_{ij} E_{ij}.
$$


*proposition*
If $\series{\alpha}{m}$ are the eigenvalues of $A$ and $\series{\beta}{n}$ are the eigenvalues of $B$, then the eigenvalues of $I_n \otimes A - B^\top\otimes I_m$ are $\alpha_i - \beta_j, 1\le i\le m$ and $1\le j \le n$.

*proof*
Let

$$
\hat{A} = I_n\otimes A = \begin{bmatrix}
A & & &0 \\ & A & & \\ & & \ddots & \\ 0& & & A
\end{bmatrix}
$$

$$
\hat{B}^\top = B^\top\otimes I_m = \begin{bmatrix}
b_{11}I_m & b_{21}I_m & \dots\\
b_{12} I_m & b_{22} I_m & \dots\\
\vdots & \vdots & \ddots
\end{bmatrix}.
$$

Now let $Q^HAQ = T$ be a Schur decomposition of $A$ and $U^HB^\top U = R$ be a Schur decomposition of $B^\top$. Form $\hat{Q} = I_n\otimes Q$ and $\hat{U} = U \otimes I_m$. Then we have

$$
\hat{Q}^H\hat{A}\hat{Q} = \begin{bmatrix}
    Q^HAQ & & & \\
    & Q^HAQ & & \\
    & & \ddots & \\
    & & & Q^HAQ
\end{bmatrix} = I_n \otimes T  := \hat{T} =\begin{bmatrix}
    T & & & \\
    & T & & \\
    & & \ddots & \\
    & & & T
\end{bmatrix}.
$$


Also, $\hat{U}^H\hat{B}^\top \hat{U} = R\otimes I_m  := \hat{R}$


Since $\hat{Q}^H \hat{B}^\top \hat{Q} = \hat{B}^\top$, $\hat{U}^H \hat{T}\hat{U} = \hat{T}$, 

$$
\begin{bmatrix}
    u_{11}^H I_m & \dots & u_{n1}^H I_m \\ 
    \vdots & & \vdots\\
    u_{1n}^H I_m & \dots & u_{nn}^H I_m
\end{bmatrix}
\begin{bmatrix}
    u_{11} T & \dots & u_{1n}T\\
    \vdots & & \vdots\\
    u_{n1}T & \dots & u_{nn}T
\end{bmatrix}
= 
\begin{bmatrix}
    T & & & \\
    & T & & \\
    & & \ddots & \\
    & & & T
\end{bmatrix}
$$

Thus, we could have

$$
\hat{U}^H\hat{Q}^H (\hat{A} - \hat{B}^\top) \hat{Q}\hat{U} = \hat{T} - \hat{R}
$$


<span style='color:red'> Must the diagonal of upper triangular be eigenvalues?</span>

---

We started from $\begin{bmatrix} T_{11} & T_{12}\\ 0 & T_{22} \end{bmatrix}$ and get to $\begin{bmatrix} T_{11} & 0 \\ 0 & T_{22}\end{bmatrix}$. How about starting even earlier from a general matrix?

Let's consider $A \in M_n(\C)$, and use $(B_1, X_1)$ as simple orthonormal eigenpair of $A$. Then can extend $X_1$ to unitary matrix $\begin{bmatrix} X_1 & Y_2\end{bmatrix}\in M_n(\C)$, and thus

$$
\begin{bmatrix} X_1^H \\ Y_2^H \end{bmatrix}A \begin{bmatrix} X_1 & Y_2  \end{bmatrix} = \begin{bmatrix} B_1 & C \\ 0 & B_2 \end{bmatrix},
$$

for some $B_2$ , $C$, and  $\sigma(B_1) \cap \sigma(B_2) = \phi$. So $\exists Z$ satisfying $B_1Z - ZB_2 = -C$ s.t.

$$
\begin{bmatrix}
    I_k & -Z\\ 0 & I_{n-k}
\end{bmatrix}\begin{bmatrix}
    B_1 & C \\ 0 & B_2
\end{bmatrix} = 
\begin{bmatrix}
    B_1 & 0\\ 0 & B_2
\end{bmatrix}
$$

Thus,  

$$
\begin{bmatrix}
    B_1 & 0 \\ 0 & B_2
\end{bmatrix}
= \begin{bmatrix}
    I_k & -Z \\ 0 & I_{n-k}
\end{bmatrix}\begin{bmatrix}
    X_1^H \\Y_2^H
\end{bmatrix}A \begin{bmatrix}
    X_1 & Y_2
\end{bmatrix}
\begin{bmatrix}
    I_k & Z \\ 0 & I_{n-k}
\end{bmatrix}
$$

Noting that 

$$
\begin{bmatrix} X_1^H \\ Y_2^H \end{bmatrix}  \begin{bmatrix} X_1 & Y_2  \end{bmatrix} = I_n,
$$

then 

$$
\begin{bmatrix} I_k & -Z \\ 0 & I_{n-k} \end{bmatrix} \begin{bmatrix} X_1^H \\ Y_2^H \end{bmatrix}  \begin{bmatrix} X_1 & Y_2  \end{bmatrix} \begin{bmatrix} I_k & Z \\ 0 & I_{n-k} \end{bmatrix}= I_n,
$$

so 


$$
\begin{bmatrix} B_1 & 0 \\ 0 & B_2 \end{bmatrix} = \begin{bmatrix} X_1^H - ZY_2^H\\ Y_2^H \end{bmatrix} A \begin{bmatrix} X_1 & X_1Z+Y_2 \end{bmatrix} = \begin{bmatrix} Y_1^H \\ Y_2^H \end{bmatrix} A \begin{bmatrix} X_1 & X_2 \end{bmatrix}
$$

so we have the **spectral representation of A**,

$$
A = \begin{bmatrix} X_1 & X_2 \end{bmatrix} \begin{bmatrix} B_1 & 0 \\ 0 & B_2 \end{bmatrix} \begin{bmatrix} Y_1^H \\ Y_2^H \end{bmatrix} = X_1B_1Y_1^H + X_2 B_2 Y_2^H
$$


Note:
1. basis $\begin{bmatrix} X_1 & X_2 \end{bmatrix}$ is not necessarily unitary.
2. orthogonality
   
   $$
    \begin{bmatrix} Y_1^H \\ Y_2^H \end{bmatrix}\begin{bmatrix} X_1 & X_2 \end{bmatrix} = I
   $$

3. $\range(X_2)$ is an invariant subspace and $(B_2, X_2)$ is an eigenpair of $A$.

4. May continue deflation to get $S\in M_n(\C)$ nonsingular s.t

    $$
    S^{-1}AS = \begin{bmatrix}
        B_1 & & & \\
        & B_2 & & \\
        & & \ddots & \\
        & & & B_r
    \end{bmatrix}
    $$

    as long as $\sigma(B_i) \cap \sigma(B_j) = \phi$.
    
    *Notation*:

    $$
    \begin{bmatrix}
        B_1 & & & \\
        & B_2 & & \\
        & & \ddots & \\
        & & & B_r
    \end{bmatrix} = B_1 \oplus B_2 \oplus \dots \oplus B_r.
    $$