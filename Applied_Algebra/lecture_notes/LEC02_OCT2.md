# Linear Independent
If $x_1, x_2, \dots x_n$ are not linearly dependent, then they are *linearly independent*.

$$
\sum \alpha_i x_i = 0 \Longleftrightarrow \alpha_1 = \alpha_2 = \dots = 0,
$$

which means there are no redundancies in $x_1, x_2, \dots x_n$.

````{admonition} Multiset
sometimes, consider linear dependence of $\{x_1, x_2, \dots x_n\}$.

```{prf:example}
$$
\begin{Bmatrix}
\begin{bmatrix}
    1\\0
\end{bmatrix},
\begin{bmatrix}
    1\\\alpha
\end{bmatrix}
\end{Bmatrix}
, \quad \alpha \rightarrow 0
$$
```
````

If $\mathcal{X} = \text{span}\{x_1, x_2, \dots x_n\}$ and if $x_1, x_2, \dots x_n$ linear independent, then $x_1, x_2, \dots x_n$ is a basis of $\mathcal{X}$.

````{note}
Bases are not unique. However, **all bases have the same number of elements**.

```{prf:proposition}
Let $\mathcal{X} = \text{span}\{x_1, x_2, \dots x_n\}$ linear independent, then for $k>n$, any choise of $y_1, y_2, \dots, y_n \in \mathcal{X}$ is linear dependent.
```


```{prf:proof}
**induction & gaussian elimination**
Induction on n

*Initial induction step* n = 1:
If $\mathcal{X} = \text{span}\{x_1\}$, then $y_1, y_2 \in \mathcal{X} = \text{span}\{x_1\}$ are both scalars times $x_1$, which are linear dependent.


*Main induction step*: 
Assume true for $n = m-1$, let's show true for $n=m$.

Given $y_1, y_2, \dots, y_k$ in which $k>m$, write each as linear combination of $x_1, x_2, \dots, x_m$,

$$
y_j = \sum_{i=1}^m \alpha_{ji}x_i, \text{for j = } 1, 2, \dots, k.
$$

Choose properly an $l$ and do gaussian eliminations to obtain,




```
````

```{prf:definition}
If $\mathcal{X}$ has basis of n elements, then dimension of $\mathcal{X}$ is n, $\text{dim}(\mathcal{X}) = n$.
```

````{margin}
```{note}
we only study finite dimensional case in this class.
```
```````


How to constitute a basis?
1. Start with a number of linear independent vectors, at least one.
2. If its span is not the whole space, then add a vector that's outside the span. And then repeat the first step.
3. Otherwise, get basis.


## Special form of vector spaces (Inner product spaces)

Vector spaces with an *inner product*,
$$
\langle \cdot, \cdot \rangle : \mathcal{X}*\mathcal{X} \rightarrow \mathbb{F},
$$

satisfies 
1. Positive definitive
2. Linearization with addition
3. Linearization with scalar multiplication
4. Commutativity

Example:
$x=\C^n$ over $\C$, then
$\langle x, y\rangle = - y^{H} x$


Can then define *norm*, (magnitude / size)
$||x|| = (\langle x, x\rangle)^{(1/2)}$.

Cauchy-schwartz says 

$$
\langle x, y \rangle | \le \|x\|\|y\|,
$$

can define angles between vectors
$$
\arccos{(\frac{}{})}
$$

### Orthogonal
We have concept of *orthogonality*,
$$
x, y \text{  is orthogonal if } \langle x, y\rangle = 0.
$$

### Subspace

$y \le \mathcal{X}$ subspace, 


**orthogonal complement of y** (subspace)