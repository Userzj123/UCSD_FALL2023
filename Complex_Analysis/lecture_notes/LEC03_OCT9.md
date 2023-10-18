LEC03 OCT 9th
# Geometry of holomorphic maps (Convoy III.3)


*definition*
$T:\R^2\rightarrow \R^2$ is $\R$-linear and invertible
- T **orientation preserving** if $\det{T}>0$
- T **angle preserving**,
    
    $$
    \sphericalangle(\vec{v}, \vec{w}) = \sphericalangle(T\vec{v}, T\vec{w}).
    $$

*examples*
$T = \begin{bmatrix}a & -b \\b & a\end{bmatrix}, \alpha = a+\mathrm{i}b \neq 0, a, b \in \R$. Since $\det{T} = a^2+b^2 \neq 0$ satisfies first definition, we could have that if $\R^2 \approxeq \C, \alpha = re^{\mathrm{i}\theta}$. Then for all $z\in \R^2$, we have

$$
\underbrace{T(z)}_{\text{dilation + rotation}} = \alpha z = re^{\mathrm{i}\theta}z
$$ 

*conclusion*
If $f:u \rightarrow \C$ holomorphic and $f'(z)\neq 0$ $\Rightarrow$ $Df(z)$ preserves orientation and angles.

*definition* $f:u\rightarrow \C$ holomorphic is **conformal** if $f'(z) \neq 0, \forall z\in u$.

*example*
$f(z) = z^2$ conformal away from 0.

$$
\begin{aligned}
    z = x+\mathrm{i}  &\Rightarrow f(z) = z^2 = \underbrace{x^2-1}_{u} + \ii \underbrace{2x}_{v} &\Rightarrow u = \frac{v^2}{4} - 1,\\
    z = 1+\ii y & \Rightarrow f(z) = z^2 = \underbrace{1-y^2}_{u} = \ii \underbrace{2y}_{v} & \Rightarrow u = 1- \frac{v^2}{4},
\end{aligned}
$$

which preserve that perpendicular angle.

*better notion*
Given $u, v\subseteq \C$, $f:u\rightarrow v$ **biholomorphism** if 
1. $f$ bijective + holomorphic
2. $f^{-1}: v\rightarrow u$ is holomorphic 

*note*
$f$ biholomorphic $\rightarrow$ $f$ conformal

*proof*
Let $g = f^{-1}$, then $g(f(z)) = z \Rightarrow g'(f(z))f'(z) = 1\Rightarrow f'(z)\neq0$

*question*
If $u, v \subseteq \C$, are $u, v$ biholomorhpic?

## Mobius transforms

**Mobius transforms/Fractional linear transformation(FLT)**

*Aside*
**Riemann sphere** 

$$
\hat{\C} = \C_{\infty} = \C \cup\{\infty\} = S^2
$$

in which $S^2\subseteq \R^3$ unit sphere.

topological space $u\subseteq \hat{\C}$
1. $\infty \notin u, u\subseteq \C$ open
2. $\infty \in u$
   1. $\forall u \neq \infty, \exists \Delta(u, r) \subseteq U, u\in U$
   2. $u = \infty, \exist r : \{|z|>r\}\subseteq u$.

Let $\underbrace{A}_{\text{invertible}} = \begin{bmatrix}a & b \\c & d\end{bmatrix} \in GL2$(General Linear 2by2 matrix), $a, b, c, d \in \C$.

*define*

$$
\begin{aligned}
    h_A : \hat{\C} & \overset{\text{mobius transformation}}{\Longrightarrow} \hat{\C} \\
    z &\Longrightarrow \frac{az+b}{cz+d}
\end{aligned}
$$

in which $\frac{1}{0} = \infty$.


1. $h_{AB} = h_A\circ h_B$
2. $h_\mathbb{1} =  \mathbb{1}$

$\Rightarrow h_{A^{-1}} = h_A^{-1} \Rightarrow h_A$ bijective and bicontinuous

3. $h_{\lambda \mathbb{1}} = \mathbb{1}$, $h_A = h_B \overset{1}{\Longleftrightarrow} h_{BA^{-1}} = \mathbb{1} \Longleftrightarrow BA^{-1} = \lambda \mathbb{1} \Longleftrightarrow B= \lambda A$

Mobius transforms are a group:
$GL_2/\langle \lambda \mathbb{1} \rangle_{\lambda \in \C^*} = PGL_2$ (projective general linear group). The best Mobius transform is **Gayley transform** (Convoy Ch6):

$$
\Delta = \Delta(0, 1) =\text{ unit disc}, \mathfrak{h}^+ = \{z:\IM{z}>0\}.
$$

$$
C: \mathfrak{h}^+ \rightarrow \Delta\\
z \rightarrow \frac{z-\mathrm{i}}{z+\mathrm{i}} \text{ holomorphic}\\
$$
 

