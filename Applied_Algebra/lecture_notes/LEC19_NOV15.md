# Lec 19 Nov 15

*porposition*
For $A\in M_n(\C)$, then $F(A)\subseteq \C$ is convex. Meaning that given $\alpha, \beta \in F(A)$, then 

$$
\theta \alpha + (1-\theta) \beta \in F(A), \forall \theta \in (0, 1)
$$

*proof*
$\alpha, \beta \in F(A) = \{x^HAx|x^Hx=1\} \Rightarrow \exists x, y \st x^HAx = \alpha, y^HAy = \beta \& x^Hx = y^Hy = 1$.

Show $\exists z\in \C^n, \st \theta \alpha + (1-\theta)\beta = z^HAz$ where $z^Hz = 1$.

We try to consider 

$$
W(t) = \frac{tx + (1-t)y}{\|tx + (1-t)y\|}, t\in (0, 1)
$$

If $tx + (1-t)y = 0$, then $x, y$ linear independent $\st x = \gamma y$, but

$$
x^Hx = \gamma^H \gamma y^Hy = |\gamma|^2 \Rightarrow |\gamma|=1.
$$

Furthermore, 

$$
\alpha = x^HAx =  \gamma^H \gamma  y^HAy = \beta.
$$

Thus, $\theta \alpha + (1-\theta)\beta = \alpha, \forall \theta\in(0, 1)$ and $z = x$ works.


Otherwise, if $tx+(1-t)y \neq 0$, then write

$$
A = B\alpha + (I-B)\beta,
$$

with $B= \frac{A-\beta I}{\alpha - \beta}$. Case when $\alpha = \beta$ has been discussed above.

So want to show that $z^HAz = \theta \alpha + (1-\theta)\beta$ where $z^HAz = \alpha z^HBz + \beta (1- z^HBz)$.

So want to find $z\in \C^n$ with $z^Hz = 1$ and $z^HBz = \theta$.


Consider the function $f:[0,1] \rightarrow \C(t \rightarrow w(t)^HBw(t))$, which is continuous and $f(0) = y^HBy = 1, f(1) = x^HBx = 0$. 

> <span style='color:red'> Why we need to modify the function f?</span>
Because it could be complex value then the line segment equation can no longer be satisfied.


We will modify this function $f$:
write $B = X+\ii Y$ where $X, Y$ are Hermitian, then 

$$
\begin{aligned}
    W(t)^HB W(t) & = \underbrace{W(t)^HX W(t)}_{\text{real}} + \ii \underbrace{W(t)^HY W(t)}_{\text{real} \& = 0}
\end{aligned}
$$


Furthermore, 

$$
\begin{aligned}
    W(t)^HY W(t) &  = 
\end{aligned}
$$


[Missing]


So $\hat{W}(t) = \frac{tx + (1-t)v}{\|tx + (1-t)v\|}, t\in (0, 1)$ and $\hat{f}:[0,1] \rightarrow \R(t \rightarrow \hat{W}(t)^HB\hat{W}(t))$ with $\hat{f}(0) =1$ and $\hat{f}(1) = 0$.

So intermediate value theorems says given any $\theta\in (0,1), \exists t \st \hat{f}(t) = \theta$ and $\hat{W}(t)^\top B\hat{W}(t) = \theta$, so take $z = \hat{W}(t)$.



> In the case $A$ is normal, it turns out that $F(A)$ is the convex hall of $\sigma(A)$.


*proposition*
$A\in M_n(\C)$ Hermitian $\Longleftrightarrow F(A) \subseteq \R$.

*Lemma*
For $A\in M_n(\C)$, $x^HAx = 0$ for all $x\in \C^n$. $\Longleftrightarrow A = 0$.

*proof*
$(\Rightarrow)$ done before

$(\Leftarrow)$ $\forall x\in C^n$, we have 

$$
\underbrace{x^HAx}_{\text{real}} = x^H(X+\ii Y)x = x^HXx + \ii x^HYx
$$

Then $x^HYx = 0$, so $A = X$ is Hermitian.


---

$A$ Hermitian, then $F(A) = [\lambda_n, \lambda_1]$, where $\lambda_n = \min{\sigma(A)}, \lambda_1 = \max{\sigma(A)}$.

In Face, 

$$
\lambda_n = \min{F(A)} = \min_{x^Hx=1}{x^HAx} = \min_{x\neq 0}{\frac{x^HAx}{x^Hx}} 
$$


and 

$$
\lambda_1 = \max{F(A)} = \max_{x^Hx=1}{x^HAx} = \max_{x\neq 0}{\frac{x^HAx}{x^Hx}} 
$$