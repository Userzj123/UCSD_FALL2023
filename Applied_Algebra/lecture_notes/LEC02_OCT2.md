# Linear Independent
```{prf:definition} Linear Independence
If $x_1, x_2, \dots x_n$ are not linearly dependent, then they are **linearly independent**,

$$
\sum \alpha_i x_i = 0 \Longleftrightarrow \alpha_1 = \alpha_2 = \dots = 0,
$$

which means there are no redundancies in $x_1, x_2, \dots x_n$.

```

*note*
sometimes, consider linear dependence of $\underbrace{\{x_1, x_2, \dots x_n\}}_{\text{multiset}}$. For example, $\begin{Bmatrix}\begin{bmatrix} 1\\0 \end{bmatrix}, \begin{bmatrix} 1\\\alpha \end{bmatrix} \end{Bmatrix}, \; \alpha \rightarrow 0$.


If $X = \span{x_1, x_2, \dots x_n}$ and if $x_1, x_2, \dots x_n$ linear independent, then $x_1, x_2, \dots x_n$ is a **basis** of $X$.

```{note}
Bases are not unique. However, **all bases have the same number of elements**.
```

````{prf:proposition}
Let $\mathcal{X} = \text{span}\{x_1, x_2, \dots x_n\}$ linear independent, then for $k>n$, any choise of $y_1, y_2, \dots, y_n \in \mathcal{X}$ is linear dependent.


```{prf:proof}
**induction & gaussian elimination**

*Initial induction step* n = 1:
If $X = \span{x_1}$, then $y_1, y_2 \in X = \span{x_1}$ are both scalars times $x_1$, which are linear dependent.


*Main induction step*: 
Assume preposition is true for $n = m-1$, then need to show it is also true for $n=m$.

Given $y_1, y_2, \dots, y_k$ in which $k>m$, write each as linear combination of $x_1, x_2, \dots, x_m$,

$$
y_j = \sum_{i=1}^m \alpha_{ji}x_i, \text{for j = } 1, 2, \dots, k.
$$

Choose properly an integer $l$ and do Gaussian eliminations to obtain,

$$
\hat{y_j} = y_j + \mu_j y_1, \text{ for } 2 \le j\le k,
$$

for some $\mu_j$ s.t.

$$
\hat{y_j}\in \span{\series{x}{l-1}, x_{l+1}, \dots, x_m}.
$$

$\hat{y_j}$ has $k-1$ element.
- If $k-1= m$, then $\hat{y_j}$ is linearly independent. However, since $\hat{y_j}$ depends on $y_1$, so that $y_1, \dots, y_n$ are linearly dependent.
- If $k-1>m$, then $\hat{y_j}$ is linearly dependent. Then $y_1, \dots, y_n$ must be linearly dependent.

```
````

*definition*
If $X$ has basis of n elements, then **dimension** of $X$ is n, 

$$
\text{dim}(X) = n.
$$


*margin_note*
we only study finite dimensional case in this class.


How to constitute a basis?
1. Start with a number of linear independent vectors, at least one.
2. If its span is not the whole space, then add a vector that's outside the span. And then repeat the first step.
3. Otherwise, get basis.


## Special form of vector spaces (Inner product spaces)

Vector spaces with an **inner product**,

$$
\langle \cdot, \cdot \rangle : x \times x \rightarrow \mathbb{F},
$$

satisfies 
1. Positive definitive

    $$
    \langle x, x \rangle \ge 0 \text{ and }\langle x, x \rangle =0 \Longleftrightarrow X = 0
    $$

2. Linearization with addition

    $$
    \langle x, y \rangle + \langle z, y \rangle = \langle x+z, y \rangle
    $$

3. Linearization with scalar multiplication

    $$
    \langle \alpha x, y \rangle = \alpha \langle x, y \rangle
    $$

4. Commutativity

    $$
    \langle x, y \rangle = \langle \bar{y}, x \rangle
    $$

*example*
$x=\C^n$ over $\C$, then

 - $$\langle x, y\rangle = y^{H} x = \sum_{j=1}^n \bar{y_j}x_j.$$

*margin*
Hermitian transpose $y^H = \bar{y}^\top$, and $(y^Hx)^H = x^H y$.

- $$\langle x, y\rangle= \sum_{j=1}^n \alpha_j \bar{y_j}x_j.$$

if $X = M_{m, n}$, then

- $$\langle A, B\rangle = \trace(B^H A)$$

### Norm

Can then define **norm**, (measured magnitude/size)
$||x|| = (\langle x, x\rangle)^{(1/2)}$.

Cauchy-schwartz says 

$$
\langle x, y \rangle | \le \|x\|\|y\|,
$$

can define angles between vectors
$$
\arccos{\frac{\langle x, y\rangle}{\|x\|\|y\|}}.
$$

### Orthogonal
We have concept of **orthogonality**,
$$
x, y \text{  is orthogonal if } \langle x, y\rangle = 0.
$$

Also, $\series{x}{n}$ are **orthogonal** if $\langle x_i, x_j\rangle = 0, \forall i\neq j$.

*note*
an orthogonal set of nonzero vectors is linear independent.

*proof*
In order to prove that the set is linear independent, then only trivial solution satisfies $\sum_{i=1}^n \alpha_i x_i = 0$. Thus, we could use the dot product of the set and each vector to obtain the values of $\alpha_j$ are all zero and conclude that the set is linear independent,

$$
\begin{aligned}
    \sum_{i=1}^n \alpha_i x_i &= 0,\\
    \langle x_j, \sum_{i=1}^n \alpha_i x_i\rangle & = 0,\\
    \sum_{i=1}^n \alpha_i \langle x_j, x_i \rangle = \alpha_j \langle x_j, x_j\rangle & = 0,\\
    \alpha_j = 0.
\end{aligned}
$$

### Subspace

$y^\perp = \{y\in X | \langle x, y\rangle = 0, \forall x\in y\}$ is the **orthogonal complement** of subspace $y \subseteq X$.


*example*
$y = \R^2$, $y =\span{\begin{bmatrix} 1\\0 \end{bmatrix}}$, then $\begin{bmatrix} 0 \\ 1\end{bmatrix}\in y^\perp$.