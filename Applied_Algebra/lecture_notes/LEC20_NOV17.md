# Lec 20
For Hermitian matrix $A$, we have

$$
\min{\sigma(A)} = \min_{x\neq 0} \frac{x^HAx}{x^Hx}
$$

$$
\max{\sigma(A)} = \max_{x\neq 0} \frac{x^HAx}{x^Hx}
$$

## Cournt-Fischer Theorem

```{prf:theorem} Cournt-Fischer Theorem
Suppose $A\in M_n(\C)$ Hermitian, and its eigenvalues in order,

$$
\lambda_n \le\dots \le\lambda_1,
$$


Then, we have

$$
\lambda_k(A) = \max_{\substack{S\subseteq \C^n, \\\dim S = k}} \min_{\substack{x\in S, \\x\neq 0}} \frac{x^HAx}{x^Hx}\\
\lambda_k(A) = \min_{\substack{S\subseteq\C^n,\\ \dim S = n-k+1}} \max_{\substack{x\in S,\\ x\neq 0}} \frac{x^HAx}{x^Hx}
$$
```


````{prf:lemma}
Let subspaces $S_1, S_2 \in C^n$ satisfying $\dim(S_1)\lt \dim(S_2)$, then 

$$
S_2 \cap S_1^\top \neq \{0\}.
$$

```{prf:proof}

$$
\begin{align}
    \dim(S_2 + S_1^\top) & = \dim(S_2) + \dim(S_1^\top) - \dim(S_2 \cap S_1^\top)\\
    & = \dim(S_2) + n - \dim(S_1) - \dim(S_2 \cap S_1^\top)\\
    & \gt \cancel{\dim(S_2)} + n - \cancel{\dim(S_2)} - \dim(S_2 \cap S_1^\top)\\
    \dim(S_2 \cap S_1^\top) & \gt n - \dim(S_2 + S_1^\top) \ge n - n = 0\\
    \dim(S_2 \cap S_1^\top) & \ge 1
\end{align}
$$
```
````

```{prf:proof} Courant-Fischer

$A$ Hermitian $\Rightarrow \exists$ $n$ orthonormal eigenvectors of $A$, $\series{x}{n} \st X = [x_1, \dots, x_n]$ unitary, with $X^HAX = \Lambda = \lambda_1\oplus \dots \oplus \lambda_n$.

Fix $1\le i\le n$, let subspace $S\subseteq \C^n$ and $\dim(S) = i$. Then, learn on $S$ and $\span{x_1, \dots, x_{i-1}}$.

$$
S\cap\{x_1, \dots, x_{i-1}\}^\perp \neq \{0\}
$$

so $\exists z\neq 0, z\in S \st z\perp \span{x_1, \dots, x_{i-1}}$ .

Note $z = Xw$ for some $w\neq 0$. 

$$
\frac{z^HAz}{z^Hz} = \frac{w^H\Lambda w}{w^Hw}
$$

Furthermore, since z is perpendicular to $\span{x_1, \dots, x_{i-1}}$, so $w_1 = \dots = w_{i-1} = 0$. 

so

$$
\frac{z^HAz}{z^Hz} = \frac{\sum_{j=i}^n \lambda_j|w_j|^2}{\sum_{j=i}^n |w_j|^2} \le \lambda_i
$$

$$
\min_{\substack{x\in S\\ x\neq 0}}\frac{x^HAx}{x^Hx} \le \lambda_i
$$

$$
S \text{ arbitrary } \Rightarrow \max_{\substack{S\subseteq \C^n, \\\dim S = k}} \min_{\substack{x\in S, \\x\neq 0}} \frac{x^HAx}{x^Hx} \le \lambda_i
$$

On the other hand, consider $W = \span{x_1, \dots, x_i}$, then $x\in W \Rightarrow x = Xw$ with $w_{i+1} = \dots = w_n = 0$. But then

$$
\frac{x^HAx}{x^Hx} = \frac{w^H\Lambda w}{w^Hw} = \frac{\sum_{j=1}^i \lambda_j|w_j|^2}{\sum_{j=1}^i |w_j|^2} \gt \lambda_i
$$

so 

$$
\min_{\substack{x\in W\\ x\neq 0}} \frac{x^HAx}{x^Hx} \ge \lambda_i\\
\max_{\substack{S\subseteq \C^n, \\\dim S = i}}\min_{\substack{x\in W\\ x\neq 0}} \frac{x^HAx}{x^Hx}\ge \lambda_i
$$

*Note* the second expression has similar proof.
```

we will use the notation $\lambda_1(A), \dots, \lambda_n(A)$ for eigenvalues satisfying $\lambda_n(A) \le \dots \le \lambda_1(A)$.

Some people may also use the notation of ordering eigenvalues as $\lambda_n\ge \dots \ge \lambda_1$, which might need to swap terms to fit our result.

````{prf:proposition}
Let $A \in M_n(\C)= \begin{bmatrix}A_{11} & A_{12}\\ A_{21} & A_{22}\end{bmatrix}$ Hermitian, where $A_{11}\in M_m(\C)$. Then 

$$
\lambda_{k+n-m}(A) \le \lambda_k(A_{11}) \le \lambda_k(A)
$$

for all $1\le k\le m$.

```{prf:proof}

Given subspace $T\in \C^m$ with $\dim(T) = k\le m$, extend it to $S_T = \left\{\begin{bmatrix}y \\ 0\end{bmatrix}\in \C^n | y\in T\right\}\subseteq \C^n$



*Note*
$x\in S_T \Longleftrightarrow x = \begin{bmatrix}y\\0\end{bmatrix},  y\in T\Longleftrightarrow x^Hx = y^Hy$ and $x^HAx = y^HA_{11}y$.

Thus,

$$
\begin{align}
    \lambda_k(A) & = \max_{\substack{S\subseteq \C^n, \\\dim S = k}} \min_{\substack{x\in S, \\x\neq 0}} \frac{x^HAx}{x^Hx}\\
    & \ge \max_{\substack{S_T\subseteq \C^n, \\\dim S_T = k}} \min_{\substack{x\in S_T, \\x\neq 0}} \frac{x^HAx}{x^Hx}\\
    & = \max_{\substack{T\subseteq \C^n, \\\dim T = k}} \min_{\substack{x\in S_T, \\x\neq 0}} \frac{x^HAx}{x^Hx}\\
    & = \max_{\substack{T\subseteq \C^n, \\\dim T = k}} \min_{\substack{y\in T, \\y\neq 0}} \frac{y^HA_{11}y}{y^Hy}\\
    & = \lambda_k(A_{11})
\end{align}
$$

*Note*
The other inequality done similarly with the second expression of Corant-Fischer Theorem.


**Eigenvalue interlacing results**
```
````
