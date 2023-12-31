# LEC05 Oct9
*recap*
$B_X = \{x_1, \dots, x_n\} \subseteq X$ basis, $x=\sum_{i=1}^\infty \alpha_i x_i$, $[x]_{B_X} = \begin{bmatrix}
    \alpha_1\\\vdots\\\alpha_n.
\end{bmatrix}$

```{prf:proof}
Let $f:X\rightarrow \F^n$ ($x\rightarrow [x]_{B_X}$), then $f$ is **invertible** (injective because all coefficient are unique and surjective) and **linear transformation**,

$$
\begin{aligned}
    x+y & = \sum \alpha_i x_i + \sum \beta_i x_i,\\
    & = \sum (\alpha_i + \beta_i )x_i,\\
    \text{or } f(\alpha x +\beta y) &= \alpha f(x) + \beta f(y),
\end{aligned}
$$

then f is an **isomorphism** $X$ and $\F^n$ are **isomorphic**.

Thus, $X$ and $\F^n$ identical in linear algebra sense, e.g., 
- $z_1, \dots, z_k \in X$ linear independent $\Longleftrightarrow$ $[z_1]_{B_X}, \dots, [z_k]_{B_X}$ linear independent
- $\dim(\span{z_1, \dots, z_k}) = \dim(\span{[z_1]_{B_X}, \dots, [z_k]_{B_X}})$
```



## Representation of linear transformation

```{prf:definition} **Linear transformation**
$T:X\rightarrow Y$, $X, Y$ are vector spaces. Let $B_X = \{x_1, \dots, x_n\}$ be basis of X, $B_Y = \{y_1, \dots, y_m\}$ be basis of Y. Then,

$$
T(x_j) = \sum_{i=1}^m a_{ij} y_i, \forall i\le j\le n.
$$
```

Let $A\subseteq M_{m, n}(\F)$ with $A = (a_{ij})$. (j-th column of $A$ is $[T(x_j)]_{B_Y}$.)

Let $x\in X$, so $[x]_{B_X} = \begin{bmatrix}\alpha_1\\ \vdots\\\alpha_n\end{bmatrix}$, then 

$$
\begin{aligned}
    \displaystyle T(x) &= \sum_{j=1}^n \alpha_j T(x_j)\\
    & = \sum_{j=1}^n \alpha_j \sum_{i=1}^m a_{ij} y_i\\
    & = \sum_{i=1}^m (A[x]_{B_X})_i y_i
\end{aligned}
$$

so $[T(x)]_{B_Y} = A[x]_{B_X}$.

Also, suppose $T$ is a transformation satisfying $[T(x)]_{B_Y} = A[x]_{B_X}$, then $T$ is **linear**.


```{prf:proposition}
$T:X\rightarrow Y$ is linear transformation $\Longleftrightarrow$ $[T(x)]_{B_Y} = A[x]_{B_X}$
```

```{prf:definition}
we say $A$ represents the linear transformation $T$ from basis $B_X \to B_Y$

*notation*
we use $_{B_Y}[T]_{B_X}= A$, so 

$$
[T(x)]_{B_Y} = _{B_Y}[T]_{B_X}[x]_{B_X}.
$$
```

Let $f:\mathcal{L}(X, Y) \rightarrow M_{m, n} (\F)$, ($T \rightarrow _{B_Y}[T]_{B_X}$), then 
- $f$ is an isomorphism,
- $\mathcal{L}(X,Y)$ and $M_{m, n}(\F)$ are isomorphic. 

Now we just start to study matrix for Matrix Analysis 202A.


```{prf:example}
- $\rank(T) = \rank(_{B_Y}[T]_{B_X})$
- $_{B_Z}[S\circ T]_{B_X} = _{B_Z}[S]_{B_Y} {_{B_Y}}[T]_{B_X}$ unless $S\in \mathcal{L}(Y, Z)$
- $T$ is invertible $\Longleftrightarrow$ $_{B_Y}[T]_{B_X}$ is invertible.
```



Consider $\mathcal{L}(X, X)$ (isomorphic to $M_n(\F)$).
Consider $B_1, B_2$ basis of $X$.

$T\in \mathcal{L}(X,X)$ then, $[T(x)]_{B_2} = \LT{T}{B_2}{B_1} [x]_{B_1}$. Let $T = I$ identity matrix, then $[x]_{B_2} = \LT{I}{B_2}{B_1}[x]_{B_1}$. In fact, 

$$
\LT{T}{B_2}{B_1}^{-1} = \LT{T}{B_1}{B_2}.
$$

````{prf:proposition}
Let $A\in M_n(\F)$ with linear independent columns, then for given basis $B_2$ of $X$, then there exists $B_1$ basis of $X$, s.t. $_{B_2}[I]_{B_1} = A$.

```{prf:proof}
Use $A$ as coefficients of basis. Suppose $B_2 = \{z_1, \dots, z_n\}$. Then, let $x_1, \dots, x_n$ satisfy,

$$
x_j = \sum_{i=1}^n a_{ij} z_i, \forall 1\le j\le n.
$$

Since $[x_j]_{B_2}$ is j-th column of $A$, then $[x_i]_{B_2}, \dots, [x_n]_{B_2}$ are linear independent. Then, $x_1, \dots, x_n$ are linear independent and a basis of $X$, denoted as $B_1 = \{x_1, \dots, x_n\}$.

Now, $\underbrace{[x_j]_{B_2}}_{\text{j-th column of }A} = _{B_2}[I]_{B_1} [x_j]_{B_1} = _{B_2}[I]_{B_1} e_j = $ j-th column of $_{B_2}[I]_{B_1} $, so 

$$
_{B_2}[I]_{B_1} = A.
$$
```
````

```{prf:definition}
Multiple definition of $A$ in $\mathbb{F}$ **non-singular**:
- $A$ is invertible
- $A$ has linear independent columns
- $A$ has linear independent basis
- $\dim{A}\neq 0$
- $\null{A} = \{0\}$
- Given $b\in\F^{n}, Ax=b$ has a unique solutions.
- $0$ is not a eigenvalue of $A$.
```


$T\in\mathcal{L}(X, X)$, so that

$$
\begin{aligned}
    _{B_2}[T]_{B_2}[x]_{B_2} &= [T(x)]_{B_2}\\
    & = [(I\circ T)(x)]_{B_2}\\
    & = _{B_2}[I]_{B_1} [T(x)]_{B_1}\\
    & = _{B_2}[I]_{B_1}{_{B_1}}[T]_{B_1}[x]_{B_1}\\
    & = _{B_2}[I]_{B_1}{_{B_1}}[T]_{B_1} {_{B_1}}[I]_{B_2}[x]_{B_2},
\end{aligned}
$$

so $_{B_2}[I]_{B_1}{_{B_1}}[T]_{B_1} {_{B_1}}[I]_{B_2} = _{B_2}[T]_{B_2}$, which is the same as $ _{B_2}[T]_{B_2} = S^{-1} {_{B_1}}[T]_{B_1} S$. 


```{prf:definition}
$A$ & $B$ **singular** if $\exists$ invertible $S$ s.t. $B = S^{-1}AS$.
```