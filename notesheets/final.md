---
documentclass: scrartcl
classoption: twocolumn, fleqn
papersize: letter
geometry: "left=1.5cm,right=1.5cm,top=1cm,bottom=1cm"
header-includes: |
    \usepackage{mathrsfs}
---



**NATURAL LOG**  
$e^{\ln(x)} = x$  
$\ln(e^x) = x$  
$\ln(x \cdot y) = \ln(x) + \ln(y)$  
$\ln(x^y) = y \cdot \ln(x)$  
$\ln(\frac{x}{y}) = \ln(x) - \ln(y)$  
$\ln(\frac{1}{x}) = -\ln(x)$  
$\ln(1) = 0$  
$\ln(0) =$ undefined  

**TRIGONOMETRY**  
$\tan x = \sin x / \cos x$  
$\cot x = 1 / \tan x$  
$\sec x = 1 / \cos x$  
$\csc x = 1 / \sin x$  
$\sin^2 x + \cos^2 x = 1$  
$\sin(A+B) = \sin A \cos B  + \cos A \sin B$  
$\cos(A+B) = \cos A \cos B - \sin A \sin B$  
$\sin(A-B) = \sin A \cos B - \cos A \sin B$  
$\cos(A-B) = \cos A cos B + \sin A \sin B$  
$\sin 2x = 2 \sin x \cos x$  

**DERIVATIVES**  
Product: $(fg)' = fg' + f'g$  
Quotient: $(f/g)' = (f'g - g'f)/g^2$  
Reciprocal: $(1/f) = -f' / f^2$  
Chain: $f(g)' = f'(g) \cdot g'$

**INTEGRALS**  
$\int u \, dv = uv - \int v \, du$  
$\int \frac{1}{x} = \ln|x|$  
$\int \ln ax = x \ln ax - x$  
$\int \tan ax = -\ln|\cos ax| \big/ a$  
$\int \cot ax = \ln|\sin ax| \big/ a$  
$\int \sec x = \ln|\sec x + \tan x|$  
$\int \sec^2 x = \tan x$  
$\int \csc x = -\ln|\csc x + \cot x|$  
$\int \csc^2 x = - \cot x$  
$\int \frac{1}{1+x^2} = \arctan x$  
$\int \frac{1}{\sqrt{1-x^2}} = \arcsin x$  




**LINEAR EQUATION** : $\frac{dy}{dx} + P(x)y=Q(x)$  
`Step1` :: $\mu=e^{(\int \!P\,dx)}$  
`Step2` ::
${
    y = \frac{1}{\mu} (\int \mu Q \, dx + C)
}$

**EXACT EQUATIONS** :
$M\,dx + N\,dy = 0$  
`Exact?` ::
${
    \partial_y M
    = \partial_x N
}$  
`MyTrick` :: $F = \int M \, dx + C(y) = \int N \,dy + C(x)$ \
`Solution` :: $F(x,y) = C$


