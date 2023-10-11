* Couchy theory and integration (Convoy IV)

*Integration*
$U\subseteq \C$, $\Gamma:[a, b] \to u$, $C^\perp$ path

- length $(\gamma)= \int_a^b |\Gamma'(t)|dt$
- reparameterization
- piecewise path

*remark*
if $\Phi$ = orientation preserving

$$
\int_\Gamma f\dd z = \int_a^b f(\Gamma(t))\Gamma'(t)\dd t\\
\int_{\hat{\Gamma}}
$$

$\Rightarrow \int_\Gamma f \dd z$ is well-defined over oriented $C^1$ paths. In fact, $\int_{-\Gamma} = - \int_\Gammaf\dd z$, opposite orientation.


**Fundamental estimate**
If $1\le M \Rightarrow |\int_\Gamma f\dd z| \le M$ length($\Gamma$) $=\int_a^b f(\Gamma(t))\Gamma'(t)\dd t\le\int_a^b|| = M \text{ length}(\Gamma)$

**Fundamental example**
$\Gamma(t) = re^{\ii t}$

**example b**
Assume $f$ admits a primitive F (holomorphic, $F'=f$) and $\Gamma$ loop, then 
$$
\begin{aligned}
    \int_\Gamma f \dd zs &= \int_a^b F'(\Gamma(t)) \Gamma'(t)\dd t\\
    & = F(\Gamma(b)) - F(\Gamma(b)) = 0
\end{aligned}

$$

*Corollary*
$U = \C\setminus$

<span style='color:red'>why logrithm doesn't exists?</span>



*proposition a*
$u\subseteq \C, f:u\rightarrow \C$ holomorphic, TFAE
- f has a primitive $F$ in u
- $\int_\Gamma f\dd z = 0$ piecewise, $C^1$ lopp


*proposition b*
$u\subseteq \C, f:u\rightarrow \C$ holomorphic, TFAE
- f admits a primitive in $u = \Delta = \text{disc}$
- $\int_{\partial R}f\dd z = 0, \forall \text{ rectangles } \bar{R}\subseteq \Delta$

*proposition c* (Goursat)
$u\subseteq \C, f:u\rightarrow \C$ holomorphic

If $f:u\rightarrow \C$ is holomorphic, then $\int_{\partial R}f\dd z = 0 \forall \bar{R}\subseteq u$

*conclusion*
if $f:\Delta \rightarrow \C$ holomorphic $\Rightarrow$ (B+C) f has primitive $\Rightarrow$ (A) $\int_\Gamma f\dd z = 0 , \forall \Gamma$ piecewise $C^1$ loop in $\Delta$.

Any $f:u\rightarrow\C$ admits locally a primitive.


*proof*2->1
Fix $p\in u$. Let 

$$
\begin{aligned}
    F(q) &= \int_\Gamma f \dd z \text{ for } \Gamma, C^1 \\
&= \int_{\tilde{\Gamma}} f \dd z 
\end{aligned}
$$ 

piecewise path from $p$ to $q$.


For $\epsilon>0$, fix $\delta>0$, 

$$
|f(z)-f(g)|<\epsilon, \text{ in } \Delta(g, \delta)
$$

Note:
*
$$
\left|\frac{}{}\right|
$$


*proof* of ii to i in prop b
$F(g) = \int_p^q f\dd z = $ well defined as long as path is segments parallel to axes by ii.

<2\epsilon


*proof* that if $p\in u$ fixed, any $q$ can be joined to p by a pieewise $C^1$ path.

$\mathfrak{X}$


Let $q\in \mathfrak{X}\rightarrow q\in u \rightarrow \exists \Delta(q, R)\subseteq u$
Note $$

*prop c*
$f:u\to \C$ holomorphic, $\bar{R}\subseteq u$, $\int_{\partial R}f\dd z=0$

*Corollary*
$f:\Delta \rightarrow (holomorphic) \C, \Gamma, C^1 loop in \Delta_1, \int_\Gamma f\dd z=0$