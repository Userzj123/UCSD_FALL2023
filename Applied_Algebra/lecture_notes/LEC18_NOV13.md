# Lec18 Nov 13

$$
A \in M_n(\C) \sim J = J_1 \oplus \dots \oplus J_k,
$$

in which $J_1 = J_{m_{11}}(\lambda_1) \oplus \dots \oplus J_{m_{1r_1}}(\lambda_1)$ and $m_1 = \sum_{j=1}^{r_1} m_{1j}$. Furthermore, $\series{\lambda}{k}$ are distinct eigenvalues of $A$, and $\series{m}{k}$ are multiplicities, respectively, where $m_1+\dots + m_k = n$.


*definition*
Define $r_p(\lambda_i) := \rank\left((A-\lambda_i I)^p\right)$, then
$$
\begin{aligned}
    r_p(\lambda_i) := \rank\left((A-\lambda_i I)^p\right) & = \rank((J-\lambda_i I)^p) \\
    & = \sum_{j=1, j\neq i}^{k} m_j + \rank((J_i - \lambda_i I)^p)\\
    & = \sum_{j=1, j\neq i}^{k} m_j + \sum_{j=1}^{r_i}\rank(J_{m_{ij}}(0)^p).
\end{aligned}
$$

Then we have,

$$
r_{p-1}(\lambda_i) - r_p(\lambda_i) = \#\{j|m_{ij} \ge p\},
$$

and 

$$
r_{p-1}(\lambda_i) - 2 r_p(\lambda_i) + r_{p+1}(\lambda_i) = \# \{j|m_{ij} = p\}.
$$

*example*

Fix $\lambda$, we have

| $p$ | $r_p(\lambda)$ | number of $J_m(\lambda)$ with $m\ge p$ | number of $J_p(\lambda)$ |
| :-: | :------------: | :------------------------------------: | :----------------------: |
|  0  |       13       |                                        |                          |
|  1  |       10       |                   3                    |            0             |
|  2  |       7        |                   3                    |            1             |
|  3  |       5        |                   2                    |            1             |
|  4  |       4        |                   1                    |            0             |
|  5  |       3        |                   1                    |            1             |
|  6  |       3        |                   0                    |                          |


Then, we have

$$
J = \dots \oplus J_2(\lambda)\oplus J_3(\lambda)\oplus J_5(\lambda)\oplus \dots
$$


**Uniqueness of Jordan Block**

If $A\sim J\sim \tilde{J}$, Jordan canonical form, and 

$$
J = J_1 \oplus \dots \oplus J_k, \quad J_i = J_{m_{i1}}(\lambda_i) \oplus \dots \oplus J_{m_{ir_i}}(\lambda_i)\\
\tilde{J} = \tilde{J}_1 \oplus \dots \tilde{J}_k, \quad \tilde{J}_i = \tilde{J}_{m_{i1}}(\lambda_i) \oplus \dots \oplus \tilde{J}_{m_{ir_i}}(\lambda_i).
$$

with

$$
m_i = \sum_{j=1}^{r_i} m_{ij},\\
\tilde{m}_i = \sum_{j=1}^{\tilde{r}_i} \tilde{m}_{ij}.
$$

Then, 

$$
m_i = \tilde{m}_i, k= \tilde{k}, r_i = \tilde{r}_i, \text{can have } m_{ij} = \tilde{m}_{ij}.
$$

So, 
1. can talk about Jordan blocks of $A$.
2. $A, B\in M_n(\C)$ are similar $\Longleftrightarrow \sigma(A) = \sigma(B)$ and for each $\lambda \in \sigma(A)$, both $A, B$ have the same number and order of Jordan blocks associated to $\lambda$.
3. $A$ is nondefective iff all its Jordan block in canonical form have order 1.

*Drawback*
Jordan canonical form can be discontinuous in $A$. -> if perturb A, the Jordan canonical form will be very different.

*example*

$$
A_\epsilon = \begin{bmatrix} \epsilon & 0\\ 1 & 0\end{bmatrix} \underbrace{\begin{bmatrix} 0 & 0 \\ 0 & \epsilon\end{bmatrix}}\begin{bmatrix} -\frac{1}{\epsilon} & 1 \\ \frac{1}{\epsilon} & 0 \end{bmatrix}.
$$

If $\epsilon \neq 0$, $J_\epsilon = \begin{bmatrix} 0 & 0 \\ 0 & \epsilon\end{bmatrix}$. However, 

$$

\begin{cases}
J_\epsilon \to \begin{bmatrix} 0 & 0\\0 & 0\end{bmatrix}, & \epsilon \to 0\\
A_\epsilon = \begin{bmatrix} 0 & 0 \\ 1 & 0 \end{bmatrix}, J_\epsilon = \begin{bmatrix} 0 & 1\\ 0 & 0\end{bmatrix}, & \epsilon =0
\end{cases}
$$


## Eigenvalues of Hermitian Matrix
Let $A\in M_n(\C)$ Hermitian$: A = A^H$, then 

1. $A$ has only real eigenvalues. $x^HAx = \lambda x^Hx$ for eigenpair $(\lambda, x)$. Furthermore, $\lambda x^Hx = x^HAx = (x^HAx)^H = \bar{\lambda}x^Hx \Longleftrightarrow \lambda$ is real.
2. $x^HAx$ is real for all $x\in \C^n$.
3. $A$ is unitarily diagonalizable since Hermitian = normal


*proposition*
Given $A\in M_n(\C)$, then $\exists S, T \in M_n(\C)$ Hermitian $\st A = S+\ii T$.


*proof*
If $A = S+\ii T$, then

$$
A + A^H = S+\ii T + S - \ii T = 2S\\
A - A^H = \ii2T
$$

so $A = S+\ii T$ and $S, T$ is Hermitian matrix iff $S = \frac{1}{2}\left(A+ A^H\right)$ and $T = \frac{1}{2}\left(A- A^H\right)$.


*definition*
For $A \in M_n(\C)$, define the set

$$
F(A) = \{x^HAx | x\in \C^n, x^Hx = 1\}
$$

called the **field of values** of $A$.

*properties*
1. $\lambda \in F(A), \forall \lambda \in \sigma(A)$.
2. $$
    \begin{aligned}
        F(\alpha A + \beta I) &= \{ x^H(\alpha A + \beta I)x | x^Hx = 1\} \\
        & =  \alpha F(A) + \beta
    \end{aligned}
   $$
3. If $U\in M_n(\C)$ unitary, then $F(U^HAU) = F(A)$.
4. $F(A+B) \subseteq F(A) + F(B)$

*properties* 
For general matrix $A\in M_n(\C)$,  $F(A)\subseteq \C$ is a compact set.

*proof*
Let $f:\C^n\rightarrow \C ( x \rightarrow x^HAx)$, then $f$ continuous. Also $S = \{x|x^Hx = 1\}$ is compact. And $f(S) = F(A)$. Since $f$ is continuous and compact then $F$ is compact.

*proposition*
For general matrix $A\in M_n(\C)$, $F(A) \subseteq\C$ is convex.