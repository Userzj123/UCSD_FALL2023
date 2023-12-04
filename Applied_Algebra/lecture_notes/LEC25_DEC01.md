# Lec 25

*proposition* Let $V$ finite dimension vector space with basis $B$ and norm $\|\cdot\|_2$. Then given norm $\|\cdot \|_2, \|\cdot\|$ and $\|\cdot\|_2$ are called **equivalent**,

$$
\exists c_1, c_2 \gt 0, c_1, c_2  \in \R \st c_1\|x\|_2 \le \|x\| \le c_2 \|x\|_2, \, \forall x \in V.
$$


*lemma*
The unit ball centered at the origin of 

$$
B_1(0) = \{x \in V | \|x\|_2=1\}
$$

is compact.

*proof*
Consider

$$
c_1 = \min_{\|z\|_2 = 1} \|z\| \\
c_2 = \max_{\|z\|_2 = 1} \|z\|
$$


Then, 

$$
\begin{cases}
    c_1 = \min_{z\neq 0} \frac{\|z\|}{\|z\|_2} \le \frac{\|x\|}{\|x\|_2}, \forall x\neq 0\\
    c_2 = \max_{z\neq 0} \frac{\|z\|}{\|z\|_2} \gt \frac{\|x\|}{\|x\|_2}, \forall x\neq 0
\end{cases}
\Rightarrow
\begin{cases}
    \|x\| \ge c_1 \|x\|_2\\
    \|x\|\le c_2 \|x\|_2
\end{cases}
$$

So the inequality are **sharp** (equality for some $x$).

*corollary*

A norm $\|\cdot \|$ of a finite dimension vector space is a continuous function under any metric that comes from a norm.


*Norm Equivalence*
Given norms $\|\cdot\|, \|\cdot\|_2$in a finite dimensional vector space $V$, then $\exists c_1, c_2\gt 0$ real such that 

$$
c_1\|x\|'\le \|x\|\le c_2 \|x\|', \, \forall x\in V.
$$

*example*
In $\C^n$, find $c_1, c_2$ for norms $\|\cdot\|_\infty, \|\cdot\|_p$

$$
\|x\|_\infty = \max_{1\le i \le n} |x_i| =  |x_k|, \text{ for some } 1\le k \le n
$$

Then 

$$
\begin{align}
    \|x\|_p &= \left( \sum_{i=1}^n |x_i|^p\right)^{\frac{1}{p}}\\
    & = (n|x_k|^p)^{\frac{1}{p}}\\
    & = n ^{\frac{1}{p}} |x_k|\\
    & = n^{\frac{1}{p}} \|x\|_\infty
\end{align}
$$

On the other hand,

$$
\begin{align}
    \|x\|_\infty = |x_k| \le \left( |x_k|^p + \sum_{\substack{i=1\\ i\neq k}}^n |x_i|^p\right)^{\frac{1}{p}} = \|x\|_p
\end{align}
$$


Thus, 

$$
1 \|x\|_infty  \le \|x\|_p \le n^{\frac{1}{p}}\|x\|_\infty
$$

Note $p \rightarrow \infty, n^{\frac{1}{p}}\rightarrow 1$, so 

$$
\lim_{p \rightarrow \infty } \|x\|_p = \|x\|_\infty.
$$


Note:
$\|\cdot \|$ equivalent to $\|\cdot \|'\Rightarrow \|\cdot \|^\prime $ equivalent to $\|\cdot \|$.


For $x\in \C^n$, we define $|x|\in \C^n$ with entries $(|x|)_i = |x_i|, \, \forall 1 \le i \le n$.

A norm is called **absolute** if $\||x|\| = \|x\|$.
A norm is called **monotone** if $|x_i|\le |y_i|, \forall $

[Missing]
<!-- all p-norm is absolute -->

$M_n(\C) \Longleftrightarrow \C^{n^2}$ so any norm of $\C^{n^2}$ is a norm of $M_n(\C)$.

*example*
Using $\|\cdot\|_2$ of $\C^{n^2}$, we can write the **Frobeniuous norm**

$$
\|A\|_F = \left(\right)
$$

[Missing]

*example*
using $\|\cdot\|_\infty$ for $\C^{n^2}$, we cee this is not consistent, for 

$$
A = B = ones
$$


---

Given a vector norm $\|\cdot\|$, a matrix norm $\|\cdot\|$ is called compatible with the vector norm $\|\cdot\|$ if 

$$
\|Ax\|\le \|A\|\|x\|, \, \forall A \in M_n(\C), x\in \C^n.
$$

With given vector norm $\|\cdot\|$ on $\C^n$, consider

$$
\|A\| = \max_{\substack{x\in \C^n\\ \|x\|=1}} \|Ax\| = \max_{\substack{x\in \C^n\\ \|x\|\neq 0}} \frac{\|Ax\|}{\|x\|}.
$$

Given $x\in \C^n$,

$$
\|A\| \ge \frac{\|Ax\|}{\|x\|}
$$

so this matrix norm is compatible with the vector norm.

The matrix norm is called the matrix norm **induced by or subordinate** to the given vector norm.

We have the following notation:

$$
\|A\|_p = \max_{x\neq 0} \frac{\|Ax\|_p}{\|x\|_p}
$$

$$
\|A\|_\infty = \max_{x\neq 0} \frac{\|Ax\|_\infty}{\|x\|_\infty}
$$

We have the following simplication:

1. $\displaystyle\|A\|_\infty = \max_{1\le i\le n}$


[Missing]

*relation*
1. A matrix norm that is induced by the a vector norm, is consistent,
   
   $$
   \|AB\| = \max
   $$

[Missing]

1. Not all compatible matrix norm are induced by some vector norm, e.g. Frobenius norm

    $$
    \|I\|_F = n^{\frac{1}{2}}
    $$

    However, 

<!-- Frobenius norm is consistent /compatible with 2-norm -->