## EX1.
First, $T$ is one-to-one mapping, hence the image of disjoint sets will also be disjoint.
Let $I=[(k-1)2^{-n}, k2^{-n}]$ is an interval of measure $2^{-n}$, then $I$ can be written as 
$I=\{\sum_{\ell=1}^{n-1} 2^{-\ell}a_\ell+\sum_{j=n}^\infty 2^{-j}b_j:b_j\in\{0,1\}\}$ for fixed $a_1,a_2,...,a_{n-1}$

$\implies T(I)=\{\sum_{\ell=1}^{n-1} 2^{-k_\ell}a_\ell + \sum_{j=n}^\infty 2^{-k_j} b_j:b_j\in\{0,1\} \}$
$=\left\{\sum_{j=1}^\infty d_j 2^{-j}:d_j=\begin{cases}a_j&if\ j\in \{k_1,...,k_{n-1}\}\\
b_j\in\{0,1\}&else
\end{cases}\right\}$

Let $K=\max\{k_\ell:1\le \ell < n\}$, we have
$T(I)=\left\{\sum_{j=1}^{K} d_j2^{-j} + \sum_{j=K+1}^\infty b_j2^{-j} :b_j\in\{0,1\},d_j=\begin{cases}a_j&if\ j\in \{k_1,...,k_{n-1}\}\\
b_j\in\{0,1\}&else
\end{cases} \right\}$

$=\cup_{d_1,d_2,...,d_K} \{\sum_{j=1}^{K} d_j2^{-j} + \sum_{j=K+1}^\infty b_j2^{-j} :b_j\in\{0,1\}\}$

note that $\{\sum_{j=1}^{K} d_j2^{-j} + \sum_{j=K+1}^\infty b_j2^{-j} :b_j\in\{0,1\}\}$ is an interval of measure $2^{-K}$ for any fixed $d_1,d_2,...,d_K$, and is disjoint (except endpoint) for different $d_1,..,d_K$ (and thus the intersection of all sets are measure zero)

besides, there are $2^{K-n}$ valid conbination of $d_1,d_2,...,d_K$, therefore the total measure is
$|T(I)|=|\cup_{d_1,...,d_K}\{\sum_{j=1}^{K} d_j2^{-j} + \sum_{j=K+1}^\infty b_j2^{-j} :b_j\in\{0,1\}\}|$
$=2^{K-n}\times 2^{-K}=2^{-n}=|I|$

Therefore, the measure of the image of $T$ is invariant with its domain

for any open sets $G$, it can be written as an disjoint union of countable many intervals of the form $[k2^{-n}, (k+1)2^{-n}],k,n\in\mathbb N$, therefore we can conclude the measure is samely invariant for any open sets $G$

Besides, $T$ will map measure zero sets onto measure zero sets by following:
- if $E$ is measure zero, then $\forall \epsilon>0$ we can always find open intervals $I=\{I_k\}$ cover $E$ and $\sum_{k=1}^\infty |I_k|<\epsilon$
from above, $T(\cup_{k=1}^\infty I_k)\le \sum_{k=1}^\infty |T(I_k)|=\sum_{k=1}^\infty |I_k|<\epsilon$

Therefore, $E$ is measurable $\implies E=G\cup Z$ where $G=\cup_{k=1}^\infty G_k \in G_\delta,|Z|=0$ and $G\cap Z=\emptyset$
$\implies|TE|=|TG|+|TZ|=\lim_{n\to\infty}|\cup_{k=1}^n TG_k|+0=\lim_{n\to\infty} |\cup_{k=1}^n G_k|=|E|$

## EX2.
By HW1, there exists an Cantor-type set of measure $1-\delta$ for all $\delta\in(0,1)$


Denote $E^k$ as the Cantor-type set of measure $2^{-k}$
let $E_0=E^1$, is the Cantor-type set of measure $\frac 12$.
From the proposition of Cantor-type set, the conplement $E^c$ can be written as the union of disjoint countable intervals $\cup_{k=1}^\infty I^0_k$, $I^0_k=(a^0_k,b^0_k)$ are intervals.

Let $E_1=E_0\cup(\cup_{k=1}^\infty F^1_k)$, where $F^1_k=\{a_k+(b_k-a_k)x|x\in E^2\}$, then $(E_1)^c$ can be represented as union of disjoint intervals $\cup_{k=1}^\infty I_k^{1},I_k^1=(a_k^1,b_k^1)$

