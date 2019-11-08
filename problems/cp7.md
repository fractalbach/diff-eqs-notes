---
documentclass: scrartcl
geometry: "left=1in,right=1in,top=0.5in,bottom=1in"
papersize: letter
header-includes: |
    \everymath{\displaystyle}
include-before: |
    \begin{flushright}\textit{\huge Chris Achenbach}\end{flushright}
---

\noindent\rule{\textwidth}{1pt}
Determine the form of a particular solution to the equation $y^{(4)} -5y'' + 4y = 10\cos(t) - 20\sin(t)$
\noindent\rule{\textwidth}{1pt}



The corresponding homogeneous equation,
$$y^{(4)} -5y'' + 4y = 0$$
has a characteristic equation of
$$r^4 - 5r^2 + 4r = 0$$
which can be factored into
$$
    r (r-1) (r^2 + r - 4) = 0
$$
In the third term, we need to know if has real or complex roots, so we can determine that checking if $b^2 -4ac<0$,
$$
(1)^2 - 4(1)(-4) \ = \ 9 \quad \not< 0
$$
Thus, the third term has real roots.

Ok, now lets look at all the roots together,
$$
\begin{aligned}
    r_1 &= 0 \\
    r_2 &= 1 \\
    r_3 &\in \mathbb{R} \\
    r_4 &\in \mathbb{R}
\end{aligned}
$$
Since we don't have any complex roots, we don't need to worry about adding extra $t$ terms to our particular solution(s).

At least, I don't *think* we need to worry about it...

---

Ok, back to the original differential equation.  First thing to notice is that we can use the superposition principle here,
$$
    k_1f_1 + k_2f_2 = 10\cos(t) - 20\sin(t)
$$
$$
\begin{aligned}
    k_1 &= 10 \\
    k_2 &= -20 \\
    f_1 &= \cos(t) \\
    f_2 &= \sin(t)
\end{aligned}
$$
So we can get particular solutions for each of them separately,
$$
\begin{aligned}
y_{p1} &= A\sin(t) + B\cos(t) \\
y_{p2} &= C\sin(t) + D\sin(t)
\end{aligned}
$$
And then do a linear combination of them to get the form of our particular solution,
$$
\boxed{y_p = (A + C)\sin{t} + (B + D)\cos{t}}
$$
