---
documentclass: scrartcl
papersize: letter
fontsize: 12pt
---

# Common Derivatives

$$\begin{aligned}
\hline
\textbf{Name} && \textbf{Function} && \textbf{Derivative} \\
\hline
\\
\text{Constant}
    && c && 0 \\ \\
\text{Linear}
    && x && 1 \\ \\
    && ax && a \\
\\
\text{Square}
    && x^2 && 2x \\
\\
\text{Square Root}
    && \sqrt{x} && \dfrac{1}{2}\cdot x^{\frac{1}{2}} \\
\\
\text{Exponential}
    && e^x && e^x \\ \\
    && a^x && \ln(a)\,a^x \\
\\
\text{Logarithms}
    && \ln(x) && \frac{1}{x} \\ \\
    && \log_a(x) && \frac{1}{x\ln(a)} \\
\\
\text{Trigonometry}
    && \sin(x) && \cos(x) \\
    && \cos(x) && -\sin(x) \\
    && \tan(x) && \sec^2(x) \\
    && \cot(x) && -\csc^2(x) \\
    && \sec(x) && \sec(x)\tan(x) \\
\end{aligned}$$


# Special Derivative Rules

$$\begin{aligned}
\hline
\textbf{Rule} && \textbf{Function} && \textbf{Derivative} \\
\hline
\\
\text{Multiply by Constant}
    &&  cf && cf' \\
\\
\text{Power Rule}
    && x^n && nx^{n-1} \\
\\
\text{Sum Rule}
    && f+g && f' + g' \\
\\
\text{Product Rule}
    && fg && fg' + gf' \\
\\
\text{Quotient Rule}
    && \frac{f}{g} && \frac{gf'-fg'}{g^2} \\
\\
\text{Reciprocal Rule}
    && \frac{1}{f} && -\frac{f}{f^2} \\
\\
\text{Chain Rule (Notation 1)}
    && f\circ g &&(f' \circ g) \cdot g' \\
\\
\text{Chain Rule (Notation 2)}
    && f(g(x) && f'(g(x))\cdot g'(x) \\
\\
\end{aligned}$$


# Blah

$\frac{d}{dx}( c ) = 0$

$\frac{d}{dx}( x^n ) = nx^{n-1}$

$\frac{d}{dx}(f+g) = f' + g'$

$\frac{d}{dx}(fg) = fg' + gf'$



# Integration

## Basic Properties of Integrals

1. $$\int a\,f(x)\,dx \ = a \int f(x)\,dx$$
2. $$\int [ f(x)+g(x) ] \,dx \ = \int f(x)\,dx + \int g(x)\,dx$$

## Integration by Parts
$$ \int u \ dv = uv - \int v \ {du} $$
For Integration by Parts, Pick $u$ and $dv$ from your equation.
$$
\begin{aligned}
    u & =\text{___} &\quad
        dv &=\text{___}
        && \leftarrow \text{pick these.}
    \\
    du& =\text{___} &\quad
        v&= \text{___}
        && \leftarrow \text{derive from above.}
\end{aligned}
$$

## Integration by Substitution
When you notice an equation that could be in the form:
$$
    \int f(g(x)) \, g'(x) \,dx
$$
1. Choose a transformation
    $$
        u = g(x)
    $$
2. Find its differential
    $$
        du = g'(x) \, dx
    $$
3. Apply substitution
    $$
        \int f(g(x)) \, g'(x) \,dx = \int f(u)\,du
    $$
4. Solve the Integral, and then replace $u$ again.