Repeat this process, more specifically
- denonte $(E_{n-1})^c$ as $\cup_{k=1}^\infty I_k^{n-1},I_{k}^{n-1}=(a^{n-1}_k,b_k^{n-1})$
- $F^n_k=\{a_k+(b_k-a_k)x|x\in E^n\}$
- $E_n=E_{n-1}+\cup_{k=1}^\infty F_k^n$

Because each construction step we only perform affine map to $E^n$, union countable measurable sets, thereofore each $E_n$ will be measurable
Besides, $|E_n|=\sum_{k=1}^\infty |I_k^n|$, therefore $|E_{n+1}|=|E_n|\times (1-|E^{n+1}|)$

Take $E=\cup_{n=1}^\infty E_n$, which is measurable from the measurablilty of $E_n$

For any interval $I=(a,b)$, $I$ will cotain an interval $I^n_k=(a^n_k,b^n_k)\supset F^n_k$ as long as $n$ sufficiently large enough, and $I\cap E,I-E$ both measurable, and therefore not equal zero as follow:

- $|I\cap E|_e \ge |F_n^k|=(b^n_k-a^n_k)\times |E^n|>0$
- $|I-E|\ge|I^n_k-E| = \lim_{n\to\infty} |I_k^n-E_n|=(b_k-a_k)\Pi_{\ell=n}^\infty(1-|E^\ell|)=(b^n_k-a^n_k)\Pi_{\ell=n}^\infty (1-2^{-\ell})>0$

## EX3.
(ref. https://www.math.ucdavis.edu/~hunter/measure_theory/measure_notes_ch2.pdf?utm_source=chatgpt.com)

Because the translation does not affect the measure, we assume $T$ is a linear transformation.

from SVD, there exist $U,V\in\mathbb R^{n\times n}$ are orthonormal s.t. $T=U^T \Lambda V$, where $\Lambda=diag(\lambda_1,...,\lambda_n)$ is diagonal matrix

any orthonormal matrix can be viewed as an conbinition of reflection and rotation, and these operations are measure-invariant.
therefore, for any measurable set $E$ we have
- $|VE|=|E|$
- $|U(\Lambda VE)|=|\Lambda VE|$

Let view $E'=VE$, because the transformation $\Lambda E'$ equivalent to stretch $E$ along each axis with correspond ratio $\lambda_k$, therefore $|\Lambda E'|=|\lambda_1\lambda_2...\lambda_n||E'|=|\det (\Lambda)||E'|=|\det (U^T \Lambda V)||E'|=|\det(T)| |E'|$

$\implies |TE|=|U^T \Lambda VE|=|\Lambda E'|=|\det T||E'|=|\det T||E|$

## EX4.

assume $\frac 1x>\pi$

$\cos \frac 1x > \frac 12 \iff 2\pi k-\frac 13 \pi <\frac 1x < 2\pi k + \frac 13 \pi,k\in\mathbb N_+$
$\iff x\in (\frac{3}{6\pi k+\pi}, \frac{3}{6\pi k-\pi})$ for $k\in\mathbb N_+$, and the negative case is symmetric

$\implies E=\cup_{k\in \mathbb Z,k\neq 0} (\frac 3{6\pi k+\pi},\frac 3{6\pi k-\pi})$, each interval is disjoint.

$\frac 3{6\pi k-\pi}\le \delta \iff k\ge \frac 1{2\pi \delta}+\frac 1 6$

$|E\cap I_\delta|=2|\cup_{k\ge \frac 1{2\delta}+\frac \pi 6} (\frac 3{6\pi k+\pi}, \frac 3{6\pi k-\pi})|=2\sum_{k\ge \frac 1{2\delta}+\frac \pi 6} (\frac 3{6\pi k-\pi}- \frac 3{6\pi k+\pi})=\frac 1{\pi}\sum_{k\ge \frac 1{2\delta}+\frac 1 6} \frac 1{k-\frac 1 6}-\frac1{k+\frac 1 6}$



$\frac 1{k-\frac 1 6}-\frac1{k+\frac 1 6}=\frac{\pi}{3(k^2-1/6^2)}$ is nonnegative and decreasing as long as $k>1$

Let $L=\frac 1{2\delta}+\frac \pi 6$, then we have

$\frac 1{\pi}\int_{L+1}^\infty \frac 1{x-\frac \pi 6}-\frac 1{x+\frac \pi 6}dx \le |E\cap I_\delta|\le \frac 1{\pi}\int_{L}^\infty \frac 1{x-\frac \pi 6}-\frac 1{x+\frac \pi 6}dx$

$\implies \log \frac{L+1-\frac \pi 6}{L-\frac \pi 6}$