**SPECIAL INTEGRATING FACTOR**  
`Step1` ::
${
\left \{
\begin{aligned}
    A(x) =
    \left(\frac{
        \partial_y M
        - \partial_x N
    }{N} \right)
    \\
    B(y) =
    \left(\frac{
        \partial_x N
        - \partial_y M
    }{M} \right)
\end{aligned}
\right .
}$  
`Step2` ::
${
    Q =
    \begin{cases}
    A(x) \text{ if it only depends on } x \\
    B(y) \text{ if it only depends on } y
    \end{cases}
}$  
`Step3` ::
${
    \mu = \exp (\int Q)
}$  
`ExactEq` :: ${
    \mu \, M \, dx
    + \mu \, N \, dy = 0
}$

**HOMOGENEOUS EQUATIONS**
${
    \frac{dy}{dx} = G\left(\frac{y}{x}\right)
}$  
`test` ::
${
f(tx, ty) = f(x,y)
}$  
`step1` :: Let $v=y/x$,  
`step2` ::
${
    \frac{dy}{dx}
    =
    v+x
    \frac{dv}{dx}
}$  
`step3` :: Solve separable.  

**SUBSTITUTION**
${
    \frac{dy}{dx} = G(ax+by)
}$  
`Step1` :: Let $z=ax+by$  
`Step2` ::
${
    \frac{dz}{dx} = a + b
    \frac{dy}{dx}
}$   
`Step3` ::
${
    \frac{dy}{dx} =
    \big(
        \frac{dz}{dx} - a
    \big)
    \big/
    b
}$  
`Step4` ::
Substitute $\frac{dy}{dx}$ into original.  
`Step5` ::
Solve separable.

**BERNOULLI EQUATIONS**  
${
    \frac{dy}{dx} = P(x)y = Q(x)y^n
}$  
`Req` :: $n\neq 0, 1$  
`Step1` :: Let $v=y^{(1-n)}$    
`Step2` ::
${    
    \frac{dv}{dx}=(1-n)y^{-n}
    \frac{dy}{dx}
}$,  
`Step3` :: Solve Linear Eq with $v$ and $x$.


**LINEAR COEFFICIENTS**  
${
    (a_1x+b_1y+c_1)dx+(a_2x+b_2y+c_2)dy=0
}$  
`Req` :: $a_1b_2 \neq a_2b_1$  
`Step1` :: Let $x=u+h$  
`Step2` :: Let $y=v+k$  
`Step3` :: Solve
${
\left \{
\begin{aligned}
    a_1 \pmb{h} + b_1 \pmb{k}+c_1=0 \\
     a_2 \pmb{h}+b_2\pmb{k}+c_2 = 0
\end{aligned}
\right \}
}$  
`Step4` ::
Solve homogeneous eq with $u$ and $v$.

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
|

\
**NEWTONS MOTION**  
${
    x(t) = \frac{mg}{b}t + \frac{m}{b}
    \left( v_0 - \frac{mg}{b} \right)
    (1 - e^{-bt/m})
}$

**NEWTONS LAW OF COOLING**  
${
    \frac{dT}{dt} =
    K \big[ M(t) - T(t) \big]
    + H(t) + U(t)
}$  
$M(t)$: outside temp  ,
$T(t)$: inside temp  
$H(t)$: additional heating  ,
$U(t)$: furnace rate  

**SPRING-MASS OSCILLATOR**  
${
    my'' + by' + ky = F_{\text{ext}}(t)
}$  
${
    y(t)=A\cos (\Omega t) + B \sin (\Omega t)
}$


**TWO REAL ROOTS:**  
$y_h = c_1 \cdot e^{r_1t} + c_2 \cdot e^{r_2t}$  
$y'_h = c_1 r_1 e^{r_1 t} + c_2 r_2 e^{r_2 t}$  

**REPEATED ROOTS**  
$y_h = c_1 \cdot e^{rt} + c_2 \cdot t \cdot e^{rt}$  
$y'_h = (c_1 r + c_2) e^{rt} + (c_2 r) t e^{rt}$  

**COMPLEX ROOTS:**  
$y_h = c_1 \cdot e^{\alpha t} \cdot \sin(\beta t) + c_2 \cdot e^{\alpha t} \cdot \cos(\beta t)$  
$y'_h = (c_1 \alpha - c_2 \beta)ES + (c_1 \beta + c_2 \alpha)EC$

**UNDETERMINED COEFFICIENTS**  
CASE:  $f == C t^m e^{rt}$  
SOLU: $y_p = t^s P^m e^{rt}$  
$s=0$ if $r$ is not a root of the equation.  
$s=1$ if $r$ is a simple root.  
$s=2$ if $r$ is a double root.  

CASE: $f = C t^m e^{\alpha t} \! \big\{ {\sin \beta t \atop \cos \beta t} \big\}$  
SOLU: $y_p = t^s P^m_1 e^{\alpha t} \! \cos(\beta t) + t^s P^m_2 e^{\alpha t} \sin(\beta t)$  
$s = 0$ if $\alpha + i\beta$ is not a root.  
$s = 1$ if $\alpha +i\beta$ is a root.  

**SUPERPOSITION**  
LET: $F = ay''+by'+cy$  
IF: $y_1$ is a solution to $F = f_1$  
AND: $y_2$ is a solution to $F = f_2$  
THEN: $k_1y_1 + k_2y_2$ is a solution to $F = k_1f_1 + k_2f_2$

**VARIATION OF PARAMETERS**  
`Step 1` :: Find $y_h$, Let $\{y_1, y_2\} = y_h$  
`Step 2` ::
$W[y_1, y_2] = y_1 y'_2 - y'_1 y_2$  
`Step 3` ::
${
    \left [
    \begin{aligned}
    v_1 &= \int
    \frac{-f y_2}{a W[y_1, y_2]}
    \\
    v_2
    &= \int
    \frac{+f y_1}{aW[y_1,y_2]}
    \end{aligned}
    \right ]
}$  
`Step 4` :: $y_p = v_1 y_1 + v_2 y_2$  
`Step 5` :: $y = y_h + y_p$  

**CAUCHY-EULER (Oily Couch)**  
$at^2y'' + bty' + cy = f$  
`CHAR` :: $ar^2 + (b-a)r + c = 0$  
`REAL` :: $y_h = t^{r_1} + t^{r_2}$  
`DOUB` :: $y_h = t^{r} + t^{r}\ln(t)$  
`PLEX` :: $y_h = t^{\alpha} \! \sin(\beta \ln t) + t^{\alpha} \! \cos(\beta \ln t)$  
`NOTE` :: If solving for $t < 0$, Set $t \gets (-t)$

**REDUCTION OF ORDER**  
$y'' + Py' + Qy = 0 \enspace$;
given $y_1$  
$\displaystyle y_2 = y_1 \int \frac{e^{-\int{P}}}{(y_1)^2}$  
$y_h = y_1 + y_2$

**LINEAR INDEPENDENCE TEST**  
For whole interval: $W[y_1, y_2] = 0$



**PHASE PLANE**  
${
    \frac{dx}{dt} = f(x,y),
    \quad
    \frac{dy}{dt} = g(x,y)
}$  
**Trajectory:**  
$x(t), y(t)$ that solve the system.  
**Related Phase Plane Eq:**  
${
    \frac{dy}{dx}
    =
    \frac{g(x,y)}{f(x,y)}
    =
    \frac{dy/dt}{dx/dt}
}$  
**Critical Points:**  
${
    \Big\{
        (x_0, y_0)
        \, : \,
        f(x_0, y_0) = g(x_0, y_0)= 0
    \Big\}
}$  
**Critical Endpoints:**  
$(x^{*}, y^{*})$
if limits exist and finite:  
${
    x^* = \lim_{t \to +\infty}
    x(t)
}$  
${
    y^* = \lim_{t \to +\infty}
    y(t)
}$


**ANNIHILATION**  
$(D - r) \left[e^{rx}\right]=0$  
$(D - r)^{k+1} \left[x^k e^{rx}\right]=0$  
${
    (D^2 + \beta^2)
    \left[
        \left\{
            {\sin \beta t \atop \cos \beta t}
        \right\}
    \right]
    =0
}$  
${
    \left(
        (D - \alpha)^2 + \beta^2
    \right)^{k+1}
    \left[
        x^k e^{\alpha x}
        \left\{
            {\sin \beta t \atop \cos \beta t}
        \right\}
    \right]
    =0
}$  
${
    (D)^{k+1}
    \left[
        x^{k} + x^{k-1} + \ldots
    \right]
    =0
}$




**LAPLACE TRANSFORM**  
${
    \displaystyle
    F(s)
    = \int_0^\infty
    e^{-st}
    f(t)
    \ dt
}$  
${
    \displaystyle
    \lim_{N \to \infty}
    Ne^{-sN} = 0
    , \quad
    s > 0
}$  


**CONVOLUTION**  
${
    \displaystyle
    (f * g)
    =
    \int_0^t
    f(t - v)
    \cdot
    g(v)
    \cdot
    dv
}$  
Properties:  
${
    f*g = g*f
}$  
${
    f*(g+h) = (f*g) + (f*h)
}$  
${
    (f*g)*h = f*(g*h)
}$  
${
    f*0 = 0
}$



**IMPULSE RESPONSE**  
`Given` ::
${
    ay'' + by' + cy = g,
    \quad y(0) = y_0,
    \quad y'(0) = y'_0
}$  
`Step 1` ::
${
    H(s)
    =
    \frac{1}{as^2 + bs + c}
    \qquad
    \longleftarrow
    \text{Transfer Func}
}$  
`Step 2` ::
${
    h(s) = \mathscr{L}^{-1} \!
    \{ H(s) \}
    \quad
    \longleftarrow
    \text{Impulse Response}
}$  
`Step 3` ::
${
    y_k
    \longleftarrow
    \big[
    \text{homogenous solution when }
    g=0
    \big]
}$  
`Solution` ::
${
    \left [
    \begin{aligned}
    y
    &= (y_k + (h*g)) \\
    &= y_k + \int_0^t h(t-v) \cdot g(v) \cdot dv
    \end{aligned}
    \right ]
}$


<!--


MACLAURIN SERIES  
${
    \displaystyle
    \frac{1}{1-x}
    \ = \
    \sum_{n=0}^{\infty}
    x^n
    \ = \
    1 + x + x^2 + x^3 + \cdots
}$  
${
    \displaystyle
    e^x
    \ = \
    \sum_{n=0}^{\infty}
    \frac{x^n}{n!}
    \ = \
    \frac{x}{1!}
    + \frac{x^2}{2!}
    + \frac{x^3}{3!}
    + \frac{x^4}{4!}
    + \cdots
}$  
${
    \displaystyle
    \sin{x}
    \ = \
    \sum_{n=0}^{\infty}
    \frac
    {
        (-1)^n
        x^{2n+1}
    }{
        (2n+1)!
    }
    \ = \
    x
    - \frac{x^3}{3!}
    + \frac{x^5}{5!}
    - \frac{x^7}{7!}
    + \cdots
}$  
${
    \displaystyle
    \cos{x}
    \ = \
    \sum_{n=0}^{\infty}
    \frac
    {
        (-1)^n x^{2n}
    }{
        (2n!)
    }
    \ = \
    1
    - \frac{x^2}{2!}
    + \frac{x^4}{4!}
    - \frac{x^6}{6!}
    + \cdots
}$   -->


**POWER SERIES**  
${
    \displaystyle
    y
    \ = \
    \sum_{n=0}^{}
    a_n
    x^n
}$  
${
    \displaystyle
    y'
    \ = \
    \sum_{n=1}^{}
    n
    a_n
    x^{n-1}
}$  
${
    \displaystyle
    y''
    \ = \
    \sum_{n=2}^{}
    n
    (n-1)
    a_n
    x^{n-2}
}$  
...when given Initial Values:  
$y_0 = a_0, \quad y'_0 = a_1$
