# Lec03
```{prf:proposition}
Given $x_1, x_2, \dots, x_n$ linear independence in inner product space, then $\exists\, y_1, y_2, \dots, y_n$ orthogonal s.t.
1. span $\{y_1, y_2, \dots, y_n\}$ = span $\{x_1, x_2, \dots, x_n\}$
2. $y_k$ are unique up to const multiple for each $1\le k\le n$
```

```{prf:proof}

Induction on n
1. Initial induction step n=1

    $y_1 \in \text{span} \{x_1\}\setminus\{0\}$ works
2. Main induction step: if statement holds for $n = m-1$, show for $n=m$.

    Already have valid: $y_1, y_2, \dots, y_{m-1}$

    Valid $y_m$ if and only if 
    
    $$
    x_m = \sum_{j=1}^m \alpha_j y_j
    $$

    where 

    $$
    \langle x_m, y_j\rangle = \alpha_j \langle y_j, y_j\rangle
    $$

    because of orthogonality.

    $$
    \alpha_m y_m = x_m - \sum_{j = 1}^{m-1} \alpha_j y_j
    $$

    make sure $\alpha_m \neq 0$ since otherwise $x_m \in \text{span}\{y_1, y_2, \dots, y_{m-1}\} = \text{span}\{x_1, x_2, \dots, x_{m-1}\}$, so $y_m$ is constuct multiple of $x_m - \sum_{j=1}^{m}\alpha_j y_j$, which is known as **Gram-Schmidt** for const multiple chosen as 1,

    $$
    y_1 = x_1\\
    y_k = x_k - \sum_{j=1}^{k-1}\frac{\langle x_k, y_j\rangle}{\langle y_j, y_j\rangle} y_j \text{,  for } k>1
    $$

    Note can also create orthogonal set by normalizing,

    $$
    \tilde{y_k} = \frac{y_k}{\|y_k\|}
    $$

    Suppose vector space is $\C^m$ with **Euclidean inner product** $\langle x, y\rangle = y^H x = y^*x$. Let $A = [x_1, x_2, \dots, x_n] \in M_{m, n}(\C)$


    Then can get $B \in M_{m, n}(\C)$ with $B^H B$ diagonal with nonzero diagonal elements and upper triangular $\R\in M_n(\C)$ s.t.,

    $$
    A = BR \Longleftrightarrow \begin{bmatrix} x_1 & \dots & x_n \end{bmatrix} = \begin{bmatrix} y_1 & \dots & y_n \end{bmatrix} \begin{bmatrix}
        x & x &\dots & x & x\\
         & x &\dots & x & x\\
         &  &\ddots &   & \\
         & & & x & x\\
         & & & & x
    \end{bmatrix}.
    $$

```



subspace $Z \subseteq X$, $X \Rightarrow$ vector space, then $X = Z \oplus Z^\perp$ where $V = V_1\oplus V_2$ means 
1. $V_1 \cap V_2 = \{0\}$ 
2. $V= V_1 + V_2 = \{x+y |x\in V_1, y\in V_2\}$.

```{prf:example}
$Z$ has basis $x_1, x_2, \dots, x_n$, and extend it to $x_1, x_2, \dots, x_n, x_{n+1}, \dots, x_r$ where $\text{dim}(X)$ = r. Proposition says can have instead $\underbrace{z_1, z_2, \dots, z_n}_{\span{Z}}, \underbrace{z_{n+1}, \dots, z_r}_{\span{Z^\perp}}$ orthogonal and $\dim(X) = \dim(Z) + \dim(Z^\perp)$.

In terms of matrices, extend the basis as $C = \begin{bmatrix} \underbrace{y_1, y_2, \dots, y_n}_{B}, \underbrace{y_{n+1}, \dots, y_r}_{\tilde{B}}\end{bmatrix}$. ($C^HC=$ diagonal matrix with positive diagonal entries.) Then, we could have,

$$
A = C\begin{bmatrix} R \\ 0 \end{bmatrix} \Longleftrightarrow \begin{bmatrix} B & \tilde{B} \end{bmatrix} \begin{bmatrix} R \\ 0 \end{bmatrix} = BR
$$
```


## Linear transformation of vector spaces

```{prf:definition} **Mapping**
$T:X\rightarrow Y$ ($x \rightarrow T(x)$), where $X$ is the **domain** of the map and $Y$ is the **codomain**.

- $\range(T) = T(x) = \{T(x) | x\in X\}$ is the **range** of $T$
- For linear transformation (if the range is the vector spaces), **rank** of $T$ is denoted as $\rank(T) = \dim(\range(T))$
- $\null(T)$ is the **null space** of $T$ defined as kernel $\{x|T(x)=0\}$
```

```{prf:property}
For $X, Y$ as vector spaces, linear transformations also satisfy
- $T(\alpha x) = \alpha T(x), \forall x\in X, \alpha \in \mathbb{F}$,
- $T(x+y) = T(x) + T(y), \forall x, y \in X$.

Can instead show as 

$$
T(\alpha x + \beta y) = \alpha T(x) + \beta T(y), \forall \alpha, \beta \in \F, x, y \in X.
$$

Note $T(0) = 0$.
```

```{prf:example}
1. $T:\C^n \rightarrow \C^m$ for fixed $A= M_{m, n}(\C)$,

    $$
    x \rightarrow Ax,
    $$

2. $T: M_n(\R) \rightarrow M_n(\R)$,

    $$
    C \rightarrow \frac{C+C^\top}{2},
    $$

3. **sylvester operator** $T:M_{m, n} \rightarrow M_{m,n}$ with fixed $A\in M_m, B\in M_n$ 

    $$
    C\rightarrow AC-CB,
    $$

4. **Lyapunov operator** $T:M_m \rightarrow M_n$ with fixed $A\in M_n$,

    $$
    C \rightarrow AC - CA^\top.
    $$
```

Linear transformation is completely determined by what it does to basis element. For example, given basis

$$
x = \sum_{i = 1}^m \alpha_i x_i,
$$

then you can obtain the result by linear combination,

$$
T(x) = \sum_{i=1}^m \alpha T(x_i).
$$

And the range of $T$ is a subspace of $Y$, 

$$
\range(T) = \span{T(x_1), \dots, T(x_n)}.
$$

