# Lec23 Nov 27

r-by-m unitary matrix $U$, m-by-n matrix $A$ and n-by-n unitary matrix $V$, 

$$
U^HAV = S = \begin{bmatrix}
    \sigma_1 \oplus \dots \oplus \sigma_r & 0\\ 0 & 0
\end{bmatrix}\in M_{m,n}(\R)
$$

where $\sigma_1 \ge \dots \ge \sigma_r \gt 0$.

Notation:

Let $p = \min\{m, n\}$ and let $\sigma_m = \dots = \sigma_p = 0$. Then $\sigma_i, \, \forall 1\le i\le p$ is a **singular value** of $A$, and $\sigma_1, \dots, \sigma_p$ are **ordered singular values** of $A$. ALso the first p columns of $V$ are **right singular vector** and the first p columns of $U$ are **left singular vectors**. 

*properties*
1. If $U = [u_1 \dots u_m], V = [v_1 \dots v_n]$, then $\forall 1\le j \le p$,
   
   $$
   A v_j = \sigma_j u_j,\\
   u_j^HA = \sigma_j v_j^H,
   $$

1. The singular values of $A^H$ and $A$ are the same,
   
   $$
    S^\top = S^H = (U^HAV)^H = V^HA^HU
   $$

1. If $A\in M_n(\C)$ Hermitian, then the singular values of $A$ are absolute values of the eigenvalues of $A$,
   
   $$
   \sigma_j = \sqrt{\lambda_j(A^HA)} = |\lambda_j(A)|
   $$

1. If $A\in M_n(\C)$ nonsingular, then $r = p-n$, and the singular values of $A^{-1}$ are
   
   $$
   \frac{1}{\sigma_n} \ge \dots \ge \frac{1}{\sigma_1}
   $$


<!-- S is unique to A. what about U and V-->

Suppose $USV^H = A = \hat{U}S\hat{V}^H$, then

$$
VS^\top SV^H = A^HA = \hat{V}S^\top S \hat{V}^H\\
\Rightarrow (\hat{V}^HV)(S^\top S) = (S^\top S)(\hat{V}V)
$$

Write 

$$
S^\top S = \mu_1 I_{m_1} \oplus \dots \oplus \mu_s I_{m_s} \in M_n(\R)
$$

where $\mu_1 \gt \dots \gt \mu_s$. And $\sum_{i=1}^{s-1} m_i = r$ and $m_j = n-r$.

Let 

$$
C = \hat{V}^HV\\
 = \begin{bmatrix}
    C_{11} &  \dots & C_{1s}\\
    \vdots & & \vdots\\
    C_{s1} & \dots & C_{ss}
 \end{bmatrix}
$$

where $C_{ii} = M_{m_i}(\C), \, \forall 1\le i \le s$. Then

$$
\begin{align}
    CS^\top S& = S^\top S C\\
\begin{bmatrix}
    \mu_1 C_{11} &  \dots & \mu_s C_{1s}\\
    \vdots & & \vdots\\
    \mu_1 C_{s1} & \dots & \mu_s C_{ss}
 \end{bmatrix}
 & = 
 \begin{bmatrix}
    \mu_1 C_{11} &  \dots & \mu_1 C_{1s}\\
    \vdots & & \vdots\\
    \mu_s C_{s1} & \dots & \mu_s C_{ss}
 \end{bmatrix}
\end{align}
$$

so in face $C_{ij} = 0$ if $i\neq j$ and $C = C_{11} \oplus \dots \oplus C_{ss}$. Then $V = \hat{V} C$. Similarly, $U = \hat{U}B$, where $B$ unitary block diagonal with same nonzero partition as $C$.

$$
B = B_{11} \oplus \dots \oplus B_{ss}\\
B_{ii} \in M_{r_i}(\C)\, \forall 1\le i \le s-1\\
B_{ss} \in M_{m-r} (\C)
$$

Now 

$$
USV^H = \hat{U}S\hat{V}^H\\
\Rightarrow \hat{U}^HUS = S\hat{V}^H V\\
\Rightarrow BS = SC
$$

this then implies $B_{ii} = C_{ii}, \, \forall 1\le i\le s-1$. This gives

*proposition*
Given $A \in M_{m,n}(\C)$, if $U^HAV = \hat{U}^HA\hat{V} = S$ where $U, \hat{U} \in M_{m}(\C)$ unitary and $V, \hat{V}\in M_n(\C)$ unitary. And 

$$
S = \begin{bmatrix}
   \sqrt{\mu_1}I_{m_1}\oplus \dots \oplus \sqrt{\mu_{s-1}I_{m_{s-1}}} & 0\\0 & 0
\end{bmatrix}\in M_{m,n}(\R)
$$

where $\mu_1\gt \dots\gt \mu_{s-1}\gt 0$. Then, exists unitary matrix $B, C$ of the forms

$$
B = B_{11}\oplus \dots \oplus B_{s-1, s-1}\oplus B_{ss}\in M_m(\C)\\
C = B_{11}\oplus \dots \oplus B_{s-1, s-1}\oplus C_{ss} \in M_n(\C)
$$

where $B_{ii} \in M_{m_i}(\C) \st U = \hat{U}B, V = \hat{V}C$.
<!-- Not unique -->

*note*
1. If $A\in M_n(\C)$ and all singular values of $A$ are distinct and nonzero, then each right singular vector $v_j$ can only differ by scalar multiple of $e^{\ii \theta}$ for some $\theta \in [0, 2\pi)$.
2. When $A\in M_n(\C)$ and positive semi-definite. Then 
   
   $$
   U^HAV = D^2 = Q^HAQ,
   $$

   so $U = QB, V = QC$. Then, $U = VC^HB$.

3. $A\in M_n(\C)$ positive semi-definite, we have the tools to show that exists unique positive semi-definite $X \in M_n(\C) \st A = X^2$. And $X$ is called the **square root** of $A$: $X = A^{\frac{1}{2}}$. Then we can define for any $A\in M_{m,n}(\C)$ then
   
   $$
   |A| = (A^HA)^{\frac{1}{2}}
   $$

   the **modules** of $A$[^reading_svd]. 

[^reading_svd]: [link](https://math.stackexchange.com/questions/1927845/is-u-v-in-the-svd-of-a-symmetric-positive-semidefinite-matrix).


Courant-Fisher says $p = \min\{m,n\}$ and $\sigma_1 \ge \dots \ge \sigma_p$ ordered singular values for $1\le i\le p$. 

$$
\sigma_i^2 = \max_{\substack{S\subseteq \C^n \text{subspace}\\ \dim(S) = i}} \left( \min_{\substack{x\in S\\ x\neq 0}} \frac{x^HA^HAx}{x^Hx} \right)
$$

$$
\sigma_i = \max_{\substack{S\subseteq \C^n \text{subspace}\\ \dim(S) = i}} \left( \min_{\substack{x\in S\\ x\neq 0}} \frac{\|Ax\|}{\|x\|} \right)
$$

and have similar form from the other form of Courant-Fisher.