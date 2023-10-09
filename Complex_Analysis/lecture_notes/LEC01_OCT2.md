*Prerequisite* 140 Rudin 

# LEC01 - OCT 2nd

## Complex differentiable (CD)
```{prf:definition} Complex Differentiable
Let $u \subseteq \C$ open & connected. $f: u \rightarrow \C$ is *Complex differentiable (CD)* if 

$$
\lim_{n\rightarrow0} \frac{f(z+h) - f(z)}{h} := f'(z) \text{ exists and is finite, }\forall z \in u
$$ (eq:complex_differentiation)
```

```{prf:example}
1. $f$, $g$ CD $\rightarrow$ $f+g$, $fg$ CD
2. $f(z) = 1, z, z^2, \dots, z^n$ are CD, but $f(z) = \bar{z}$ (complex conjugated) is *not* CD. Because it approaches to 1 along real and -1 along imaginary,

$$
f(h) = \lim_{h\rightarrow0 } \frac{\bar{h}}{h} = \begin{cases}
   1 & \forall h \in \R,\\
   -1 & \forall h \in \mathrm{i}\R.
\end{cases}
$$

[Further reading](https://math.stackexchange.com/questions/2199702/why-isnt-fz-barz-complex-differentiable#:~:text=Multiplication%20by%20a%20complex%20number,point%20in%20the%20complex%20sense.)

```

## Comparison with Real Analysis (RA)
**Real differentiable function**
same as {eq}`eq:complex_differentiation`

```{prf:example}
$f \text{ is CD} \Rightarrow f' \text{ is CD} \Rightarrow F'' \text{ is CD} \Rightarrow \exists \text{ derivatives of all order}$[^complex_infinite_derivatives].

[^complex_infinite_derivatives]: Why differentiable complex functions are infinitely differentiable? [Reference](https://math.stackexchange.com/questions/640/why-are-differentiable-complex-functions-infinitely-differentiable)

In real analysis, this fails, e.g.,

$$
f(x) = \begin{cases}
   x^2 \sin{\frac{1}{x}}, & x\neq 0\\
   0, & x = 0
\end{cases} \quad \Longrightarrow \quad
f'(x) = \begin{cases}
   2x\sin{\frac{1}{x}} - \cos{\frac{1}{x}}, & x\neq 0\\
   0, & x=0
\end{cases}
$$
```


````{prf:example}
In complex, if $f$ is CD in $U$ then $f$ converges to its Taylor expansion[^complex_power_series], 

$$
f(z) = \underbrace{ \sum_{n=0}^\infty \frac{f^{(n)}(a)}{n!} (z-a)^n  }_{\text{Taylor series}} , \quad \forall z \text{ near } a, 
$$

[^complex_power_series]: Power series of complex function is proved [here](proof_complex_power_series).

In real analysis, this is false, e.g.,

$$
f(x) = \begin{cases}
   e^{-\frac{1}{x^2}}, & x\neq 0\\ 0, & x=0
\end{cases}, \quad
f^{(n)}(0) = 0.
$$

So that Taylor expansion of $f$ at $0$ is 0, which does not equal to its value in any interval $(-r, r), r>0$.

````


````{prf:example}
If $f: \C \rightarrow \C$ is complex differentiable for $u = \C$ and f bounded $\Rightarrow$ f is constant

If f is real differentiable, this fails. For example, $f(x) = \sin{(x)} \R \rightarrow \R$ is RD + bounded, but $f$ is not constant.
````

```{prf:example}
**Identity Theorem**

$f. u \rightarrow \C$ is CD and $f\equiv 0$ on $V \le U$ open
$\Rightarrow f\equiv 0$ on U, which fails in RA.
```

## Better Comparison
It is more appropriate to compare $RD_2$, real differentiable function in 2 variables, with complex differentiable.

Identify that $\C \approxeq \R^2, z = x + \ii y \Longleftrightarrow \begin{bmatrix}
   x\\y
\end{bmatrix} \in \R^2$. And define $|z| = \sqrt{x^2 + y^2}$.

````{prf:definition}
$f: u \subset \R^2 \rightarrow \R^2$ is real differentiable (RD2), if $\forall z\in U, \exists \, A: \R^2 \rightarrow \R^2$ be $\R$-linear (differentiable on $z$).


$$
\lim_{h\rightarrow 0} \frac{|f(z+h) - f(z) - Ah|}{|h|} = 0,
$$ (eq:def_rd2)

```{prf:remark}
$$
A = Df(z) = J_f(z).
$$

If f=(u, v) is RD2 $\Rightarrow$ u, v admit partial derivatives and $A = \begin{bmatrix}
   u_x & u_y\\ v_x & v_y
\end{bmatrix}$.

Conversely, if partial derivatives exist and are continuous $\Rightarrow$ f is RD2. 

Details see [Rudin 9.21 or Math 140C].
```

````




