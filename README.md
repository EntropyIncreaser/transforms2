# transforms2
compute "Further Transformations of Integer Sequences" http://oeis.org/transforms2.html

## 约定记号

由 $A(x)$ 表示 $a_n$ 的 OGF，$\widehat A(x)$ 表示其 EGF。

即有关系
$$
A(x) = \int_{0}^\infty \widehat A(xt)\mathrm e^{-t} \,\mathrm d t
$$

# 总结

## AIK

$$
\operatorname{AIK} A(x) = \frac1{1 - A(x)}
$$

时间复杂度：$\Theta(n\log n)$

## AIJ

$$
\widehat {\operatorname{AIJ} A}(x) = \frac1{1 - \widehat A(x)}
$$

时间复杂度：$\Theta(n\log n)$

## CHK

$$
\begin{align}
\operatorname{CHK} A(x) &= \sum_{k\ge 1} \frac1k \sum_{d|k} \mu(d) A(x^d)^{k/d}\\
&= \sum_{d\ge 1} \mu(d) \sum_{j \ge 1} \frac{A(x^d)^j}{dj}\\
&= \sum_{d\ge 1} \frac{\mu(d)}d \ln \frac1{1 - A(x^d)}
\end{align}
$$

时间复杂度：$\Theta(n\log n)$

## CIK

$$
\begin{align}\operatorname{CIK}
A(x) &= \sum_{k\ge 1} \frac1k \sum_{j = 0}^{k - 1} A(x^{k / \gcd(k,j)})^{\gcd(k,j)}
\\ &= \sum_{k\ge 1} \frac1k \sum_{d|k} \varphi(d) A(x^d)^{k/d}\\&= \sum_{d\ge 1} \varphi(d) \sum_{j \ge 1} \frac{A(x^d)^j}{dj}\\&= \sum_{d\ge 1} \frac{\varphi(d)}d \ln \frac1{1 - A(x^d)}
\end{align}
$$

时间复杂度：$\Theta(n\log n)$

## EGK

$$
\begin{align}
\operatorname{EGK} A(x) &=  \prod_{n\ge 1} (1 + x^n)^{a_n}\\
&= \exp \sum_{n\ge 1} a_n\ln (1 + x^n)\\
&= \exp \sum_{n\ge 1} \sum_{k\ge 1} \frac{(-1)^{k-1}a_nx^{kn}}k\\
&= \exp \sum_{k\ge 1} \frac{(-1)^{k-1}}k \sum_{n\ge 1} a_n x^{kn}\\
&= \exp \left( \sum_{k\ge 1} \frac{(-1)^{k-1}}k A(x^k) \right)
\end{align}
$$

时间复杂度：$\Theta(n\log n)$

## EIJ

$$
\widehat{\operatorname{EIJ} A} (x) = \exp \widehat A(x)
$$

时间复杂度：$\Theta(n\log n)$

## EIK

$$
\begin{align}
\operatorname{EIK} A(x) &=  \prod_{n\ge 1} (1 - x^n)^{-a_n}\\
&= \exp \sum_{n\ge 1} a_n\ln \frac1{1 - x^n}\\
&= \exp \sum_{n\ge 1} \sum_{k\ge 1} \frac{a_nx^{kn}}k\\
&= \exp \sum_{k\ge 1} \frac1k \sum_{n\ge 1} a_n x^{kn}\\
&= \exp \left( \sum_{k\ge 1} \frac{A(x^k)}k  \right)
\end{align}
$$

时间复杂度：$\Theta(n\log n)$

