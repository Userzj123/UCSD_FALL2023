* Couchy theory and integration (Convoy IV)

*Integration*
$u\subseteq \C$, $\Gamma:[a, b] \to u$, $C^\perp$ path

- length $(\gamma)= \int_a^b |\Gamma'(t)|dt$
- a $C^1$ reparameterization

    $$
    \Phi : \underbrace{\underrightarrow{[\hat{a}, \hat{b}] \rightarrow [a, b] \overset{\Gamma}{\rightarrow} u}}_{\hat{\Gamma} = \Gamma \circ \Phi},
    $$

    If $\Phi'>0, \Phi$ is an orientation preserving reparametrization.

- $\Gamma$ is piecewise $C^1$ path, $\exists a = a_0 \lt a_1 \lt \dots \lt a_n = b$, s.t.,

    $$
    \Gamma(t) = \begin{cases}
        \Gamma_1(t), & t\in [a_0, a_1]\\
        \Gamma_n(t), & t\in [a_{n-1}, a_n]
    \end{cases}
    $$

    $\Gamma_2$ is of class $C^1$. $f:u\rightarrow \C$ const. 
    
    $$
    \int_{\Gamma} f \dd z = \int_{a}^b f(\underbrace{\Gamma(t)}_{z})\underbrace{\Gamma'(t)\dd t}_{\dd z}
    $$

*remark*
if $\Phi$ = orientation preserving, change of variables with $t = \Phi(s)$,

$$
\begin{aligned}
    \int_\Gamma f\dd z &= \int_a^b f(\Gamma(t))\Gamma'(t)\dd t\\
    \int_{\hat{\Gamma}}f\dd z & = \int_{\hat{a}}^{\hat{b}} f(\hat{\Gamma(t)})\hat{\Gamma}'(t)\dd t = \int_{\hat{a}}^{\hat{b}} f(\Gamma(\Phi(s)))\Gamma'(\Phi(s))\Phi'(s)\dd s
\end{aligned}
$$

$\displaystyle\Rightarrow \int_\Gamma f \dd z$ is well-defined over oriented $C^1$ paths. In fact, $\int_{-\Gamma} = - \int_\Gamma f\dd z$. $-\Gamma$ is the opposite orientation.


**Fundamental estimate**
If $1\le M$, then

$$
\begin{aligned}
    \Rightarrow \left|\int_\Gamma f\dd z \right| & \le M \text{length}(\Gamma) \\
    \left|\int_a^b f(\Gamma(t))\Gamma'(t)\dd t \right| & \le \int_a^b \underbrace{|f(\Gamma(t))|}_{M} \cdot |\Gamma'(t)| \dd t
\end{aligned}
$$ 

*example a*
$\Gamma(t) = e^{\ii t}, t\in [0, 2\pi]$, then $\Gamma'(t) = \ii e^{\ii t}$. Given $f(z)=z^n, n\in \Z$. Thus, we have

$$
\begin{aligned}
    \frac{1}{2\pi \ii}\int_{\Gamma}f \dd z &= \frac{1}{2\pi\ii}\int_{0}^{2\pi} f(\Gamma(t)) \Gamma'(t) \dd t\\
    & = \frac{1}{2\pi}\int_{0}^{2\pi} e^{\ii (n+1)t} \dd t = \begin{cases} 0, & n \neq -1 \\ 1, & n=-1 \end{cases}
\end{aligned}
$$



*example b*
Assume $f$ admits a **primitive** F (holomorphic, $F'=f$) and loop $\Gamma\subseteq U$, then 
$$
\begin{aligned}
    \int_\Gamma f \dd z &= \int_a^b F'(\Gamma(t)) \Gamma'(t)\dd t\\
    & = F(\Gamma(b)) - F(\Gamma(b)) = 0
\end{aligned}

$$

*Corollary*
$U = \C\setminus\{0\}$, $\frac{1}{z}$ has no primitive $\Longleftrightarrow \nexists$ logorithm in $\C\setminus\{0\}$.

<span style='color:red'>why logrithm doesn't exists?</span> Lec2

*proposition a*
$U\subseteq \C, f:U\rightarrow \C$ holomorphic, TFAE
- f has a primitive $F$ in U
- $\displaystyle\int_\Gamma f\dd z = 0, \forall$ piecewise $C^1$ loop.


*proposition b*
$u\subseteq \C, f:u\rightarrow \C$ holomorphic, TFAE
- f admits a primitive in $U = \Delta = \text{disc}$
- $\displaystyle\int_{\partial R}f\dd z = 0, \forall \text{ rectangles } \bar{R}\subseteq \Delta$

*proposition c* (Goursat)
If $f:U\rightarrow \C$ is holomorphic, then $\int_{\partial R}f\dd z = 0, \; \forall \bar{R}\subseteq U.$

*conclusion*
if $f:\Delta \rightarrow \C$ holomorphic $\overset{B+C}{\Longrightarrow}$ f has primitive $\overset{A}{\Longrightarrow}$ $\int_\Gamma f\dd z = 0 , \forall \Gamma$ piecewise $C^1$ loop in $\Delta$. Any $f:U\rightarrow\C$ admits locally a primitive.


*proof*2->1
Fix $p\in U$. Let 

$$
\begin{aligned}
    F(q) &= \int_\Gamma f \dd z \text{ for } \Gamma, C^1 \text{ path from p to q} \\
&= \int_{\tilde{\Gamma}} f \dd z \text{ for } \hat{\Gamma}, C^1 \text{ another path from p to q} \\
\int_\Gamma f\dd z - \int_{\hat{\Gamma}} f\dd z = \int_\eta f\dd z &= 0, \;\eta = \Gamma + -\hat{\Gamma}=\text{loop}
\end{aligned}
$$ 


For $\epsilon>0$, fix $\delta>0$, 

$$
|f(z)-f(g)|<\epsilon, \text{ in } \Delta(g, \delta) \subseteq U
$$

Note if $|h|\lt \delta$, then 

$$
\begin{aligned}
    \left|\frac{F(g+h) - F(g)}{h} - f(g)\right| & = \left| \frac{1}{h}\int_{g}^{g+h}f(z)\dd z - f(g) \right|\\
    & = \left| \frac{1}{h}\int_g^{g+h} \underbrace{(f(z) - f(g))}_{\lt \epsilon} \dd z \right| \le \cancel{\frac{1}{|h|}} \epsilon \cancel{|h|} = \epsilon
\end{aligned}
$$


*proof* of ii to i in prop b
$F(g) = \int_p^q f\dd z = $ well defined as long as path is segments parallel to axes by ii.


*proof* that if $p\in u$ fixed, any $q$ can be joined to p by a piecewise $C^1$ path,

$$
\mathfrak{X} = \{g\in U:\exists\text{ piecewise } C^1 \text{ path from p to q}\}.
$$

$\mathfrak{X} \neq \Phi$ since $p\in \mathfrak{X}$. Show $\mathfrak{X}$ is open + closed in $U$ ( = connected), hence $\mathfrak{X}=U$.

- $\mathfrak{X}$ open, let $g\in \mathfrak{X}\Rightarrow g\in U \Rightarrow \exists \Delta(q, R)\subseteq U$.

    *Note*
    $\Delta(g, R)\subseteq \mathfrak{X}$. If $g'\in \Delta(g, R) \Rightarrow g'\in \mathfrak{X}$.

- $\mathfrak{X}$ closed is similar,

    $$
    g\in \partial \mathfrak{X} \Rightarrow g \in\mathfrak{X}.
    $$


*prop c*
$f:U\to \C$ holomorphic, $\bar{R}\subseteq U$, 

$$
\int_{\partial R}f\dd z=0.
$$

which leads to the next corollary.

*Corollary*
$f:\Delta \overset{\text{holomorphic}}{\longrightarrow} \C, $ $C^1$ loop $\Gamma$ in $\Delta$, 

$$
\int_\Gamma f\dd z=0.
$$