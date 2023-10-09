*Proposition*:
Given $x_1, x_2, \dots, x_n$ linear independence in inner product space, then $\exists\, y_1, y_2, \dots, y_n$ orthogonal s.t.
1. span $\{y_1, y_2, \dots, y_n\}$ = span $\{x_1, x_2, \dots, x_n\}$
2. $y_k$ are unique up to const multiple the for each $1\le k\le n$

*Proof*
Induction on n
1. Initial induction step n=1

    $y_1 \in \text{span} \{x_1\}\setminus\{0\}$ works
2. Main induction step

    Already have valid: $y_1, y_2, \dots, y_{m-1}$

    Valid $y_m$ if and only if 
    
    $$
    x_m = \sum \alpha_j y_j
    $$

    where 

    $$
    \langle x_m, y_j\rangle = \alpha_j \langle y_j, y_j\rangle
    $$

    because of orthogonality.

    $$
    \alpha_m y_m = x_m - \sum_{j = 1}^{m-1} \alpha_j y_j
    $$

    make sure $\alpha_m \neq 0$ since otherwise $x_m \in \text{span}\{y_1, y_2, \dots, y_{m-1}\} = \text{span}\{x_1, x_2, \dots, x_{m-1}\}$, so you constuct multiple of 

    $$
    x_m - \sum_{j=1}^{m}\alpha_j y_j
    $$

    Known as Gran-Schiwilt for const multiple chosen as 1.

    $$
    y_1 = x_1\\
    y_k = x_k - \sum_{j=1}^{k-1}\frac{\langle x_k, y_j\rangle}{\langle y_j, y_j\rangle} y_j \text{,  for } k>1
    $$

    Note can also create orthogonal set by normalizing,

    $$
    \tilde{y_k} = \frac{y_k}{\|y_k\|}
    $$

    Suppose vector space is $\C^m$ with Euclidien inner product $\langle x, y\rangle = y^H x$. Let $A = [x_1, x_2, \dots, x_n] \in M_{m, n}(\C)$


    Then can get $B \in M_{m, n}(\C)$




*Consequence*
$Z \subseteq X$ subspace, X -> vector space, then $X = Z \oplus Z^\perp$ where $V = V_1\oplus V_2$ means 1. $V_1 \cap V_2 = \{0\}$ 2. $V= V_1 + V_2 = \{x+y |x\in V_1, y\in V_2\}$.

e.g.

$Z \leftarrow $ basis $x_1, x_2, \dots, x_n$, and extend it to $x_1, x_2, \dots, x_n, x_{n+1}, \dots, x_r$ where $\text{dim}(X)$ = r. Proposition says can have instead $z_1, z_2, \dots, z_n, z_{n+1}, \dots, z_r$




In terms of matrices



## Linear transformation of vector spaces
**Mapping**
$T:X\rightarrow Y$ ($x \rightarrow T(x)$), where $X$ is the domain of the map and $Y$ is the codomain.

- $range(T) = T(x) = \{T(x) | x\in X\}$ is the range of $T$
- For linear transformation (if the range is the vector spaces), $rank(T) = dim(range(T))$
- $null(T)$ is the *null space* of $T$ defined as kernel $\{x|T(x)=0\}$


### Linear Transformation
also satisfy
- $T(\alpha x) = \alpha T(x), \forall x\in X, \alpha \in \mathbb{F}$ 
- $T(x+y) = T(x) + T(y), \forall x, y \in X$

For $X, Y$ vector spaces.

Can instead showed as 

$$
T(\alpha x + \beta y) = 
$$

Note $T(0) = 0$.


*Example*
1. $T:\C^n \rightarrow \C^m$ for fixed $A= M_{m, n}(\C)$
1. $T:$
2. $T:M_{m, n} \rightarrow M_{m,n}$ with fixed $$
3. $T:M_m \rightarrow M_n$ with fixed $A\in M_n$


Linear transformation is completely determined by what it does to basis element.

$$
x = \sum_{i = 1}^m \alpha_i x_i
$$

then you can obtain the result by linear combination,

$$
T(x) = \sum_{i=1}^m \alpha T(x_i)
$$

