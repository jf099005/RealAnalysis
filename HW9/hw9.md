# EX1.
we will directly prove the case that $y$-dimension is the increasing function $f(h)$:

Let $H$ be the set of all heights, and the set $K=\{Rect(h, f(h)):h\in H\}$ cover $E$, where $Rect(a, b)$ represent the rectangle of width $a$ and height $b$(omit the axis)

let $h_1^* = \sup H,f_1^* = \sup_{h\in H} f(h)$, and pick $h_1\in H$ s.t. $f(h_1) \ge f_1^*$ and $h_1 \ge h_1^*$, which can be chosen by following process
- pick $h_1^x\in H$ s.t. $h_1^x \ge \frac 12 h_1^*$
- pick $h_1^y\in H$ s.t. $f(h_1^y) \ge \frac 12 f^*_1$
- let $h_1=\max(h_1^x, h_1^y)$

let $Q_1 = Rect(h_1, f(h_1))$

split $K$ into $K_1,K_1'$, where all cube within $K_1$ are disjoint with $Q_1$, and all cube in $K_1'$ are intersect with $Q_1$.

We claim that $K_1'$ is covered by $5Q_1$:
- WLOG suppose the origin located at the center of $Q_1$, i.e. the upper right corner of $Q_1$ is $(\frac {h_1}2, \frac 12 f(h_1) )$
For any $Rect(h', f(h')),h'\neq h_1$, we have $h'\le 2 h_1$ and $f(h') \le f_1^* \le 2 f(h_1)$
$\implies$  if $Rect(h', f(h'))$ is intersect with $Q_1$,the right upper corner of $Rect(h', f(h'))$ is at the lower-left of $(\frac 52 h_1, \frac 52 f(h_1))\implies Rect(h', f(h'))\subseteq Q_1$

Therefore, the set $K_1,K_1'$ have the same property as in Lemma 7.4, therefore we can prove Lemma 7.4 is still hold with $\beta = 5^{-2}$



<!-- samely, continue this process, we can construct $Q_2,Q_2,...$, $K_2,K_3,...$ and $K'_2,K_3',...$ -->

<!-- with the same process of the proof of 7.4, $K=K_1=K_2'\cup K_3'\cup ...\cup K_n'\cup K_{n+1}$

WLOG suppose $h_k\to 0$ as $k\to\infty$ (otherwise ), we have -->

# EX2.
by the property of Riemann-Stieltjes integral, $\int_a^b \phi df = \int_a^b \phi d(g+h)=\int_a^b \phi dg + \int_a^b dh$

$g$ is abs. continuous $\implies g$ is B.V. $\implies \int_a^b \phi dg$ is exist, and by thm 7.32 is equal to $\int_a^b \phi g' dx$

$\implies \int_a^b \phi df = \int_a^b \phi dh + \int_a^b \phi g' dx$

# EX3.
The $\to$ part is trivial, so we only prove the converse part

fix $\epsilon>0$
Let $\delta>0$ s.t. for any finite collection of non-overlapping interval $\{[a_i, b_i]\}_{i=1}^N$ with $\sum_{k=1}^N |b_k-a_k|<\delta$, the sum
$\sum_{j=1}^N |f(b_j)-f(a_j)| < \epsilon$


For any countable collections of nonoverlapping intervals $\{[A_j, B_j]\}$, we have
- if $\sum_{j=1}^\infty |B_j - A_j|<\delta$, then $\sum_{j=1}^N |B_j - A_j|<\delta \forall N \in \mathbb N$
$\implies \sum_{j=1}^N |f(B_j)-f(A_j)|<\epsilon\forall N\in\mathbb N$
$\implies \lim_{N\to\infty} \sum_{j=1}^N |f(B_j)-f(A_j)|\le \epsilon < 2\epsilon$

$\implies \sum_{j=1}^\infty \sum_{j=1}^N |f(B_j)-f(A_j)|< 2\epsilon$ if $\sum_{j=1}^\infty |B_j-A_j|<\delta$
$\implies f$ is abs. cont.

# EX4.

First, we prove the case that $|\cup_{B\in \mathcal F}B|_e <\infty$:

Let $K_1 = \mathcal F$,
take $R_1^* = \sup\{rad(B):B\in K_1\}$, choose $B_1$ from $\mathcal F$ s.t. $rad(B_1) > \frac 12 R_1^*$

split $K_1 = K_2\cup K_2'$ s.t. all elements in $K_2$ disjoint with $B_1$ and all elements in $K_2'$ has nonempty intersection with $B_1$

if $B' \in K_2'$, then $B'\subseteq 5B_1$:
- WLOG suppose $B_1$ centered at origin
- suppose $B'$ centered at $c$, radius $R' < 2rad(B_1)$, i.e. $|c-0| \le R'+rad(B_1)$
$x\in B'\iff |x-c|<R' \implies |x| \le |x-c| + |c| \le R'+R'+rad(B_1) < 5 rad(B_1) \implies x\in 5B_1$

Therefore, $\cup_{B'\in K_2'} B' \subseteq 5B_1$.

continue this process, we obtain $B_2,B_3,...$, $K_2,K_3,...$ and $K_2',K_3',...$, because the finiteness of $|\cup_{B\in \mathcal F} B|$, $rad(B_k)\to 0$ as $k\to\infty$, and therefore $5B_1\cup5B_2\cup...$ will cover the entire $\mathcal F$, and obviously the propositions hold

if $|\cup_{B\in \mathcal F} B|=\infty$, first only consider balls within $B_k(0)$ and the requests hold, then take $k\to\infty$ we can obtain the same conclusion.




# EX5.
fix $\epsilon>0$
$V$ is abs. cont. $\implies\exists \delta>0$ s.t.
$\forall \{[a_j, b_j]\}$ with $\sum_j b_i-a_j < \delta$, we have $\sum_j |V(b_j)-V(a_j)| < \epsilon$

by the proposition of $V$, $|V(b_j)- V(a_j)| \ge |f(b_j)- f(a_j)|$

$\implies \sum_j |f(b_j)- f(a_j)|<\epsilon$

$\implies f$ is abs. cont.



