1. Coursat IV.8
2. Coursat^\dag
3. Cauchy Integral Formula IV.2.6
4. Winding number IV.4

*proposition c*
$f:u\rightarrow \C$ holomorphic, $\displaystyle \bar{R} \subseteq u \Rightarrow \int_{\partial R}f \dd z =0$.

*remark* $f'$ may not be cont(continuous).
$f'$ continuous, an easy proof using Green can be given.

*proof*
Let $A = |\int_{\partial R}f \dd z =0|$. $\exists k$, fix $\epsilon > 0$, wills show $A\lt k\epsilon$.

Observed to notice that some lines are integrated in inverse orientation.

$$
A = |\int_{\partial R}f \dd z|
$$

Repeat to find

$$
R \supseteq R_1 \supseteq R_2 \supseteq \dots, \text{diam}(R_n) = \frac{\text{diam}(R)}{2^n}\rightarrow 0\\
\frac{A}{4^n} \le|\int_{\partial R_n}f \dd z|
$$

**compactness**

if $f'$ is continuous, the proof could be simplified. 1901 paper

*corollary*(Last time)
If $f:\Delta\rightarrow \C $ holomorphic, then 

- $\overset{C}{\Rightarrow}\int_{\partial R} f\dd z = 0, \forall \bar{R}\subseteq \Delta$
- $\overset{B}{\Rightarrow}$
- $\overset{A}{\Rightarrow}$

*Goursat**
If $f:U \rightarrow \C$ continuous, holomorphic in $U\setminus\{a\}$, 

$$
\Rightarrow \int_{\partial R} f\dd z = 0, \forall \bar{R} \subseteq U.
$$

*proof*
If $a\notin\bar{R}$, $U^\text{new} U\setminus\{a\}$ apply Goursat ($f\cdot U^\text{new}$).

If $a\in \bar{R}$, by subdivision, we may assume that $a$ is a corner for $R$.



*corollary*+
If $f:\Delta\rightarrow \C $ holomorphic in $\Delta\setminus\{a\}$, then 

- $\overset{C^+}{\Rightarrow}\int_{\partial R} f\dd z = 0, \forall \bar{R}\subseteq \Delta$
- $\overset{B}{\Rightarrow}$
- $\overset{A}{\Rightarrow}$


*Cauchy's Integral Formula* (CIF)(local version)
asumme $f:U\rightarrow \C$ holomorphic, $\bar{\Delta}\subseteq U, a\in \Delta$.

$$
f(a) = \frac{1}{2\pi \ii}\int_{\partial \Delta} \frac{f(z)}{z-a} \dd z
$$

orientation by default is counter-clockwise.

*proof*


*lemma*
*proof*
Step 1. If $a = c = $center of $\Delta$.
Let $z = c+ Re^{\ii t}$, then $\dd z = R\ii e^{\ii t}\dd t$, and $\frac{\dd z}{z-c}=\ii \dd t$ 

Step 2. $a\neq c$, will show 

$$
\int_{\partial \Delta} \frac{}{}
$$


Generalization
II. Winding Numbers (Index)
$\Gamma$ piecewise $C^1$ loop. $a\notin \{\Gamma\}$. Winding number $n(\Gamma, a) = \frac{1}{2\pi \ii}\int_\Gamma \frac{\dd z}{z-a}$.


*examples*
1. $\Gamma  =\partial \Delta = $ positive orientation.

CIF
$f:\Delta \rightarrow \C$ holomorphic, $\Gamma$ loop in $\Delta, a\notin \{\Gamma\}$


*remark*
1. $\Gamma = \Gamma_1 + \Gamma_2$, 

    $$
    n(\Gamma_1, a) = n(\Gamma, a) + n(\Gamma_2, a)\\
    \int_{\Gamma} \frac{\dd z}{z-a} = \int_{\Gamma_1}\frac{\dd z}{z-a} + \int_{\Gamma_2}\frac{\dd z}{z-a}
    $$

2. $n(-\Gamma, a) = -n(\Gamma, a)$
3. $n(\Gamma, a) \in \Z$
4. $n(\Gamma, a)$ is locally constant in $a\notin\{\Gamma\}$
5. $n(\Gamma, a) = 0$ if $a$ is in unbounded component of $\C\setminus \{\Gamma\}$

Already prove 1-2. Next time, prove 3-5.