$$
C^{-1}: \Delta \rightarrow \mathfrak{h}^+\\
w\rightarrow \mathrm{i} \frac{1+w}{1-w}
$$

If $z\in \mathfrak{h}^+ \Longleftrightarrow C(z)\in \Delta \Longleftrightarrow \frac{z-\ii}{z+\ii}<1 \Longleftrightarrow |z-\ii|<|z+\ii| \Longleftrightarrow x^2 + (y-1)^2 < x^2 +(y+1)^2  \Longleftrightarrow y>0 \Longleftrightarrow z\in \mathfrak{h}^+.$


*conclusion* !!!
$C$ establishes a biholomorphism $\mathfrak{h}^+ \approxeq \Delta$. 

*remark*
$\frac{az+b}{cz+d} = 
\begin{cases}
\frac{a}{c} + \frac{1}{z+\frac{d}{c}}\cdot\frac{ad-bc}{c^2} &\if c\neq 0\\
\frac{a}{d}z+\frac{b}{d} & \if c=0
\end{cases}
$


**mobius transforms**
1. $T(z) = z+\lambda$ translation
2. $R(z) = e^{\mathrm{i}\theta}z$ rotation
3. $D(z)=rz$ dialtion
4. $S(z) = \frac{1}{z}$ inversion

*definition* A generalized circle in $\hat{\C}$ is
1. a circle in $\C$
2. $L\cup\{\infty\}$, $L \rightarrow$line in $\C$

*theorem a*
<!-- :label: a -->
Mobius transforms send generalized circles to generalized circles.

*theorem b*
<!-- :label: b -->
"PGL2  $\rightarrow \hat{\C}$ tuply transitive"

$\forall (z_1, z_2, z_3), (z_1', z_2', z_3')$ distinct in $\hat{\C}$, $\exists ! \mathfrak{h}$ s.t. 

$$
\mathfrak{h}(z_1) = z_1'\\
\mathfrak{h}(z_2) = z_2'\\
\mathfrak{h}(z_3) = z_3'
$$

---
(proof_theorem_a)=
*proof*
Suffices to deal with $S(z) = \frac{1}{z}$

---
*lemma*
A generalized circle has 

$$
Az\bar{z} + Bz + C\bar{z} + D=0,
$$ (eq:theorem_a_eq1)

in which $A, D\in \R, B=\bar{C}$. Thus, S(`eq`{eq:theorem_a_eq1})

$$
\frac{A}{z\bar{z}} + \frac{B}{z} + \frac{C}{\bar{z}} + D = 0 \Longleftrightarrow Az\bar{z} + Bz + C\bar{z} + D=0
$$

(proof_lemma)=
*proof*

$$
\begin{aligned}
|z-\alpha| = r & \Longleftrightarrow (z-\alpha)(\overline{z-\alpha}) = r^2\\
& \Longleftrightarrow z\bar{z} - \alpha \bar{z} - \bar{\alpha} z + \underbrace{\alpha\bar{\alpha} -r^2}_{D}=0\\
& \Longleftrightarrow A = 1, B=-\bar{\alpha}, C = -\alpha, D = \alpha\bar{\alpha} -r^2=
\end{aligned}
$$

Lines correspond to $A=0$.

---

---
(proof_theorem_b)=
*proof*
- Uniqueness

$$
z_1 \overset{\mathfrak{h}_1}{\rightarrow} z'_1 \overset{\mathfrak{h}_2}{\rightarrow} z_1\\
z_2 \overset{\mathfrak{h}_1}{\rightarrow} z'_2 \overset{\mathfrak{h}_2}{\rightarrow} z_2\\
z_3 \overset{\mathfrak{h}_1}{\rightarrow} z'_3 \overset{\mathfrak{h}_2}{\rightarrow} z_3s
$$

Let $\mathfrak{h} = \mathfrak{h}_2^{-1}\circ \mathfrak{h}_1$, then $\mathfrak{h}(z_k) = z_k, \forall k=1, 2, 3$. Furthermore, $\mathfrak{h}(w) = w $ has two roots or trivial solution, so we could have

$$
\begin{aligned}
    \frac{aw+b}{cw+d} & = w\\
    aw + b& = cw^2 + dw\\
    \text{In order to satisfy uniqueness}\\
     c = 0, a=d, b=0 & \Rightarrow \mathfrak{h}=\mathbb{1}
\end{aligned}
$$

- Existence
$z_1$
$z_2$
$z_3$

we reduce to the case $(z_1, z_2, z_3) \rightarrow (0, 1, \infty)$

$z\rightarrow \frac{\frac{z-z_1}{z-z_3}}{\frac{z_2 - z_1}{z_1 - z_3}}$, this forms make sense even if any $z_k=\infty$.


Next time, Cauchy theory.