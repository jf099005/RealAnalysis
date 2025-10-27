## EX1.
https://math.stackexchange.com/questions/215215/showing-a-function-of-two-variables-is-measurable


Let $f_n(x,y) = f(x, \frac{k}{n})$, where $\frac kn \le y< \frac{k+1}n$

$\{f_n < a\} = \cup_{k=0}^n\{ x:f(x,\frac kn)< a \} \times [\frac kn,\frac{k+1}n)$

From the continuity of $x$, $\{ x:f(x,\frac kn)< a \}$ is measurable, and therefore \cup_{k=0}^n\{ x:f(x,\frac kn)< a \} \times [\frac kn,\frac{k+1}n)$ measurable, $f_n$ is a measurable function.

From the continuity of $y$, $\lim_{n\to\infty} f_n = f$, and then from Theroem 4.12 $f$ is measurable.




## EX2.
Let $C_n = \{a_1f_1+a_2f_2+...+a_Nf_N|N\in \mathbb N,a_k\ge 0,f_k\in U_n\forall k,\sum_{k=1}^N a_k=1\}$ be the minimum convex set contain $U_n$,
first, we prove any simple function is within $C_n$:
- first, for any set $E\subseteq [0,1),c\in \mathbb R$, we have $c\chi_{E}\in C_n$:
    - if $c\le 0$, then the solution is trivial
    - if $|E|<\frac 1n$, then obviously $c\times \chi_E\in C_n$
    - if $|E|\ge \frac 1n$, Let $E_k=E\cap [\frac {k-1}{n+1},\frac k{n+1})$, then $E=\cup_{k=1}^{n+1} E_k$ and $|E_k|\le \frac 1{n+1}<\frac 1n$
    $\implies (n+1) c\chi_{E_k}\in C_n\forall k=1,2,...,n+1$
    $\implies \frac 1{n+1}[c(n+1)\chi_{E_1}]+\frac 1{n+1}[c(n+1)\chi_{E_{2}}]+...+\frac 1{n+1}[c(n+1)\chi_{E_{n+1}}]\in C_n$, which is equal to $c \chi_E$

- second, for any disjoint sets $E_1,...,E_N$ and constants $a_1,...,a_N$, $\sum_{k=1}^N a_k \chi_{E_k}=\sum_{k=1}^N \frac 1N[\underbrace{a_kN \chi_{E_k}}_{within\ C_n}]\in C_n$

Therefore, all simple functions are within $C_n$

Now assume $f$ is a measurable functions, then by above proposition we can find a sequence $\{f_1,f_2,...\}$ s.t. $\lim_{k\to\infty} f_k= 2f$

Besides, by Egorov theorem we can find $F\subseteq [0,1)$ and $K$ s.t. $\sup_F|f_k-2f|<\frac 1{2n}\forall k\ge K$ and $|E-F|<\frac 1{2n}$

$\implies \sup_F |2f - f_{K+1}| < \frac 1{2n}\implies |\{x:(f-f_K)(x)>\frac 1n\}|\le |E-F|< \frac 1n$

$\implies 2f(x)-f_K(x)\in U_n\subseteq C_n$, and we know $f_K\in C_N$ by previous proposition

$\implies \frac 12 (2f-f_K) + \frac 12(f_K)=f\in C_n$

$\implies S\subseteq C_n$ and obviously $C_n\subseteq S$, therefore $S=C_n\forall n$

## EX3.
use $\partial_x f$ to represent $\frac{\partial}{\partial x} f,$ and Let $M$ be the upper bound of $\partial_x f$ in $[0,1]$


$\frac d{dx}\int_0^1 f(x,y)dy=\lim_{\delta \to 0}\frac{\int_0^1 f(x+\delta,y)dy- \int_0^1 f(x,y)dy}{\delta}$
$=\lim_{\delta \to 0}\int_0^1 \frac{f(x+\delta, y)-f(x,y)}{\delta}dy$

Therefore, $|\frac d{dx}\int_0^1 f(x,y)dy - \int_0^1 \partial_x f(x,y)dy|=\lim_{\delta\to 0} |\int_0^1  \frac{f(x+\delta, y)-f(x,y)}{\delta}- \partial_x f(x,y)dy|\le \lim_{\delta\to 0} \int_0^1 | \frac{f(x+\delta, y)-f(x,y)}{\delta}- \partial_x f(x,y)|dy$
$\le \lim_{k\to \infty} \int_0^1 | \frac{f(x+\frac 1k, y)-f(x,y)}{\frac 1k}- \partial_x f(x,y)|dy$


Let $f_k(x,y)=\frac{f(x+\frac 1k, y)-f(x,y)}{\frac 1k}$, then $f_k(x,y)\to \partial_x f(x,y)$ as $k\to\infty$
therefore, fix any $\eta>0$, $\exists F\subseteq [0,1],K$ s.t. $|E-F|<\eta/2$ and $|f_k(X,y)-f(x,y)|\le \eta/2\forall k\ge K$

$\implies$ for $k\ge K$, $\int_0^1 | \frac{f(x+\frac 1k, y)-f(x,y)}{\frac 1k}- \partial_x f(x,y)|dy=\int_0^1 |f_k(x,y)-\partial_x f(x,y)|dy$
$\le \int_F |f_k(x,y)-\partial_x f(x,y)|dy + \int_{E-F} |f_k(x,y)-\partial_x f(x,y)|dy$
$\le \int_F \eta/2dy + M|E-F|\le \eta$

## EX4.
for any function $F:E\to\mathbb R$, define $F^+=\max(0, F)$ and $F^-=\max(0,-F)$

Let $f=f^+-f^-$, $f\in L(0,1)\implies \int_0^1 f^+dx\ge 0$ and $\int_0^1 f^-dx\ge 0$ finite

$\implies \int_0^1 x^k f^+dx = \int_0^1 (x^k f)^+ dx\le \int_0^1 f^+ dx$ and $\int_0^1 x^k f^- dx = \int_0^1 (x^k f)^- dx\le \int_0^1 f^- dx$ finite

$\implies$ By definition $\int_0^1 x^k fdx$ exist and finite, hence $x^k f\in L(0,1)$

Besides, $x^k f \le |f|$ in $[0,1]$, therefore by Fatou's Lemma we have $\lim_{k\to\infty} \int_0^1 |x^k f |dx \le \int_0^1 |\lim_{k\to\infty} x^k f|dx =\int_0^1 0 dx = 0$
$\implies \int_0^1 x^k fdx \to 0$ as $k\to\infty$

## EX5.
fix $\epsilon>0$,

$\exists F\subseteq E$ s.t. $|E-F|<\frac \epsilon{3M}$ and $f_k\to f$ uniformly on $F$.

Therefore, we can choose sufficiently large $K$ s.t. $\sup_F |f_k- f| < \frac{\epsilon}{3M} \forall k\ge K$

$\implies \forall k\ge K$, we have 
$|\int_E f_k dx - \int_E f dx|\le |\int_E f_k dx - \int_F f_k dx| + |\int_F f_k dx - \int_F f dx| + |\int_F fdx - \int_E f dx|$
$\le |E - F|M + |F|\times \frac{\epsilon}{3M} + |E-F|M < \epsilon/3 + \epsilon/3+\epsilon/3 = \epsilon$

$\implies \int_E f_k dx \to \int_E fdx$ as $k\to\infty$ by definition.
