# Lec 21 Nov 20

**Courant-Fischer**

$$
\lambda_k(A) = \max_{\substack{S\subseteq \C^n, \\\dim S = k}} \min_{\substack{x\in S, \\x\neq 0}} \frac{x^HAx}{x^Hx}\\
\lambda_k(A) = \min_{\substack{S\subseteq\C^n,\\ \dim S = n-k+1}} \max_{\substack{x\in S,\\ x\neq 0}} \frac{x^HAx}{x^Hx}\\
\lambda_n(A)\le \dots \le \lambda_1(A)
$$


````{prf:proposition}
Let $C = A+B$ where $A, B\in M_n(\C)$ Hermitian. Then, $\forall 1\le k\le n$,

$$
\lambda_k(A)+\lambda_n(B)\le \lambda_k(C)\le \lambda_k(A) + \lambda_1(B),
$$

```{prf:proof}
Consider

$$
\lambda_k(A) = \min_{\substack{S\subseteq\C^n,\\ \dim S = n-k+1}} \max_{\substack{x\in S,\\ x\neq 0}} \frac{x^HAx}{x^Hx}.
$$

Suppose subspace $W\subseteq \C^n$, and $\dim W = n-k+1$, such that

$$
\lambda_k(A) = \max_{\substack{x\in W,\\ x\neq 0}} \frac{x^HAx}{x^Hx}.
$$


Furthremore, 


$$
\begin{aligned}
\lambda_k(C) &= \min_{\substack{S\subseteq\C^n,\\ \dim S = n-k+1}} \max_{\substack{x\in S,\\ x\neq 0}} \frac{x^HCx}{x^Hx}\\
& \le \max_{\substack{x\in W,\\ x\neq 0}} \frac{x^HCx}{x^Hx}\\
& \le \max_{\substack{x\in W,\\ x\neq 0}} \frac{x^HAx}{x^Hx} +  \max_{\substack{x\in W,\\ x\neq 0}} \frac{x^HBx}{x^Hx}\\
& \le \lambda_k(A) + \underbrace{\max_{\substack{x\in \C^n, \\ x\neq 0}} \frac{x^HBx}{x^Hx}}_{\lambda_1(B)}.
\end{aligned}
$$


For the other inequality, apply previous result to $A = C+(-B)$ to get 

$$
\begin{aligned}
    \lambda_k(A) & \le \lambda_k(C) + \lambda_1(-B),\\
    & = \lambda_k(C) - \lambda_n(B).
\end{aligned}
$$

```

```{prf:example}

Let $A\in M_n(\C)$ Hermitian and $z\in \C^n\setminus\{0\}$, study $C = A+\underbrace{zz^H}_{\text{Hermitian }B}$

1. $C = A-B$, note that $z$ is an eigenvector of $B$ with eigenvalue $(z^Hz)$ since $zz^Hz = (z^Hz)z$. If $w\perp z$, then $zz^Hw = 0$, and

$$
\lambda_k(A) - z^Hz \le \lambda_k(C) \le \lambda_k(A) + 0
$$

2. $C=A+B$

$$
\lambda_k(A) - 0 \le \lambda_k(C) \le \lambda_k(A) + z^Hz
$$
```
````

````{prf:proposition}
Let Hermitian matrix $A\in M_n(\C)$ and let $C = A + zz^H$ for some $z\in \C^n$, then

$$
\lambda_{k+1}(C)\le \lambda_k(A), \forall 1\le k \le n-1\\
\lambda_k(A)\le \lambda_{k-1}(C), \forall 2\le k\le n
$$

```{prf:lemma}
For subspace $W\subseteq \C^n$ and $z \in \C^n$, then 

$$
\begin{aligned}
\dim (W\cap \{z\}^\perp) 
& = \dim W + \underbrace{\dim \{z\}^\perp}_{n-1 \text{ or } n} - \underbrace{\dim(W+\{z\}^\perp)}_{\ge n-1}\\
&\ge \dim(W) - 1\\
\end{aligned}
$$
```

```{prf:proof}
Start with


$$
\begin{aligned}
    \lambda_{k+1}(C) & = \max_{\substack{S\subseteq \C^n, \\\dim S = k+1}} \min_{\substack{x\in S, \\x\neq 0}} \frac{x^HCx}{x^Hx}\\
    & = \min_{\substack{x\in W, \\ x\neq 0}} \frac{x^HCx}{x^Hx}, \text{ for some subspace } W\subseteq \C^n, \dim W = k+1
\end{aligned}
$$

Note for $x\in \{z\}^\perp$, $Cx = (A\pm zz^H)x = Ax$. Thus, let $V = W\cap \{z\}^\perp$, then

$$
\begin{aligned}
\lambda_{k+1}(C) &= \min_{\substack{x\in W, \\ x\neq 0}} \frac{x^HCx}{x^Hx},\\
& \le \min_{\substack{x\in V, \\ x\neq 0}} \frac{x^HCx}{x^Hx},\\
& = \min_{\substack{x\in V, \\ x\neq 0}} \frac{x^HAx}{x^Hx},\\
& \le  \max_{\substack{S\subseteq \C^n, \\\dim S = \dim V}} \min_{\substack{x\in S, \\x\neq 0}} \frac{x^HAx}{x^Hx}\\
& = \lambda_{\dim V}(A) \\
& \le \lambda_k(A)
\end{aligned}
$$

Note other inequality similar using other form of Courant-Fisher.

```
````

```{prf:corollary}
Hermitian matrix $A \in M_n(\C)$, Let $C = A \pm zz^H$ for some $z\in \C^n$, then

$$
\lambda_{k+1}(C)\le \lambda_k(A), \forall 1\le k \le n-1\\
\lambda_k(A)\le \lambda_{k-1}(C), \forall 2\le k\le n,
$$

since $A = C\mp zz^H$. Same as previous proposition.
```

```{prf:definition}
Hermitian matrix $A\in M_n(\C)$ is called **positive definite** i.f.f. $x^*Ax \gt 0 \forall x\in \C^n \setminus \{0\}$. And it is **positive semidefinite** i.f.f. $x^HAx \ge 0 \forall x\in \C^n$.

It is possible to define for $\F = \R$ and $A\in M_n(\R)$, $x^\top Ax \gt 0, \forall x\in \R^n\setminus\{0\}$ as beging positive definite. Here $A$ positive definite does not necessarily imply $A$ symmetric. Mostly in this setting, work with symmetric positive definite (SPD).
```

````{prf:proposition}
Let $A\in M_n(\C)$ be Hermitian, then

1. $A$ positive semidefinite i.f.f. $\lambda \ge 0, \forall \lambda \in \sigma(A)$
2. $A$ positive definite i.f.f. $\lambda \gt 0, \forall \lambda \in \sigma(A)$

```{prf:proof}
I. 
(forward) $\lambda \in \sigma(A)$ means $(\lambda, x)$ is eigenpair of $A$ for some $x\in \C^n\setminus\{0\}$, then 

$$
\lambda = \frac{x^HAx}{x^Hx} \ge 0
$$

(backward) $\lambda \ge 0, \forall \lambda \in \sigma(A)$ means that $\displaystyle\min_{\lambda \in \sigma(A)} \lambda\ge 0$. Then, for some $x\in \C^n$ satisfies $x^Hx = 1$,

$$
x^HAx \ge\min_{\lambda \in \sigma(A)} \lambda\ge 0.
$$

Thus, $\forall x\in \C^n\setminus\{0\}$, 

$$
\frac{x^HAx}{x^Hx} \ge 0.
$$

II.
Similarly.

```
````