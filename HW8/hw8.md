## EX1.
note that $M_0(x)\ge 0\forall x\in F$
$M_0(x)<\infty$ a.e. in $F\iff \int_F M_0(x)dx <0\infty$

$[\log \frac 1{\delta(y)}]^{-1} |x-y|^{-1} \ge 0$ and measurable 

$\implies \int_F \int_a^b [\log \frac 1{\delta(y)}]^{-1} |x-y|^{-1} dydx= \int_a^b \int_F [\log \frac 1{\delta(y)}]^{-1} |x-y|^{-1} dxdy$

$\int_a^b \int_F [\log \frac 1{\delta(y)}]^{-1} |x-y|^{-1} dxdy = \int_a^b  [\log \frac 1{\delta(y)}]^{-1}  \int_F |x-y|^{-1} dxdy$
$\le \int_a^b  [\log \frac 1{\delta(y)}]^{-1} \int_{\delta(y) \le | x-y| \le 1} \frac 1{|x-y|}dxdy$
$=\int_a^b  [\log \frac 1{\delta(y)}]^{-1} \times  2 \int_{z=\delta(y)}^1 \frac 1z dzdy = \int_a^b  [\log \frac 1{\delta(y)}]^{-1} \times 2 [\log 1 - \log \delta(y)]dy=\int_a^b 2dy \le 2$

$\implies \int_F M_0dx$ is finite, therefore $M_0$ is finite a.e.

## EX2.
$x\notin F \stackrel{F^c\ open}{\implies} \exists r>0$ s.t. $I_x = [x-r,x+r] \in F^c$

$\implies \Delta = \min\{ \delta(x-r), \delta(x+r) \} > 0$, nad obviously $\forall x'\in I_x, \delta(x')\ge \Delta$
$\implies M_\lambda(x,F) \ge \int_{I_x} \frac{\Delta^\lambda}{|x-y|^{1+\lambda}}dy \ge 2\Delta^\lambda \int_{0}^r \frac 1{z^{1+\lambda}}dz=\infty$

## EX3.
WLOG suppose $f\ge 0$ for convinience, otherwise letting $\hat f = |f|$ and the proof can be still finish.

suppose $|\{f>0\}|>0$, letting $E_m=\{x:f(x)> \frac 1m\}$, then from $E_m\to \{f>0\}$ as $m\to\infty$ we know that $\exists M$ s.t. $|E_M|>0$, calling $E=E_M$, and let $r=\sup[\{|e|:e\in E\}\cup \{1\}]$

for $E$, we have
- $\int_E f dx \ge  \frac{|E|}M > 0$
- $E\subseteq \{y:|y|\le r\},r\ge 1$


for $|x|\ge 1$, letting $Q_x = \{y:|y-x|\le 2r|x| \}$ is a cube with edges parallel to the coordinate axis and centered at $x$, therefore

$f^*(x)\ge \frac 1{|Q_x|}\int_{Q_x} fdx$

besides, $y\in E\implies |y|\le r\implies |y-x| \le |x|+|y|\le |x|r+r|x|=2r|x|\implies y\in Q_x$

$\implies \int_{Q_x} fdx \ge \frac {|E|}M$

$\implies f^*(x)\ge \frac 1{|Q_x|}\frac{|E|}{M}\ge \frac {E}{2r^n M} \frac 1{|x|^n} \forall |x|\ge 1$

$\implies \exists c =  \frac 1{|Q_x|}\frac{|E|}{M}\ge \frac {E}{2r^n M}$ s.t. $f^*(x) \ge c\frac{1}{|x|^n}$



## EX4.
Let $M=\sup \phi$
use $\circledast$ to represent convolution
if $|x|>$, then $\phi_\epsilon(x)=\epsilon^{-n} \phi(\underbrace{x/\epsilon}_{\ge 1})=0$

Let $B_\epsilon = B_\epsilon(0)$, we have

$f\circledast g(x) - f(x) = \int (f(x-y)-f(x))\phi_\epsilon(y)dy = \int_{B_\epsilon} (f(x-y)-f(x))\phi_\epsilon(y)dy $


<!-- $=F\circledast \phi_\epsilon (x)$, where
- $F(x-y)=(f(x-y)-f(x))\implies F(z)=f(z)-f(x)$
-->
$\implies |f\circledast g(x)|\le \int_{B_\epsilon} |(f(x-y)-f(x))|\times |\phi_\epsilon(y)|dy \stackrel{symmetry}= \int_{B_\epsilon} |(f(x+y)-f(x))|\times |\phi_\epsilon(y)|dy = M \int_{B_\epsilon+x} |(f(z)-f(x))|dz$

$B_\epsilon+x \subseteq B_{2\epsilon}(x)$ is shrink regrlarly to $x$

$\implies M \int_{B_\epsilon+x} |(f(z)-f(x))|dz \to 0$ as $\epsilon\to 0$

$\implies f\circledast \phi_\epsilon(x)\to f(x)$ as $\epsilon\to 0$

## EX5.
Choose $A\subseteq E_1,B\subseteq E_2$ s.t. $|A|<\infty,|B|<\infty$,

the claim hold if $\exists t$ s.t. $|A\cap B+t|>0$

let $\mu(t)=|A\cap B+t|=\int_\mathbb R\chi_{A}(x)\chi_{B+t}(x)dx=\int_\mathbb R\chi_A(x)\chi_B(x-t)dx\ge 0$

$\int\mathbb R \mu(t)dt=\int_\mathbb R \chi_Adx\times \int_\mathbb R \chi_B dx =|A|\times |B|>0\implies \mu(t)$ take positive at some points.

$\implies \exists t$ s.t. $|A\cap B+t|>0\implies \{a-\hat b:a\in A,\hat b\in B+t\}$ contain an interval
$\implies \{x_1-x_2:x_1\in E_1, x_2\in E_2\}\supseteq \{a-b:a\in A,b\in B\}=\{a-\hat b:a\in A,\hat b\in B+t\} + t$ contain an interval.