---
geometry: "left=1.5cm,right=1.5cm,top=2cm,bottom=2cm"
papersize: letter
documentclass: scrartcl
classoption: twocolumn, twoside
header-includes: |
    \pagestyle{headings}
    \usepackage{cancel}
    \usepackage{fancyhdr}
    \pagestyle{fancy}
    \fancyhead{}
    \fancyhead[C]{\textsc{Chris Achenbach's Awesome Differential Equations Notesheet}}
    \fancyfoot[C]{}
    \renewcommand{\footrulewidth}{0.4pt}
---

**LINEAR EQUATION**
$$\frac{dy}{dx} + P(x)y=Q(x)$$
$$
    y = \frac{\int \mu Q \, dx + C}{\mu} , \quad
    \mu=e^{\int P\,dx}
$$

**EXACT EQUATIONS**
$$M\,dx + N\,dy = 0$$
Exactness: $\frac{\partial}{\partial y} M =\frac{\partial}{\partial x} N$\
My Trick: $F = \int M \, dx + C(y) = \int N \,dy + C(x)$ \
Solution: $\quad F(x,y) = C$


**SPECIAL INTEGRATING FACTOR** \
$$
A = \left(
    \frac{
        \frac{\partial}{\partial y} M
        - \frac{\partial}{\partial x} N
    }{N} \right)
,\quad
B = \left(\frac{
    \frac{
        \partial}{\partial x} N
        - \frac{\partial}{\partial y} M
    }{M} \right)
$$
Use $A$ if it only depends on $x$.\
Use $B$ if it only depends on $y$.

**HOMOGENEOUS EQUATIONS**
$$
    \frac{dy}{dx} = G\left(\frac{y}{x}\right)
$$
$$
\text{the test:} \quad f(tx, ty) = f(x,y)
$$
Let $v=y/x$, then $dy/dx = v+x(dv/dx)$, and the transformed equations in the variables $v$ and $x$ is separable.

**ANOTHER SUBSTITUTION**
$$
    \frac{dy}{dx} = G(ax+by)
$$
Let $z=ax+by$. Then $dz/dx = a + b(dy/dx)$, and the transformed equation in the variables $z$ and $x$ is separable.

**BERNOULLI EQUATIONS**
$$
    \frac{dy}{dx} = P(x)y = Q(x)y^n
$$
For $n\neq 0, 1$, Let $v=y^{(1-n)}$. Then $\frac{dv}{dx}=(1-n)y^n\left(\frac{dy}{dx}\right)$, and the transformed equation in the variables $v$ and $x$ is linear.

**LINEAR COEFFICIENTS**
$$
    (a_1x+b_1y+c_1)dx+(a_2x+b_2y+c_2)dy=0
$$
For $a_1b_2 \neq a_2b_1$, let $x=u+h$ and $y=v+k$ where $h$ and $k$ satisfy
$$
\begin{aligned}
    a_1h + b_1k+c_1=0 \\
     a_2h+b_2k+c_2 = 0
\end{aligned}
$$
Then the transformed equation in the variables $u$ and $v$ is homogeneous.

**EULERS METHOD** \
$x_{n+1} = x_n + h$\
$y_{n+1} = y_n + hf(x_n, y_n)$

| **IMPROVED_EULER**$(x_0, y_0, c, N):$
|         $x = x_0$
|         $y = y_0$
|         $h = (c - x_0) / N$
|         $\texttt{FOR } i \texttt{ FROM } 0 \texttt{ TO } N:$
|                 $F = f(x,y)$
|                 $G = f((x+h), \ (y+h*F))$
|                 $x = x+h$
|                 $y = y+h(F + G)/2$


**NEWTONS MOTION**
$$
    x(t) = \frac{mg}{b}t + \frac{m}{b}
    \left( v_0 - \frac{mg}{b} \right)
    (1 - e^{-bt/m})
$$

**SPRING-MASS OSCILLATOR**
$$
    my'' + by' + ky = F_{\text{ext}}(t)
$$
$$
    y(t)=A\cos (\Omega t) + B \sin (\Omega t)
$$

**HOMOGENEOUS LINEAR EQUATIONS**
$$
    ay'' + by' + cy = 0 , \qquad a \neq 0
$$
Two Roots $\rightarrow$ $y(t) = c_1 \, e^{r_1t} + c_2 \, e^{r_2t}$ \
Same Root $\rightarrow$ $y(t) = c_1 \, e^{rt} + c_2 \, t \, e^{rt}$


**THE QUADRATIC EQUATION**
$$
    x = \frac{-b \pm \sqrt{b^2 - 4 a c}}{2a}
$$
