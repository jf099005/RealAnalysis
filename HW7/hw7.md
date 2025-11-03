# EX1.
(ref. https://math.stackexchange.com/questions/4797313/if-f-k-oversetm-longrightarrowf-and-and-int-e-f-kp-le-m-then-int)
$\int_E |f-f_k|^p=\int_0^\infty p\alpha^{p-1} \omega_{|f-f_k|}(\alpha)d\alpha\to 0$ as $k\to\infty$
$\implies \lim_{k\to\infty} \alpha^{p-1} \omega_{|f-f_k|}(\alpha) =0$ a.e. on $[0,\infty)$
$\implies \lim_{k\to\infty} \omega_{|f-f_k|}(\alpha) =0$ a.e. on $[0,\infty)$
$\implies \lim_{k\to\infty} |\{|f_k-f|>\alpha\}|=0\forall \alpha > 0$
$\implies f_k\stackrel m\to f$
$\implies |f_k|^p\stackrel m\to |f|^p$

$\implies \exists \{f_{n_K}\}$ s.t. $f_{n_k}\to f$ a.e.

$\implies \int_E |f|^p = \int_E \liminf_{k\to\infty} |f_{n_k}|^p\le \liminf_{k\to\infty} \int_E |f_{n_k}|^p \le M$ by Fatou's Lemma



# EX2.
Let $f(x) = \frac 1{\log (x+5)}$, then $\lim_{x\to\infty} f(x)=0$, but
$\log(x+5)^p\in o(x+5)\forall p>0 \implies \exists R$ s.t. $\log(x+5)^p < x+5\forall x > R$

$\implies \int_0^\infty f(x)^pdx \ge \int_R^\infty f(x)^p dx \ge \int_R^\infty \frac 1x dx=\infty$

therefore, $f(x)\notin L^p(0,\infty)$

# EX3.
## a.
$|f_k|$ are positive
$\implies \sum\int_E |f_k(x)|=\int_E \sum |f_k(x)|<\infty\forall x$
$\implies \sum |f_k(x)|$ is finite a.e.

$\implies \sum f_k$ converge absolutely a.e.

## b.
We can claim $\sum_k \int_{[0,1]} |a_k|\times |x-r_k|^{-\frac 12}<\infty$ and therefore $\sum_k a_k\times |x-r_k|^{-\frac 12}$ converge absolutely by subproblem a:

<!-- WLOG suppose $a_k>0\forall k$ -->

$|\int_0^1 \frac{a_k}{\sqrt{|x-r_k|}}dx|=|a_k [\int_0^{r_k} \frac 1{\sqrt{r_k-x}}dx + \int_{r_k}^1 \frac 1{\sqrt{x-r_k}}dx]|=|a_k[2\sqrt {r_k} + 2\sqrt{1-r_k}]|\le 4 |a_k|$

$\implies \sum_k \int_{[0,1]} |a_k|\times |x-r_k|^{-\frac 12}\le \sum_k 4|a_k|<\infty$, and the claim hold.

# EX4.
Let $P_n=\{f>\frac 1n\},N_n = \{f<-\frac 1n\}$, both measurable
$0=\int_{P_n} f\ge \inf_{P_n} f\times |{P_n}| \ge \frac 1n \times |{P_n}|\implies |{P_n}|=0$
$0=\int_{N_n} f \le \sup_{N_n} f\times |N_n|\le -\frac 1n |N_n|\implies |N_n|=0$

$\implies |\{f>0\}|=|\cup_n P_n|=\lim_{n\to\infty} |P_n|=0$, and so as $N_n$

$\implies |\{f\neq 0\}|\le |\{f>0\}| + |\{f<0\}|=0$, $f=0$ a.e.

# EX5.
(ref. https://math.stackexchange.com/questions/3984200/f-in-lp-iff-sum-k-in-mathbbz2kp-lambda-f2k-infty)

if $f\in L^p$, then
$\sum_{k=-\infty}^\infty 2^{kp}\omega(2^k) = \sum_{k=-\infty}^\infty  \frac{p}{1-2^{-p}} \int_{2^{k-1}}^{2^k} \alpha^{p-1} d\alpha\omega(2^k) \le \frac{p}{1-2^{-p}} \sum_{k=-\infty}^\infty \int_{2^{k-1}}^{2^k} \alpha^{p-1} \omega(\alpha)d\alpha=\frac 1{1-2^{-p}}\int_{-\infty}^{\infty} p\alpha^{p-1} \omega(\alpha)d\alpha=\frac 1{1-2^{-p}}\int f^p<\infty$

For the converse side, 
$\sum_{k=-\infty}^\infty 2^{pk}\omega(2^k)<\infty \implies \omega(\alpha)<\infty \forall \alpha>0\implies f\in L^p$ by Exercise 16.

