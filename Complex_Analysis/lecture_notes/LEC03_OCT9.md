# LEC03 OCT 9th
- Geometry of holomorphic maps (Convoy III.3)


*definition*
$T:\R^2\rightarrow \R^2$ is $\R$-linear and invertible
- T orientation preserving if $\det{T}>0$
- T angle preserving $\sphericalangle(\boldsymbol{v}, \boldsymbol{w}) = \sphericalangle(\mathbf{T}\boldsymbol{v}, \mathbf{T}\boldsymbol{w})$.

*examples*
$T = \begin{bmatrix}a & -b \\b & a\end{bmatrix}, \alpha = a+\mathrm{i}b \neq 0, a, b \in \R$
$\det{T} = a^2+b^2 \neq 0$ satisfies first point
$\R \approxeq \C, \alpha = re^{\mathrm{i}\theta}$
$T(z) = \alpha z = re^{\mathrm{i}\theta}z$ -> dilation + rotation

*conclusion*
If $f:u \rightarrow \C$ holomorphic and $f'(z)\neq 0$ $\Rightarrow$ $Df(z)$ preserves orientation and angles.

*definition* $f:u\rightarrow \C$ holomorphic is conformal if $f'(z) \neq \forall z\in u$.

*example*
$f(z) = z^2$ conformal away from 0

$z = x+\mathrm{i}$ ->

*better notion*
Given $u, v\subseteq \C$, $f:u\rightarrow v$ biholomorphism if 
1. $f$ bijective + holomorphic
2. $f^{-1}: v\rightarrow u$ is holomorphic 

*note*
f biholomorphic \rightarrow f conformal
*proorf*
$g = f^{-1}$
$g(f(z)) = z \Rightarrow g'(f(z))f'(z) = 1\Rightarrow f'(z)\neq0$

*question*
If $u, v \subseteq$, are $u, v$ biholomorhpic?

---
**Mobius transforms/Fractional linear transformation(FLT)**
*Aside*(Riemann sphere)
$\hat{\C} = \C_{\infty} = \C \cup\{\infty\} = S^2$

$S^2\subseteq \R^3$ unit sphere, s

topological space $u\subseteq \hat{\C}$
1. $\infty \notin u, u\subseteq \C$ open
2. $\infty \in u$

Let $\underbrace{A}_{\text{invertible}} = \begin{bmatrix}a & b \\c & d\end{bmatrix} \in GL2$ -> general linear 2by2

*define*
$h_A : \hat{\C} \rightarrow \hat{\C}$ **mobius transformation**
$z \rightarrow \frac{az+b}{cz+d}$, $\frac{1}{0} = \infty$


1. $h_{AB} = h_A\circ h_B$
2. h_1 = 1

$1, 2 \Rightarrow h_{A^{-1}} = h_A^{-1} \Rightarrow h_A$ bijective and bicontinuous

3. $h_{\lambda \mathbf{I}} = \mathbf{I}$, $h_A = h_B \Longleftrightarrow h_{BA^{-1}} = 1 \Longleftrightarrow BA^{-1} = \lambda 1 \Longleftrightarrow B= \lambda A$

Mobius transforms are a group:
$GL_2/\langle \lambda \mathbf{I}\rangle_{\lambda \in \C^*} = PGL_g$
PGL: projective general linear group


The best Mobius transform is *Gayley transform* (Convoy Ch6):
$\Delta = \Delta(0, 1) = unit disc, h^+ = \{z:\Im{z}>0\}$

$C: h^+ \rightarrow \Delta, z\rightarrow \frac{z-\mathrm{i}}{z+\mathrm{i}}$ holomorphic
$C^{-1}: \Delta \rightarrow h^+, w\rightarrow \mathrm{i} \frac{1+w}{1-w}$

If $z\in h^+ \Longleftrightarrow c(z)\in \Delta \Longleftrightarrow \frac{}{}<1 \Longleftrightarrow ||<|| \Longleftrightarrow x^2 + (y-1)^2 <  \Longleftrightarrow y>0 \Longleftrightarrow z\in h^+$


*conclusion* !!!
$C$ establishes a biholomorphism $h^+ \approxeq \Delta$. 

*remark*
$\frac{az+b}{cz+d} = 
\begin{cases}
\frac{a}{c} + \frac{}{}\cdot\frac{}{} &if c\neq 0\\
\frac{}{} & if c=0
\end{cases}
$


*mobius transforms*
1. $T(z) = z+\lambda$ translation
2. $R(z) = e^{\mathrm{i}\theta}z$ rotation
3. $D(z)=rz$ dialtion
4. $s(z) = \frac{1}{z}$ inversion

*definition* A generalized circle in $\hat{\C}$ is
1. a circle in $\C$
2. $LU\{\infty\}$, $L \rightarrow$line in $\C$

*theorem*
:label: a
Mobius transforms send generalized circles to generalized circles.

*theorem*
:label: b
"PGL2 -> $\hat{\C}$ tuply transitive"


(proof_theorem_a)=
*proof*
Suffices to deal with $S(z) = \frac{1}{z}$

*lemma*
A generalized circle has $Az\bar{z} + Bz + C\bar{z} + D=0$

(proof_lemma)=
*proof*
$|z-\alpha| = r \Longleftrightarrow (z-\alpha)(\bar{z-\alpha}) = r^2$
$\Longleftrightarrow $


(proof_theorem_b)=
*proof*
- Uniqueness
$z_1 \rightarrow z'_1$
$z_2 \rightarrow z'_2$
$z_3 \rightarrow z'_3$

$h = h_2^{-1}\circ h_1$

has two roots or trivial solution

- Existence
$z_1$
$z_2$
$z_3$

we reduce to the case $(z_1, z_2, z_3) \rightarrow (0, 1, \infty)$

$a\rightarrow \frac{\frac{z-z_1}{z-z_3}}{\frac{z_2 - z_1}{z_1 - z_3}}$, this forms make sense even if one of z is infinity.


Next time, Cauchy theory.