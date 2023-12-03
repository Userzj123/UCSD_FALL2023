# Lec 25

*proposition* Let $V$ finite dimension vector space with basis $B$ and norm $\|\cdot\|_2$


*lemma*
The unit ball centered at the origin of 

$$
B_1(0) = \{x \in V | \|x\|_2=1\}
$$

is compact.

*proof*
Consider

$$
c_1 = \min_{\|z\|_2 = 1}
$$

[Missing]

So the inequality are sharp (equality for some $x$).

*Corralry*

[Missing]


*Norm Equivalence*
Given norms $\|\cdot\|, \|\cdot\|_2$in a finite dimensional vector space $V$, then $\exists c_1, c_2\gt 0$ real such that 

$$
c_1\|x\|'\le \|x\|\le c_2 \|x\|', \, \forall x\in V.
$$

*example*
In $\C^n$, find $c_1, c_2$ for norms $\|\cdot\|_\infty, \|\cdot\|_p$

[Missing]

A norm is called **absolute** if $\||x|\| = \|x\|$.
A norm is called **monotone** if $|x_i|\le |y_i|, \forall $


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