# Lec 14
Start from block triangular form (such as Schur decomposition), 

Easy case first,

$$
T = \begin{bmatrix}
    T_{11} & T_{12} \\ T_{21} & T_{22}
\end{bmatrix}\in M_n(\C), T_{11} \in M_k(\C)
$$

*example*
Scalars instead of bloks

$$
T = \begin{bmatrix}
    t_{11} & t_{12} \\ t_{21} & t_{22}
\end{bmatrix}, 
$$

Let 

$$
W = \begin{bmatrix}
    1 & -z \\ 0 & 1
\end{bmatrix}
$$

Then

$$
WT = \begin{bmatrix}
    t_{11} & t_{12} - z t_{22}\\ 0 & t_{22}
\end{bmatrix}\dots
$$

Note $W^{-1} = \begin{bmatrix} 1 & z \\ 0 & 1\end{bmatrix}$ and $WTW^{-1} = \begin{bmatrix} t_{11} & t_{11}z + t_{12} - zt_{21}\\ 0 & t_{22}\end{bmatrix}$, can find $z = -\frac{t_{12}}{t_{11} - t_{22}}$ to get block diagonal matrix if $t_{11}\neq t_{22}$.

Back to blocks, let $Z \in M_{k, n-k} (\C)$, then

$$
W = \begin{bmatrix} I_{k} & Z \\ 0 & I_{n-k}\end{bmatrix},\\
W^{-1} = \begin{bmatrix} I_{k} & -Z \\ 0 & I_{n-k}\end{bmatrix},
$$

Thus, we could have

$$
W^{-1}TW = \begin{bmatrix}
    T_{11} & T_{11}Z + T_{12} - ZT_{22}\\ 0 & T_{22}
\end{bmatrix}.
$$

Note we want to find $Z$ s.t. 

$$
T_{11}Z + T_{12} - ZT_{22}  = 0 .
$$


Study **Sylvester equation**,

$$
AX - XB = C,
$$

where $A\in M_m(\C), B\in M_n(\C), C\in M_{m, n}(\C), X\in M_{m, n}(\C)$.

In this is the Sylvester operator:

$$
S: M_{m, n}(\C) \longrightarrow M_{m,n}(\C), \text{ for fixed } A, B\\
X \longrightarrow AX-XB
$$

and becomes $S(X) = C$.


If $C\subseteq \range(S)$, then $\forall C\in M_{m, n}(\C)$ then $S$ is 1-1, onto.


$$
\begin{aligned}
    S(X) &= AX - XB\\
    & = AX - XQTQ^H\\
    S(X)Q &= A\underbrace{XQ}_{Y} - \underbrace{XQ}_{Y}T\\
    & = AY-YT
\end{aligned}
$$

$$
\begin{aligned}
S(X) = 0 \Longleftrightarrow AY-YT = 0
\end{aligned}
$$


For 1-1, want

$$
AY-YT = 0 \Longleftrightarrow Y=0
$$

Take a look at the columns of $AY-YT$ when $Y = \begin{bmatrix} y_1 & y_2 & \dots & y_n \end{bmatrix}$, then the j-th column is 

$$
\begin{aligned}
    Ay_j - \sum_{i = 1}^jt_{ij} y_i & = (A - t_{jj}I ) y_j - \sum_{i = 1}^{j-1}t_{ij} y_i
\end{aligned}
$$

For $j = 1$, we have

$$
(A - t_{11}I ) y_1 =0,
$$

If $t_{11} \notin \sigma(A)$, then $y_1 = 0$.

For $j=2$, we have

$$
(A - t_{22}I ) y_2 - \cancel{t_{12}y_1} =0,
$$

If $t_{22}\notin \sigma(A)$, then $y_2=0$.

Continues induction



*Conclusion*
If $\sigma(B)\cap \sigma(A) = \phi$, then $S$ is 1-1 and can find $X$ s.t. $AX - XB = C, \forall \in M_{m, n}(\C)$.



Now if $\lambda $ eigenvalue of $A$ and of $B$ then let $x$ be the corresponding eigenvector for $A$, and $y$ be the corresponding left eigenvector for $B$,

Consider $xy^H \neq 0$, then 

$$
\begin{aligned}
    S(xy^H) & = Axy^H  - xy^H A\\
    & = \lambda xy^H - x\lambda y^H\\
    & = 0
\end{aligned}
$$

and $S$ not 1-1.


*proposition*

For $A\in M_{m}(\C), B\in M_n(\C)$,  

$$
\sigma(A)\cap\sigma(B) = \phi \Longleftrightarrow AX- XB = 0 \text{ if and only if } X = 0 \\
\Longleftrightarrow \forall C\in M_{m, n}(\C), \exists X\in M_{m, n}(\C) \text{ s.t } AX-XB = C
$$

If $\alpha$ eigenvalue of $A$, corresponding eigenvector $x$ and $\beta$ eigenvalue of $B$, correponding eigenvector $y$, so

$$
S(xy^H) = (\alpha - \beta) xy^H
$$

so $(\alpha - \beta, xy^H)$ is an eigenpair of $S$.


In fact, all eigenvalues of $S$ follow this form:

let $(\lambda, X)$ be an eigenpair of $S$, 
  
$$
\begin{aligned}
    S(X) = \lambda X & \Longleftrightarrow AX-XB = \lambda X\\
    & \Longleftrightarrow (A-\lambda I)X - XB = 0, \text{ for } X \neq 0\\
    & \Longleftrightarrow \sigma(A - \lambda I) \cap \sigma(B) \neq \phi\\
    & \Longleftrightarrow \exists \beta \in \sigma(A - \lambda I)\cap \sigma(B)
\end{aligned}
$$

So 
- $\beta \in \sigma(A-\lambda I) \Rightarrow \beta = \alpha - \lambda$ for some $\alpha \in \sigma(A)$
- $\beta \in \sigma(B)$

so $\lambda = \alpha - \beta$.