```{prf:remark}
if $f: u \rightarrow \C$ is complex differentaible $\Rightarrow f: u \rightarrow \R^2 \approxeq \C$ is real differentiable, 

$$
\lim \frac{f(z+h) - f(z) - f'(z)h}{h}= 0
$$


difference: Complex number vs Linear mapping matrix

Question??[^linear_mapping]

[^linear_mapping]: Real linear and complex linear. [reference](https://math.stackexchange.com/questions/1420014/real-linear-vs-complex-linear)
```



````{prf:lemma}
:label: lma_real_complex
Let $A: \R^2 \rightarrow \R^2$ be $\R$-linear,  TFAE:
1. A is $\C$-linear
2. $\forall h , A(h) = \alpha h,\text{ for } \alpha \in \C$
3. For $ \alpha = a+ \mathrm{i}b , A = \begin{bmatrix}a & -b\\ b & a \end{bmatrix}, a, b \in \R$


```{prf:proof}

2$\leftrightarrow$1,

$$
A(1) = \alpha \Longleftrightarrow A(h) = hA(1) = \alpha h
$$

2 $\rightarrow$ 3,

$$
A\begin{bmatrix} 1\\0\end{bmatrix} =A(1) = \alpha =  \begin{bmatrix}a\\ b\end{bmatrix},
$$

$$
A\begin{bmatrix} 0\\1\end{bmatrix} = A(\ii) = \ii \alpha =  \begin{bmatrix}-b\\ a\end{bmatrix},
$$

so that we have 

$$
A = A\begin{bmatrix} 1 & 0\\ 0 &1\end{bmatrix} = \begin{bmatrix}a & -b\\ b & a \end{bmatrix}.
$$

```
````


```{prf:remark}
According to {prf:ref}`lma_real_complex`, TFAE
1. $f$ is CD.
1. $f$ is real differentiable (RD2) and  $Df(z)$ is $\C$-linear
```

```{prf:remark}
If $f$ is CD then, $Df(z) = A = \begin{bmatrix}
   u_x & u_y \\ v_x & v_y
\end{bmatrix}$ is $\C$-linear. By the {prf:ref}`lma_real_complex`, we could obtain the Cauchy-Riemann equations,

$$
\Rightarrow \begin{cases}
   u_x = v_y\\ u_y = -v_x
\end{cases}
$$ (eq:cauchy_riemann)

Conversely, if CR hold and the derivatives are continuous $\Rightarrow$ f is CD.


```

```{prf:remark}
If f is complex differentiable and class $\C^2$, then we could conclude that $u=\RE (f), v = \IM (f)$ are harmonic according to the relationship of second order partial derivatives,

$$
\begin{cases}
   u_{xx} = v_{yx}, \\ u_{yy} = -v_{xy},
\end{cases} \Rightarrow \begin{cases}
   u_{xx} + u_{yy} = 0,\\ v_{xx} + v_{yy} = 0.
\end{cases}
$$

> If class $\C^2$ function h satisfies $h_{xx}+h_{yy}=0$, it is said to be **harmonic**.

Pairs $(u, v)$ arising this way are called **harmonic conjugate**.
```

## Notations (Derivatives and Other Reallocations)

$$
\begin{cases}
   z = x+\mathrm{i}y\\
   \hat{z} = x-\mathrm{i}y
\end{cases} \Longleftrightarrow \begin{cases}
   x = \frac{z + \hat{z}}{2}\\
   y = \frac{z - \hat{z}}{2\ii}
\end{cases}
$$


According to chain rule,

$$
\frac{\partial }{\partial z} = \frac{\partial }{\partial x}\frac{\partial x}{\partial z} + \frac{\partial }{\partial y}\frac{\partial y}{\partial z}
$$

same for the $\hat{z}$.

Assuming that $z$ and $\hat{z}$ are independent, so that we have 

$$
\frac{\partial x}{\partial z} = \frac{1}{2}, \text{etc.}
$$


```{prf:definition}
$$
\frac{\partial}{\partial z} = \frac{1}{2} \left( \frac{\partial}{\partial x} + \ii \frac{\partial }{\partial y} \right)\\
\frac{\partial}{\partial \bar{z}} = \frac{1}{2} \left( \frac{\partial}{\partial x} - \ii \frac{\partial }{\partial y} \right)\\
$$
```

*Sanity Check:*
Assume f is complex differentiable,

$$
\frac{\partial f}{\partial z} = \frac{1}{2} \left(\cancelto{0}{u_x - v_y} + \ii \left(\cancelto{0}{v_x + u_y}\right)\right) = 0
$$


```{prf:lemma} f depends on $z$ but not dependent on complex conjugate $\bar{z}$
f is complex diff $\Rightarrow \frac{\partial f}{\partial \bar{z}} = 0 \Longleftrightarrow$ (Cauchy-Riemann Equations)

Furthermore, $\frac{\partial f}{\partial z} = f'(z)$.
```