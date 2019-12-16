---
documentclass: scrartcl
geometry: "left=1in,right=1in,top=1in,bottom=1in"
papersize: letter
header-includes: |
    \everymath{\displaystyle}
include-before: |
    \texttt{\textbf{\LARGE CP 9}}
    \hfill
    \textit{\huge Chris Achenbach}
    \everymath{\displaystyle}
    \newenvironment{amatrix}[1]{\left(\begin{array}{@{}*{#1}{c}|c@{}}}{\end{array}\right)}
---

Find the Laplace transform of $\sin(\beta t)$,
$$
\begin{aligned}
\mathcal{L}\big\{\sin(\beta t)\big\}
&= \int_0^{\infty} e^{-st} \sin(\beta t) \, dt \\
&= \lim_{N\to\infty} \int_0^N  e^{-st} \sin(\beta t) \, dt \\
&= \lim_{N\to\infty} \Big[ F \Big]_0^N \\
\end{aligned}
$$

First let's find the integral $\int e^{-st} \sin(\beta t)$ so that we will be able to solve the rest of the problem,
$$
\text{Let} \quad F = \int e^{-st} \sin(\beta t)
$$
Let's use *Integration by Parts* where
$$
\begin{aligned}
u &= e^{-st} \qquad
&dv &= \sin(\beta t) \\
du &= (-s)e^{-st} \qquad
&v &= \left(-\tfrac{1}{\beta}\right)\cos(\beta t)
\end{aligned}
$$
so the integral $F$ now looks like
$$
\begin{aligned}
F
&= \int u \, dv  \\
&= uv - \int v \ du \\
&=
    e^{-st}
    \left(-\tfrac{1}{\beta}\right)\cos(\beta t)
    - \int
    \left(-\tfrac{1}{\beta}\right)\cos(\beta t)
    (-s)e^{-st}
    \ dt
    \\
&=
    \left(-\tfrac{1}{\beta}\right)
    e^{-st} \cos(\beta t)
    -
    \left(\tfrac{s}{\beta}\right)
    \int e^{-st} \cos(\beta t) \ dt
    \\
&=
    \left(-\tfrac{1}{\beta}\right)
    e^{-st} \cos(\beta t)
    -
    \left(\tfrac{s}{\beta}\right)
    G
\end{aligned}
$$
Well now we have got another integral to deal with,
$$
\text{Let} \quad G = \int e^{-st} \cos(\beta t)
$$

---

    THINGS WENT BAD AFTER THIS POINT... LOL

---

And we want to do integration by parts again, but switch it up a bit,
$$
\begin{aligned}
u &=  \cos(\beta t) \qquad
&dv &= e^{-st} \\
du &= -\beta \sin(\beta t) \qquad
&v &= \left(-\tfrac{1}{s}\right) e^{-st}
\end{aligned}
$$
so the integral $G$ now looks like,
$$
\begin{aligned}
G
&= \int u \ dv \\
&= uv - \int v \ du \\
&=
    \cos(\beta t)
    \left(-\tfrac{1}{s}\right) e^{-st}
    -
    \int
    \left(\tfrac{1}{s}\right) e^{-st}
    \beta \sin(\beta t)
    \\
&=
    \left(-\tfrac{1}{s}\right) e^{-st}
    \cos(\beta t)
    +
    \left(\tfrac{\beta}{s}\right)
    \int
    e^{-st}
    \sin(\beta t)
\end{aligned}
$$
Now what's interesting is that we have ended up with a term that is identical to $F$ from our earlier integral, so we can substitute that,
$$
    G =
    \left(- \tfrac{1}{s}\right) e^{-st}
    \cos(\beta t)
    +
    \left(\tfrac{\beta}{s}\right)
    F
$$
And now we can go back to our definition of $F$ and plug in our newly discovered expression for $G$ and simplify,
$$
\begin{aligned}    
F
&=
    \left(-\tfrac{1}{\beta}\right)
    e^{-st} \cos(\beta t)
    -
    \left(\tfrac{s}{\beta}\right)
    G
    \\
&=
    \left(-\tfrac{1}{\beta}\right)
    e^{-st} \cos(\beta t)
    -
    \left(\tfrac{s}{\beta}\right)
    \bigg(
        \left(- \tfrac{1}{s}\right) e^{-st}
        \cos(\beta t)
        +
        \left(\tfrac{\beta}{s}\right)
        F
    \bigg)
    \\
&=
    \left(-\tfrac{1}{\beta}\right)
    e^{-st} \cos(\beta t)
    +
    \left(\tfrac{1}{\beta}\right)
    e^{-st}
    \cos(\beta t)
    -
    F
    \\
2F &=
    \left(\tfrac{1}{\beta}\right)
    \Big(
    -
    e^{-st} \cos(\beta t)
    +
    e^{-st}
    \cos(\beta t)
    \Big)
    \\
\end{aligned}
$$
