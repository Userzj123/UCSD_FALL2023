Content -- Convay III 1, III 2.
1. Power sereies
2. e^z, sinz, cosz, logz

## Power series
$c \in \C$, $a_n \in \C$

$$
\sum a_n (z - c)^n
$$

```{prf:definition}
$\exists, 0\le \R \le \inf$
```

```{prf:property}
1. absolutely and locally uniformly
2. diverges
```

```{prf:proof}
WLOG $C = 0$, else $z^{\text{new}} = z - c$.
we will show $(\dag) = \sum $ converges uniformly in $\Delta(0, r)$ for $r<R$
```

```{prf:proof}

```

```{prf:remark} (Rudin III.38)
If $\alpha = \lim _{n\rightarrow \inf} = \text{exists}$

```

### Differentiation of power series

If $f_n \rightarrow f$, it is false that $f_n' \rightarrow f'$.
If $\sum f_n \rightarrow f$, it is false that $\sum f_n' \rightarrow f'$.

```{prf:theorem} (Rudin 8.1)
If $\sum a_n (z-c)^n$ has radius $R$, then $\sum na_n (z-c)^{n-1}$ has radius $R$. Furthermore, if $f(z) = \sum \in \Delta(c, R)$.
$\Rightarrow f'(z) = \sum$
```

```{prf:definition}
$f: u \rightarrow \C$ is analytic if $\forall c \in u, \exists \Delta(c, R) \text{and} \{a_n\}$
```

*Corollary*
$f$ analytic $\Rightarrow$ f holomorphic (-> complex differentiable).



Furthermore, differentiate k-times in $\Delta(c, R)$

$$
\Rightarrow \frac{f^{(k)}}{k!} = a_k
$$

<so that f analytic -> f Taylor series>

```{prf:proof}
$c =0, z^{\text{new}} = z-c$,

$$
\sum na_n z^{n-1} \text{converges} \Longleftrightarrow
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
$u \subseteq \Complex \\ \{0\}$
```

Q1: Does the log exist? Maybe
Q2: Is it unique? No

Example: 
$u \subseteq \Complex \\ \{0\}, \nexists \log \text{on} u$

$z = r e^{\mathrm{i}\theta}, \theta \in [\pi, pi)$

**fails continuity**


Example A
Let $u = \Complex \\ \R_{\le 0} = \text{slit plane}$.

*Define* $\Log{z} = \log{r} + \mathrm{i}\theta, \theta \in (-\pi, \pi) = continuous$
$=$ principal branch of log


*Beware*
$\Log(zw) \neq \Log z + \Log w$

### Example b
Let $u = \Complex \\ \R_{\le 0}$


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


Undefined on $u = \Complex \setminus 0$, but defined on $\Complex - \R_{\le 0}$ by means of principal branch of l.
