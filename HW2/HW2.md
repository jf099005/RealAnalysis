## EX1.
(ref. https://math.stackexchange.com/questions/2115139/is-lebesgue-outer-measure-continuous-from-above-for-sets-with-finite-lebesgue-ou?utm_source=chatgpt.com)

From Theorem 3.38, we know that the Vitari set $V$, which form by selecting exactly one element from each equality class of irrational numbres in $[-1,1]$ separately, is nonmeasurable.

Define $\{r_k\}_{k=1}^\infty$ be all rational numbres at $[0,1]$, let $V_k=\{v+r_k:v\in V\}$, we can find that each $V_k$ is disjoint
- otherwise, $V_m\cap V_n\neq \emptyset\implies v_1+r_m=v_2+r_n$ for some $v_1,v_2\in V$
$\implies v_1-v_2=r_2-r_1\in\mathbb Q\implies v_1=v_2\implies r_m=r_n,m=n$, contradiction

Besides, it's from definition that $\cup_{k=1}^\infty V_k\subseteq[-1, 2]$

define $E_k=\cup_{j=k}^\infty V_k$, then we can find that
- $E_k$ is decreasing to $E=\emptyset$, which from the proposition that $V_k$ is disjoint.
($a\in[0,2]\implies a$ belong to at most one $V_k$)

- $|E_k|_e \ge |V|_e$
Because $V$ have nonzero measure, and $V_k$ is just the translate of $V$, therefore they have the same outer measure
$\implies |E_k|_e\ge |V_k|_e=|V|_e$
$\implies \lim_{k\to\infty} |E_k|_e\ge |V|_e > 0=|E|_e$


## EX2.
If $|E|=\infty$, then no matter $A$ is finite or $|A|_e=\infty$, both side of the equation are $\infty$ and therefore trivial

Following we assume $|E|<\infty$

First, suppose $B_k\subseteq A$ is closed and $|B_k|\ge |A|_i-\frac 1k$, $\lim_{k\to\infty} |B_k|=|A|_i$

$|E|=|B_k|+|E-B_k|\ge |A|_i-\frac 1k+|E-B_k|\ge |A|_i+|E-A|_e-\frac 1k\forall k$

$\implies|E|\ge |A|_i+|E-A|_e$

For the converse part, assume $|E|>|A|_i+|E-A|_e$, i.e.
$|E|-|A|_i-d>|E-A|_e$ for some $d$

Then there exist $G\supseteq E-A$, $G$ is open, and $|G|\le |E-A|_e+\epsilon$ for some $0<\epsilon<d/2$

Take $H=E-G$, we have $|H|=|E|-|E\cap G|$
$\ge|E|-|E-A|_e-\epsilon \ge |E|-(|E|-|A|_i-d)-d/2=|A|_i+d/2$

Therefore, there's an measurable set $H\subseteq A$ with $|H| > |A|_i$, this cause a contradiction from $|H|\le \sup_{H':H'\ is\ F_\sigma,H'\subseteq A}|H'|=|A|_i$

$\implies |E|\ge |A|_i+|E-A|_e$, and thus we obtain the equality.

## EX3.
(motivated by https://www.facebook.com/groups/120223891488/posts/10161752568386489/)

Let $f$ be the Cantor Lebesgue function, for each $x$ in Cantor set, $x=\sum_{k=1}^\infty a_k3^{-k},$ where $a_k\in\{0,2\}\forall k$, $f$ will map $x$ to $y=\sum_{k=1}^\infty b_k2^{-k}$, 
where $b_k=\begin{cases}
0 &if\ a_k=0\\
1 &if\ a_k=2
\end{cases}$

Therefore, the image of the Cantor set will be $\{\sum_{k=1}^\infty b_{k}2^{-k}|b_k\in\{0,1\}\}=[0,1]$

From Corollary 3.39, $[0,1]$ contain a nonmeasurable subset $U$, and the preimage of $U$, i.e. $f^{-1}(U)$ is a subset of Cantor set and thus has measure zero.

Therefore, $f^{-1}(U)$ is a measurable set, and the function $f$ map it onto a nonmeasurable set.

## EX4.
for any collection of intervals $I=\{I_k\}_{k=1}^\infty$, define $I_h=\{I_k^h\}_{k=1}^\infty$, where $I_k^h = \{a + h\}$, we can easily to see
- $I$ covers $E$ $\iff I_h$ covers $E_h$

Therefore, there's an one-to-one relation between $\mathbb I=\{I:I\ cover\ E\}$ and $\mathbb I_h=\{I_h:I_h\ cover\ E_h\}$ and $\sum_{k=1}^\infty |I_k|=\sum_{k=1}^\infty |I_k^h|$ for each one-to-one pair.

Therefore, $|E|_e = \sup_{I\in \mathbb I}\sum_{k=1}^\infty|I_k|= |E_h|_e=\sup_{I_h\in \mathbb I_h}\sum_{k=1}^\infty |I_h^k|$

samely, for any $F$ is closed, define $F_h=\{x+h:x\in F\}$, we have $F\subseteq E\iff F_h\subseteq E_h$

Therefore, $\sup_{F\subseteq E,F\ closed}|F|=\sup_{F\subseteq E,F\ closed}|F|_e=\sup_{F_h\subseteq E_h,F_h\ closed}|F_h|$
$\implies |E|_i=|E_h|_i$

Therefore, $|E|_i=|E|_e\iff |E_h|_i=|E_h|_e$
$E$ measurable iff $E_h$ measurable.