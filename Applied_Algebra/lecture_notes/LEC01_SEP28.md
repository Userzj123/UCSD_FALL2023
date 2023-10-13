# preliminaries
Let $\displaystyle A = (a_{ij})\in \underbrace{M_{m,n}(\C)}_{\C^{m, n}}$ be an $m\times n$ matrix with elements in $\C$. Let $x\in \C^n$, then 

$$
(Ax)_i = \sum_{j=1}^n a_{ij}x_j.
$$ 

Alternatively, $A=\begin{bmatrix}a_1 & a_2 & \dots & a_n\end{bmatrix}$, then 

$$
Ax = \sum_{i=1}^n x_i a_i.
$$

Also, if $B=(b_{ij}) \in M_{n, r}(\C)$, then 

$$
C = AB\Longleftrightarrow c_{ij} = \sum_{k=1}^n a_{ik}b_{kj}.
$$

But also 

$$
A\begin{bmatrix}b_1 & b_2 & \dots & b_r\end{bmatrix} = \begin{bmatrix}Ab_1 & Ab_2 & \dots & Ab_r\end{bmatrix}.
$$

Also if $B = \begin{bmatrix}d_1\\ d_2 \\ \vdots \\d_n\end{bmatrix}$, then 

$$
AB = \begin{bmatrix}a_{11}d_1+\dots + a_{1n}d_n \\ \vdots \\ a_{m1}d_1 + \dots + a_{mn}d_n\end{bmatrix}.
$$

```{prf:definition} Kronecker delta
$$
\delta_{ij} = \begin{cases}1, & \if i = j\\ 0, & \if i \neq j,\end{cases}
$$

which is the elements of *identity matrix*.
```

## Vector spaces
```{prf:definition} Scalar field
Underlying a vector space is its *field*, or set of scalars. In this course, we focus on the real numbers $\R$ and complex numbers$\C$. When the field is unspecified, we denote it by the symbol $\F$. To qualify as a field, a set must be 
- closed under two binary operations: "addition" and "multiplication"
      
    $$a+b \text{ and } ab \text{ are still in the scalar field if } a, b \text{ are}.$$

- associative and commutative
    
    $$
    (a+b)+c = a+(b+c)\\
    ac = ca
    $$

- existence of an identity element in the set & inverses for all elements except additive identity under multiplication

    $$
    a+0 = a\\
    a\cdot1 = a\\
    ab = 1, \;\for ab\neq0\\
    a+c = 0
    $$

- multiplication must be distributive over addition

    $$
    a(c+d) = ac+ad
    $$
```

````{prf:definition} Vector Space

Vector space over s scalar field $\F$ contains elements (vectors) with generations of "addition" and "scalar multiplication"
- associative & commutative laws for addition
- distributive law for scalar multiplication and vector addition

    $$
    a(x+y) = ax + ay
    $$

- 0 identity element and inverses under addition; 1 identity element in scalar multiplication
- Compatibility between scalar and field multiplication

    $$
    (ab)x = a(bx)
    $$

- closed under add and scalar multiplication

```{prf:example}
$\{\begin{bmatrix} 1\\0 \end{bmatrix}, \begin{bmatrix} 0\\0 \end{bmatrix}, \begin{bmatrix} -1\\0 \end{bmatrix} \}$ not closed under scalar multiplication over $\R$. Thus, it is not a vector space.
```

```{prf:example}
Vector Spaces
- $\R^n $ over $\R$ (not $\C$)
- $\C^n$ over $\R$ or $\C$
- $M_{m,n}(\F)$ over $\F$, $M_n(\F) = M_{n,n}(\F)$ over $\F$
- $P_n(\F)$ polynomials of deg $\le n$ with coefficients in $\F$.
```
````

````{prf:definition} Subspace
A *subspace* $S\subseteq X$ (vector space) is a vector space that inhabits its operations and scalar field from $X$. Just proved closed under operations.

```{prf:example}
- $x\in \F^2, \{\alpha x| \alpha\in \F\} \subseteq \F^2$
- Symmetric matrix in $M_n$
- Upper triangular matrix in $M_n$
- $P_m \subseteq P_n, m\le n$
```
````
### Tools
A *finite linear combination* of vectors $\series{x}{n}\in X$ looks like $\sum_{i=1}^n \alpha_i x_i$, so with vectors $x_1, \dots, x_n \in X$, define $\span{\series{x}{n}} = \{\sum_{i=1}^n \alpha_i x_i|\series{\alpha}{n}\in \F\}$ then $\span{\series{x}{n}}\subseteq X$ is a subspace with finite linear combinations. Furthermore, $X = \span{x|x\in X}$, but there may be a more "efficient" span.

````{prf:definition} linear dependence
We call $\series{x}{n}$ linearly dependent if $\exists \series{\alpha}{n}\in \F$ not all zero, s.t. 

$$
\sum_{i=1}^n \alpha_i x_i = 0.
$$

If linearly dependent, can have one as linear combination of others, e.g. $x_1 = -2x_2 -3x_3.$ Suppose $x_k$ could be expressed as the linear combination of others, then the span of the series could be abbreviated,

$$
\span{\series{x}{n}} = \span{\series{x}{k-1}, x_{k+1}, \dots, x_n}.
$$


```{note}
if $\series{x}{n}$ has one of them as 0 then it's linearly dependent.
```
````