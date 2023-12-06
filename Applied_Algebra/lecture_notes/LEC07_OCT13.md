---
header-includes:
- \usepackage{cancel}
---
# Lec07
## 1.1 The eigenvalue-eigenvector equation

```{prf:definition}
$(\lambda, x)$ is a right or left eigenpair if $Ax=\lambda x, x\neq 0$ or $x^HA = \lambda x^H, x\neq 0$ respectively.
```

```{prf:definition} Eigenspace
Given eigenvalues $\lambda$ of $A$, we have left eigenspace $\null(A^H-\lambda^H I)$ and right eigenspace $\null(A-\lambda I)$. 
```

The left and right eigenspaces are generally not the same, but they have the same dimensions since $\rank(A-\lambda I) = \rank(A^H - \lambda^H I)$ and rank-nullity.

Also $S^{-1}AS = \Lambda \Longleftrightarrow AS = S\Lambda$, if $\Lambda$ diagonal, then $S$ is the eigenvectors of columns.

On the other hand, we could have $S^{-1}AS = \Lambda \Longleftrightarrow S^{-1}A = \Lambda S^{-1}$. In this case, if $S^{-1} = \begin{bmatrix} S_1 & \dots & S_n \end{bmatrix}^H$, then $S^H_j A = \lambda_j S_j^H $, which is the left eigenpair.

```{margin}
If the matrix is orthogonal, then its transpose and inverse are equal. [^orthogonal_matrix]
```

[^orthogonal_matrix]: [orthogonal matrix](https://byjus.com/maths/orthogonal-matrix/#:~:text=If%20the%20matrix%20is%20orthogonal,transpose%20and%20inverse%20are%20equal.)

Also, $x\neq 0$ is an eigenvector i.f.f. $A \cdot\span{x}\subseteq \span{x}$ (follow from $Ax=\lambda x$).

```{prf:proposition}
y is a left eigenvector i.f.f. $y\neq0$ and $A \cdot\span{y}^\perp\subseteq \span{y}^\perp$.
```

```{margin}
$\perp$ means **Euclidean inner product**
``` 

```{prf:proof}
($\Rightarrow$)
If $y$ is left eigenvector then $A \cdot \span{y}^\perp = \{Az|y^H z = 0\}$ and $y^H A z = \lambda y^Hz, \forall z\in \C^n$,

so 

$$
\{Az|y^Hz=0\}\subseteq \{Az|y^HAz=0\}\subseteq \{w|y^Hw = 0\} = \span{y}^\perp.
$$

($\Leftarrow$) If $A \cdot \span{y}^\perp \subseteq \span{y}^\perp$. Let $z\in \C^n$, then 

$$
\begin{aligned}
z&\in \underbrace{\span{y} \oplus \span{y}^\perp}_{\C^n},\\
\Longleftrightarrow z & = \alpha y + w \text{ when } w \in \span{y}^\perp.
\end{aligned}
$$

So 

$$
y^HAz = y^HA(\alpha y+w) = \alpha y^H A y +\cancel{ y^H \underbrace{Aw}_{\in \span{y}^\perp}}
$$

$$
y^Hz = y^H(\alpha y+w) = \alpha y^H y + \cancel{y^H w}.
$$ (eq:yHz)

Together, we could obtain that,

$$
y^HAz = \alpha y^HAy = \alpha \beta y^H y = \beta y^H z.
$$

Thus, y is a left eigenvector.
```


## The characteristic polynomial and algebraic multiplicity
Construct a polynomial $P_A(\alpha) = \det(A-\alpha I)$, which equal to 0 i.f.f. $\alpha$ is eigenvalue of $A$. So eigenvalues are roots of $P_A$.

Fundamental theorem of algebra says that 

$$
P_A (\alpha) = \beta(a\alpha-\lambda_1)^{m_1}\dots ( \alpha - \lambda_k)^{m_k},
$$

where $\lambda_i = \lambda_j \Longleftrightarrow i=j$. Degree of the polynomial $P_A$ is n. Thus, $m_1+\dots+m_k = n$.

```{prf:definition}
$\lambda_1, \dots, \lambda_k$ are called the **distinct eigenvalues** of $A$.
```

````{prf:definition}
$am(\lambda_i)=m_i$ is called the **algebraic multiplicity** of eigenvalue $\lambda_i$ of $A$.


```{prf:example}
$A = \begin{bmatrix}2 & 0 \\ 0 & 2\end{bmatrix}$, then the polynomial is $P_A(\alpha) = (2-\alpha)^2$. Thus, $\lambda = 2$ is a eigenvalue with $am(\lambda)=2$.


then we can say $A\in M_n(\C)$ has n eigenvalues counting algebra multiplicity.
```
````


````{prf:definition}
Let $\sigma(A) = \{\lambda | P_A(\lambda) = 0\}$ (multiset) be the **spectrum** of $A$.

```{prf:example}
$A = \begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix}$, then $\sigma(A)= \{2, 2\}$.
```
````


Left and Right eigenvalues have the same algebra multiplicity, since

$$
P_A(\alpha^H) = \det(A^H - \alpha^H I) = \overline{\det(A-\alpha I)} = \overline{P_A(\alpha).}
$$

````{prf:definition}
We call $\lambda \in \sigma(A)$ a **simple eigenvalue** if $am(\lambda)=1$. If every eigenvalue of $A$ is simple then we say $A$ has **distinct eigenvalues**. Otherwise at least one eigenvalue is not simple. In this case, we say $A$ has **multiple eigenvalues**.
````

```{note}
$A$ and $S^{-1}AS$ have the same eigenvalues with the same algebraic multiplicity. $\sigma(A) = \sigma(S^{-1}AS)$.

$$\begin{aligned}
    P_{S^{-1}AS}(\alpha) &= \det(S^{-1}AS - \alpha I)\\ 
    & = \det(S^{-1}(A-\alpha I)S)\\
    & = \cancel{\det(S^{-1})} \underbrace{\det(A-\alpha I) }_{P_A(\alpha)}\cancel{\det(S)}
\end{aligned}$$
```

Furthermore, 

$$
(\lambda, x) \text{ eigenpair } \Longleftrightarrow (\lambda, S^{-1}x) \text{ eigenpair of } S^{-1}AS.
$$

```{prf:proposition}
$A\in M_n(\C)$, then 

$$
\trace(A) = \sum_{i=1}^n a_{ii} = \sum_{\lambda \in \sigma(A)} \lambda,
$$

and $\displaystyle\det{A} = \prod_{\lambda \in \sigma(A)} \lambda$ .
```

```{prf:proof}
for $\trace(A)$, 

$$
\begin{aligned}
    P_A(\alpha) & =  \det(A-\alpha I),\\
    & = \prod_{i=1}^n (a_ii - \alpha + \mathcal{O}(\alpha^{n-2})),\\
    & = (-1)^n \alpha^n - (-1)^n \sum_{i=1}^n a_{ii}\alpha^{n-1} + \mathcal{O}(\alpha^{n-2}).
    \end{aligned}
$$

On the other hand, the polynomial satisfies,

$$
\begin{aligned}
    P_A(\alpha) &= (\lambda_1 - \alpha)\dots (\lambda_n -\alpha),\\
    & = (-1)^n \alpha^n - (-1)^n \sum_{i=1}^n\lambda_i \alpha^{n-1} + \mathcal{O}(\alpha^{n-2}).
\end{aligned}
$$

In order to match these two expression, so that we could have

$$
\sum_{i=1}^n\lambda_i = \sum_{i=1}^n a_{ii}.
$$
```