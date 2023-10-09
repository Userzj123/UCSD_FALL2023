# LEC02 - OCT4
Content -- Convay III 1, III 2.
1. Power sereies
2. e^z, sinz, cosz, logz

## Power series and Analytic Functions
$c \in \C$, $a_n \in \C$

$$
f(z) = \sum_{n = 0}^\infty a_n (z - c)^n
$$ (eq:complex_power_series)

```{prf:theorem} Power Series of Complex Functions
:label: theorem_convergence
$\exists radius of convergence $R$, 0\le R \le \infty$, s.t.,
1. if $|z-c|< R$ then {eq}`eq:complex_power_series` converges absolutely and locally uniformly.
1. if $|z-c| > R$ then {eq}`eq:complex_power_series` diverges. Moreover, $\displaystyle R^{-1} = \limsup_{n\rightarrow \infty} \sqrt[n]{|a_n|}$
```

```{prf:definition} Analytic Function
$f:u\rightarrow \C$ is analytic if $\forall z \in u \exists R>0$ s.t.,

$$
f(z) = \sum_{n = 0}^\infty a_n (z - z_0)^n \text{ in } \Delta(z_0, R)\subseteq u
$$
```

(proof_complex_power_series_convergence)=
```{prf:proof} Convergence
WLOG $C = 0$, else $z^{\text{new}} = z - c$.

we will show {eq}`eq:complex_power_series` $ = \sum_{n=0}^{\infty} a_n z^n$ converges uniformly in $\Delta(0, r)$ for $r<R$

Let $r<\rho < R$. Note $\displaystyle \limsup_{n\rightarrow \infty} \sqrt[n]{|a_n|} = \frac{1}{R} < \frac{1}{\rho}$.

$$
\begin{aligned}
    & \Rightarrow \exists N, \sqrt[n]{|a_n|} < \frac{1}{\rho}, \text{ for } n \ge N\\
    & \Rightarrow \underbrace{|a_n z^n|}_{f_n} < \underbrace{\frac{1}{\rho^n} r^n}_{M_n} \text{, for } z\in \Delta(0, r), n\ge N
\end{aligned}
$$

Recall the Weierstrass M-test
> $|f_n|\le M_n, \sum_n M_n < \infty$ then $\sum_n f_n$ converges absolutely and uniformly.

$\Longrightarrow \sum_n a_n z^n$ converge absolutely and uniformly in $\Delta(0, r)$.
```


```{prf:proof} Divergence

If $|z|>\rho>R$

$$
\begin{aligned}
    &\Rightarrow \limsup_{n\rightarrow\infty}{\sqrt[n]{|a_n|}} = \frac{1}{R} > \frac{1}{\rho}\\
    & \Rightarrow \sqrt[n]{|a_n} > \frac{1}{\rho} \text{for infinitely many n's}\\
    & \Rightarrow |a_n| > \frac{1}{\rho^n}\\
    & \Rightarrow |a_n z^n| > \left( \frac{|z|}{\rho} \right)^n \text{ for infinitely many n's}\\
    & \Rightarrow a_n z^n \not\to 0\\
    & \Rightarrow \sum_{n} a_n z^n \text{ diverges}.
\end{aligned}
$$
```



```{prf:remark} (Rudin III.38)
If $\alpha = \lim_{n\rightarrow \infty} \left| \frac{a_{n+1}}{a_n}\right| = \text{exists, then } R=\alpha^{-1}$.
```

### Differentiation of power series

1. If $f_n \rightarrow f$, it is false that $f_n' \rightarrow f'$.
1. If $\sum f_n = f$, it is false that $\sum f_n' = f'$.

However, for power series, we have

```{prf:theorem} (Rudin 8.1)
If $\sum_{n=0}^\infty a_n (z-c)^n$ has radius $R$, then $\sum_{n=1}^\infty na_n (z-c)^{n-1}$ has radius $R$. Furthermore, if $f(z) = \sum_{n=0}^\infty \in \Delta(c, R)$.
$\Rightarrow f'(z) = \sum_{n=1}^\infty na_n (z-c)^{n-1} \text{ in } \Delta(c, R)$.
```


```{prf:corollary}
$f$ analytic $\Rightarrow$ f holomorphic ($\Rightarrow$ complex differentiable).
```


Furthermore, differentiate k-times in $\Delta(c, R)$,

$$
\frac{f^{(k)}}{k!} = a_k.
$$

Thus, f analytic means that power series of f is Taylor expansion of f.

```{prf:proof}
$c =0, z^{\text{new}} = z-c$,

$$
\sum_{n=1}^{\infty} na_n z^{n-1} \text{converges} \Longleftrightarrow \sum_{n=0}^\infty na_n z^n \text{ converges.}
$$

```

```{prf:proof}
Let $S_n = \sum a_n z^n$, remainder $\sum_{n\ge N+1} z_n z^n$.

We know $S_N \rightarrow f$. Let $g = \sum na_n z^{n-1}$.


Wish $f'(a) = g(a)$ for $a\in \Delta(0, R)$.

Let $\epsilon >0$. Want $\delta >0$, such that in $\Delta(0, R)$,

$$
\frac{f(z) - f(a)}{z-a} - g(a) = \frac{}{} - + - + \frac{}{}< \epsilon
$$

```


## Exponential

Example:
1. $e^z = \sum_{n = 0}^\infty \frac{z^n}{n!}$ converges for $z\in\C$.

$$
R^{-1} = 
$$

1. $\cos{z} = \frac{}{}$, $\sin{z} = \frac{}{}$. Derivative,
$sin^2   $

*Beware* sin & cos are not bounded by 1.
Ex. $\cos{(\pi\mathrm{i}n)} \rightarrow \infty$.


## Logarithm
$e^{2\pi\mathrm{i}n} = 1$, thus

$$
\log{1} = 0, \pm2\pi\mathrm{i}, \pm4\pi\mathrm{i}, \dots
$$

which value should be picked?

### Example a
```{prf:definition}
:label: def-3
$u \subseteq \C \\ \{0\}$
```

Q1: Does the log exist? Maybe
Q2: Is it unique? No

Example: 
$u \subseteq \C \\ \{0\}, \nexists \log \text{on} u$

$z = r e^{\mathrm{i}\theta}, \theta \in \left[\pi, pi\right)$

**fails continuity**


Example A
Let $u = \C \\ \R_{\le 0} = \text{slit plane}$.

*Define* $\Log{z} = \log{r} + \mathrm{i}\theta, \theta \in (-\pi, \pi) = continuous$
$=$ principal branch of log


*Beware*
$\Log(zw) \neq \Log z + \Log w$

### Example b
Let $u = \C \\ \R_{\le 0}$


### Example c (HW)
$U = \Delta(1, 1)$

$L(z) = \sum \frac{(-1)^{n-1}}{n} (z-1)^n$ is a log in $u$.

### Example
$\sqrt{z} $

By convention, we define

$$
z^\alpha = e^{\alpha l(z)} \text{ where } l \text{ is a logarithm}.
$$

multiple values up to the $e^{\alpha 2\pi \mathrm{i}n}, n\in \Z$


Undefined on $u = \C \setminus 0$, but defined on $\C - \R_{\le 0}$ by means of principal branch of l.
