# Latex Practice
###### tags: `test`

$$
\begin{align*}
y = y(x,t) 
&= A e^{i\theta} \\
&= A (\cos \theta + i \sin \theta) \\
&= A (\cos(kx - \omega t) + i \sin(kx - \omega t)) \\
&= A\cos(kx - \omega t) + i A\sin(kx - \omega t)  \\
&= A\cos \Big(\frac{2\pi}{\lambda}x - \frac{2\pi v}{\lambda} t \Big) + i A\sin \Big(\frac{2\pi}{\lambda}x - \frac{2\pi v}{\lambda} t \Big)  \\
&= A\cos \frac{2\pi}{\lambda} (x - v t) + i A\sin \frac{2\pi}{\lambda} (x - v t)
\end{align*}
$$

<hr>

$$
f(n) =
\begin{cases} 
n/2,  & \mbox{if }n\mbox{ is even} \\
3n+1, & \mbox{if }n\mbox{ is odd}
\end{cases}
$$

The angle is 30$^\circ$

<hr>

\begin{align}
  (a + b)^3  &= (a + b) (a + b)^2       \\
            &= (a + b)(a^2 + 2ab + b^2) \\
            &= a^3 + 3a^2b + 3ab^2 + b^3
\end{align}

\begin{align}
  x^2  + y^2 & = 1                      \\
 x         & = \sqrt{1-y^2}
\end{align}
This example has two column-pairs.
\begin{align}   \text{Compare }
  x^2 + y^2 &= 1              &
  x^3 + y^3 &= 1              \\
 x        &= \sqrt  {1-y^2} &
 x        &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
   x   &= y     & X  &= Y  &
     a  &= b+c              \\
   x'   &= y'    & X' &= Y' &
     a' &= b                \\
  x + x' &= y + y'           &
  X + X' &= Y + Y' & a'b &= c'b
\end{align}

\begin{align}   \text{Compare }
  x^2 + y^2 &= 1              &
  x^3 + y^3 &= 1             \\
 x        &= \sqrt  {1-y^2} &
 x        &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.



\begin{align}
 x     &= y     && \text{by hypothesis} \\
     x' &= y'    && \text{by definition} \\
  x + x' &= y + y' && \text{by Axiom 1}
\end{align}

\begin{equation}
\begin{aligned}
  x^2 + y^2  &= 1              \\
 x         &= \sqrt{1-y^2}   \\
 \text{and also }y &= \sqrt{1-x^2}
\end{aligned}              \qquad
\begin{gathered}
 (a + b)^2 = a^2 + 2ab + b^2    \\
 (a + b) \cdot (a - b) = a^2 - b^2
\end{gathered}     \end{equation}

\begin{equation}
\begin{aligned}[b]
  x^2 + y^2  &= 1              \\
 x         &= \sqrt{1-y^2}   \\
 \text{and also }y &= \sqrt{1-x^2}
\end{aligned}              \qquad
\begin{gathered}[t]
 (a + b)^2 = a^2 + 2ab + b^2    \\
 (a + b) \cdot (a - b) = a^2 - b^2
\end{gathered}
\end{equation}

\begin{equation} \begin{aligned}
  V_j &= v_j                     &
  X_i &= x_i - q_i x_j           &
     &= u_j + \sum_{i\ne j} q_i \\
  V_i &= v_i - q_i v_j           &
  X_j &= x_j                     &
  U_i &= u_i
\end{aligned} \end{equation}


<hr>

- ref : [LaTeX 符号命令大全](https://www.cnblogs.com/Coolxxx/p/5982439.html)