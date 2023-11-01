# Lec04

```{prf:definition}
The function $T: X\rightarrow Y$ is **injective**, or **one-to-one**, if each element of the codomain $Y$ is mapped to by at most one element of the domain $X$, or equivalently, if distinct elements of the domain $X$ map to distinct elements in the codomain $Y$. An injective function is also called an **injection**. Notationally:

$$
\forall x, x' \in X, f(x) = f(x') \Rightarrow x = x'.
$$

The function is $T: X\rightarrow Y$ **surjective**, or **onto**, if each element of the codomain $Y$ is mapped to by at least one element of the domain $X$. That is, the image and the codomain $Y$ of the function are equal. A surjective function is a **surjection**. Notationally:

$$
\forall y \in Y, \exists x \in X \st y = f(x)
$$
```


````{prf:definition} Rank-Nullity Theorem
$\underbrace{\dim(\range( T ))}_{\rank(T)} + \dim(\null(T)) = \dim(X)$


```{prf:proof}
Let $y_1, y_2, \dots, y_m$ be a basis of $\range(T)$, so $\exists z_1, z_2, \dots, z_m \in X$ s.t. $T(z_j) = y_j,\, \forall 1\le j\le m$. Also let $x_1, \dots, x_n$ be a basis of $\null(T)$. Study $x_1, \dots,x_n, z_1, \dots, z_m$,


First, show that these two set are linearly independent,

$$
\begin{aligned}
\sum_{i=1}^n \alpha_i x_i + \sum_{i=1}^m \beta_i z_i &= 0,\\
\sum_{i=1}^n \alpha_i \cancel{T(x_i)} + \sum_{i=1}^m \beta_i T(z_i) &= 0,\\
\sum_{i=1}^m \beta_i y_i &= 0,\\
\beta_i = 0 \text{ since } y_i \text{ are basis of } \range(T),\\
\Rightarrow \sum_{i=1}^n \alpha_i x_i &= 0,\\
\Rightarrow \alpha_i = 0 \text{ since } x_i \text{ are basis of } \null(T).
\end{aligned}
$$

Secondly, show that they are inside $X$. Let $x\subset X$, then we have

$$
\begin{aligned}
    T(x) & =   \sum_{i=1}^m \gamma_i y_i = \sum_{i=1}^m \gamma _iT(z_i)\\
    \Rightarrow T(x) - \sum_{i = 1}^m \gamma_i T(z_i) &= 0\\
    T(x - \sum_{i=1}^m \gamma_i z_i) & = 0\\
    \Rightarrow x - \sum_{i= 1}^m \gamma_i z_i & = \sum_{i=1}^n \mu_i x_i\\
    x &= \sum_{i=1}^m \gamma_i z_i + \sum_{i=1}^n \mu_i x_i\\
    \Rightarrow \dim(X) &= n+m
\end{aligned}
$$
```

````


```{prf:definition}
For $T(x) = Ax$ for $x\in \C^n$, $A\in M_{m, n}(\C)$.

Let $e_1, \dots, e_n$ be the **standard orthogonal basis**: $(e_i)_j = \delta_{ij}$. Then, $T(e_i) = a_i$ is the i-th column of A. Thus, $\range(A) = \span{a_1, \dots, a_n}$, $\rank(A) = \dim(\range(A)) = \dim(\span{a_1, \dots, a_n})$. This is also known as the **column rank** of $A$.

Then, **row rank** is the dimension of the span of the rows of $A$.

```

```{margin}
- $\range(A) = \range(T) = \{Ax|x\in \C^n\}$
- $\null(A) = \null(T) = \{x\in \C^n|Ax=0\}$
```



````{prf:proposition}
The column rank equals to the row rank.

```{prf:proof}

Suppose $A\in M_{m, n}$ has column rank $r$ and row rank $q$. Let $y_1, \dots, y_r$ be a basis of $\range(A)$. Let $B = [y_1, \dots, y_r]$, $A_{m, n} = B_{m, r} C_{r, n}$, so that A is the linear combination of B ($A_i = Bc_i$). Furthermore, $A^\top_{n, m} = C^\top_{n, r} B^\top_{r, m}$, in which columns of $A^\top$ are rows of $A$. 

In this case, the dimension cannot be larger than the basis number(r) $q\le r$. Do same analysis on $A^\top: r\le q$. so $r=q$.

```
````


Let linear transformation $S, T: X\rightarrow Y$, in which $X, Y$ are finite dim vector space.

Study:
1. $S+T$ meaning $(S+T)(x) = S(x) + T(x)$
2. $\alpha T$ meaning $(\alpha T)(x) = \alpha T(x)$


Let $\mathcal{L}(X, Y)$ denote set of all linear transformation form $X$ to $Y$, then $\mathcal{L}(X, Y)$ is a vector space.


Also, $T:X\rightarrow Y$, $S:Y\rightarrow Z$, $T, S$ linear transformation. $S\circ T :X\rightarrow Z$, $(S\circ T)(x) = S(T(x))$, which is a linear transfomation.


## Representations
````{prf:definition}
$B_x = \{x_1, \dots, x_n\}$ a basis of $X$. Then, given $x\in X$,

$$
x = \sum_{i = 1}^n \alpha_i x_i.
$$

Collect coefficients as $\begin{bmatrix}
    \alpha_1\\\vdots\\\alpha_n
\end{bmatrix}\in \mathbb{F}^n$. This we call the **representation of x w.r.t. $B_x$**.


*Notation*: 

$$
\begin{bmatrix}
    \alpha_1\\\vdots\\\alpha_n
\end{bmatrix} = [x]_{B_x}.
$$

```{note}
If $[x]_{B_x} = [y]_{B_x} \Longleftrightarrow x=y$
```
````

Now consider $z_1, \dots, z_n$. 

$$
z_i = \sum_{j=1}^n a_{ij}x_j, \quad \forall 1\le i\le n
$$

```{prf:proposition}
Define $A = (a_{ij}) \in M_{n}(\mathbb{F}) = \begin{bmatrix}
    \alpha_1\\\vdots\\\alpha_n
\end{bmatrix}$, then $z_1, \dots, z_n \in X$ linear independent $\Longleftrightarrow$ $a_1, \dots, a_n \in \mathbb{F}^n$ linear independent.
```