## EX1.
choose
$\chi_{K_1} = [0,\frac 12]$
$\chi_{K_2}=[0,\frac 14]$
...
$\chi_{K_n}=[0,2^{-n}]$
...

Then $f_{\chi_{K_j}}\to \begin{cases}
0&x\in (0,1]\\
1&x=0
\end{cases}$

which equal to $0$ except except $\{0\}$, which is a measure zero set.

## EX2.
if $\limsup_{y\to x}g(y) = g(x)-d < g(x)$ (i.e. $d>0$), then
$\exists \delta>0$ s.t. $\sup_{y\in B_{\delta}(x) \backslash \{x\}} g(y) < g(x)-d/2$, and we can choose $\delta < r$
However, $\sup_{y\in B_{\delta}(x) \backslash \{x\}}g(y)=\sup_{y\in B_{\delta}(x) \backslash \{x\}} \sup_{y'\in B_r(y)} f(y')$
$= \sup_{y'\in\cup_{y\in B_{\delta}(x) \backslash \{x\}} B_r(y)} f(y') < g(x)$

- $B_r(x)\subset\cup_{y\in B_{\delta}(x) \backslash \{x\}} B_r(y)$

$\implies \sup_{y'\in\cup_{y\in B_{\delta}(x) \backslash \{x\}} B_r(y)} f(y') \ge \sup_{B_r(x)}f =g(x)$, which make a contradiction

therefore, $g(x)$ is LSC

Besides, we can notice the formula $B_r(x)\subset\cup_{y\in B_{\delta}(x) \backslash \{x\}} B_r(y)$ also hold for closed balls, therefore the proposition still hold if we replace the open balls by closed.

for the case of $h(x)$, we take $g(x)=-h(x)$, then $g(x)=\inf_{B_r(x)}-f$ and therefore LSC $\implies h=-g$ is USC

## EX3.

<!-- Define $g_n(x)=\sup_{k\ge n}f_k(x)$ and $g(x)=\lim_{n\to\infty} g_n(x)=\limsup_{k\to\infty} f_k(x)$

$g_n(x)\to g(x)$ pointwisely, and $-\infty < g(x)<\infty \forall x\in E$ from $|g_n(x)|\le \sup_{n\ge k} |f_k(x)|\le M_x\forall x \in E$

by Egorov theorem, $\exists F\subseteq E$ closed with $|E-F|<\epsilon$ and $g_n\stackrel{unif.}{\to} g$ at $F$

- 1. for the case $E$ is finite(i.e. compact),  -->
First, we consider the case $E$ is bounded.

define $g_k(x)=\sup_{1\le j\le k}f_j(x)$ and $g(x)=\sup_{k\in\mathbb N} f(x)$, then $g_k\to g$ pointwisely, and $g(x)\le M_x\forall x$ and thererfore finite.

$g_k$ measurable and finite, therefore by Lusin's theorem $\exists F_k\subseteq E$ is closed and $g_k$ continuous at $F_k$ and $|E-F_k|<\epsilon\times 2^{-k-1}$
Let $F_C=\cap_{k=1}^\infty F_k$, then which is closed with $|E-F_C|=|\cup_k (E-F_k)|\le \sum_k |E-F_k|\le \epsilon/2$, and all $g_k$ continuous at $F_C$

Besides, by Egorov theorem $\exists F_U\subseteq E$ closed, $|E-F|<\epsilon/2$ and $g_k\to g$ uniformly on $F_U$

Take $F=F_C\cap F_U$, then $F$ will be compact, $|E-F|\le |E-F_C|+|E-F_U|\le \epsilon$ and $g_k$ cont. at $F$, $g_k\to g$ uniformly.

$\implies g$ is a countinuous function at $F$
Take $M=\sup_{F} |g|$, because $F$ is compact and $g$ is continuous at $F$, $M<\infty$

Therefore, we can find $F$ closed with $|E-F|<\epsilon$, $M<\infty$ s.t. $f_k(x)\le g(x)\le M\forall x\in F$


for the case $E$ unbounded, take $E_N=B_{N}(0)$, we can make $|E-E_N|<\epsilon/2$ as long as $N$ sufficiently large.

Because $E_N$ finite, we can find $M>0, F\subseteq E_N$ closed with $|E_N-F|<\epsilon/2$ and $f_k(x)<M\forall x\in F$
Besides, $|E-F|\le |E-E_N|+|E_N-F|\le \epsilon$, therefore such $M,F$ satisfy the request.

<!-- define $g(x)=\sup_{k} f_k(x)$,  --> 

## EX4.

#### $f+g$ case
$\lim_{k\to\infty}|\{x:|(f+g)(x)-(f_k+g_k)(x)|>\epsilon\}|$

$\le \lim_{k\to\infty}|\{x:|(f-f_k)(x)+(g-g_k)(x)|>\epsilon\}|$

$\le \lim_{k\to\infty}|\{x:|(f-f_k)(x)|>\epsilon\} \cup \{x:|(g-g_k)(x)|>\epsilon\}|$
$\le \lim_{k\to\infty}|\{x:|(f-f_k)(x)|>\epsilon\} | + |\{x:|(g-g_k)(x)|>\epsilon\}|$
$=0+0=0$


#### $f\times g$ case
fix $\eta>0$

$|\{|fg-f_kg_k|>\epsilon\}|\le |\{|f|\times |g-g_k| > \epsilon/2\}| + |\{|g_k|\times |f-f_k|>\epsilon/2\}|$



for any $N>0$, we have $\{|f|\times |g-g_k| > \epsilon/2\} = \{x:|f(x)|>N, |f|\times |g-g_k| \ge \epsilon/4\} \cup \{x:|f(x)|\le N,|f|\times |g-g_k| \ge \epsilon/4\}$

$\subseteq \{x:|f(x)|>N, |f|\times |g-g_k| \ge \epsilon/4\} \cup \{x:|f|\times |g-g_k| \ge \epsilon/(4N)\}$

from $|E|<\infty$, we can pick sufficiently large $N$ s.t. $|\{ x:|f(x)| > N \}|<\eta /2$

besides, when $N$ fixed, we can choose $k$ sufficiently large s.t. $|\{x:|g-g_k| \ge \epsilon/(4N)\}|<\eta/2$

$\implies \{|f|\times |g-g_k|>\epsilon/2\} \le |\{x:|f(x)|>N, |f|\times |g-g_k|\ge \epsilon/4\} |+| \{x:|f(x)|\le N,|f|\times |g-g_k| \ge \epsilon/4\} | \le \eta$ as $k$ sufficently large

replace the role of $f,g_k$, we can also prove $|\{|g_k|\times |f-f_k|>\epsilon/2\}|<\eta$ as $k$ sufficeintly large

$\implies |\{x:|f(x)g(x)-f_k(x)g_k(x)|>\epsilon\}|\to 0$ as $k\to\infty$, therefore $f_kg_k\to fg$ in measure as $|E|<\infty$

#### $f/g$ case
Because we have prove the $f\times g$ case, it is sufficient to show $\frac 1{g_k}\stackrel{m}\to \frac 1g$


$g\neq 0$ a.e. $\implies |\{|g|<\frac 1k\}|\to 0$ as $k\to\infty$

fix $\eta>0$
$\{|\frac{1}{g}-\frac 1{g_k}|>\epsilon\}=\{|\frac{1}{g}-\frac 1{g_k}|>\epsilon, |g|<\frac 1N\} + \{|\frac{1}{g}-\frac 1{g_k}|>\epsilon, |g|>\frac 1N\}$
$\subseteq \{|g|\le \frac 1N\}\cup\{|g|\ge \frac 1N,|\frac{g-g_k}{g_k g}| <\epsilon\}$

choose $N$ sufficiently large s.t. $|\{|g|\le \frac 1N\}|<\eta/2$, and by Egorov theorem choose $F\subseteq E$ is closed, $K\in\mathbb N$ s.t. 
- $|E-F|<\eta/2$
- $|g(x)-g_k(x)|<\min\{\frac{1}{2N},\frac{\epsilon}{2N^2}\}\forall k\ge K, x\in F$

then for $k\ge K$, we have
- $|\{|g|\le \frac 1N\}|\le \eta/2$
- $\{|g|\ge \frac 1N,|\frac{g-g_k}{g_k g}| <\epsilon\}\subseteq \{|\frac{g-g_k}{\frac 1{N}\times \frac 1{2N}}|<\epsilon\}\subseteq \{|g-g_k|\le \frac{\epsilon}{2N^2}\}\subseteq E-F$

$\implies |\{|\frac{1}{g}-\frac 1{g_k}|>\epsilon\}|\le |\{|g|\le \frac 1N\}| + |\{|g|\ge \frac 1N,|\frac{g-g_k}{g_k g}| <\epsilon\}|$
$\le \eta+|E-F|\le \eta$

$\implies \forall \eta>0,\exists K$ s.t. $|\{|\frac 1g- \frac 1{g_k}|>\epsilon\}| <\epsilon\forall k\ge K$

$\implies \frac 1{g_k}\stackrel{m}{\to} \frac 1g$

and by the $f\times g$ case, $\frac{f_k}{g_k}\stackrel{m}\to \frac fg$


## EX5.
fix $a\in E$
if $f_k\to f$, let $A_k=\{x:f_k(x)>a\}$ and $A=\{x: f(x)>a\}$

from the increasing property of $f_k$, we know that $A_k$ will increase to $A$, i.e. $A=\limsup_{k\to\infty} A_k$, therefore $f(a)=|A|=\lim_{k\to\infty} |A_k|=\lim_{k\to\infty} f_k(a)$

if $f_k\stackrel m\to f$, fix any $\epsilon>0$, we claim
$\omega_f(a+\epsilon) \le \liminf_{k\to\infty} \omega_{f_k}(a)\le \limsup_{k\to\infty}\omega_{f_k}(a)\le \omega_f(a-\epsilon)$
- for any $\eta>0$, exist $K$ and a set $F$ s.t. $|E-F|<\eta$ and $|f_k(x)-f(x)|<\epsilon\forall x\in F,k\ge K$
therefore, $f_k(x)>a\implies f(x) > a-\epsilon\forall x\in F, k\ge K$
$\implies \{f_k(x) > a\}\subseteq (E-F)\cup\{f(x) > a-\epsilon\}$
$\implies \omega_{f_k}(a) \le |E-F|+\omega_f(a-\epsilon)=\eta + \omega_f(a-\epsilon)\forall k\ge K$
$\implies\limsup_{k\to\infty} \omega_{f_k}(a) \le \omega_f(a-\epsilon)$
- with the symmetric step, we can also prove $\omega_f(a+\epsilon) \le \liminf_{k\to\infty} \omega_{f_k}(a)$

$\omega_f$ continuous at $a\iff \lim_{\epsilon\to 0}\omega_f(a+\epsilon) = \lim_{\epsilon\to 0}\omega_f(a-\epsilon)=\omega_f(a)$

Therefore, at $a$ which $\omega_f$ is continuous, $\lim_{\epsilon\to 0}\omega_f(a+\epsilon)=\liminf_{k\to\infty} \omega_k(a)=\limsup_{k\to\infty} \omega_k(a)=\lim_{\epsilon\to 0}\omega_f(a-\epsilon)=\omega_f(a)$

$\implies \lim_{k\to\infty} \omega_{f_k}(a)=\omega_f(a)$