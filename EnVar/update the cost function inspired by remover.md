\begin{align}
   J&=\frac{1}{2}\delta z^T\delta z+\frac{1}{2}(A_b\delta z-d)^TR^{-1}(A_b\delta z-d),\\
   G&=\delta z+A_b^TR^{-1}(A_b\delta z-d).
\end{align}
Usually we have the initial vector equals zero, so:
\begin{align}
   J_0&=\frac{1}{2}d^T R^{-1} d,\\
   G_0&=-A_b^TR^{-1}d.
\end{align}
After one update in conjuagete gradient, we have $\delta z^*$, so
\begin{align}
   J^*&=\frac{1}{2}\delta z^{*T}\delta z^*+\frac{1}{2}(A_b\delta z^*-d)^TR^{-1}(A_b\delta z^*-d),\\
   G^*&=\delta z^*+A_b^TR^{-1}(A_b\delta z^*-d).
\end{align}
For cost function
\begin{align}
   J^*&=\frac{1}{2}\delta z^{*T}\delta z^*+\frac{1}{2}(A_b\delta z^*-d)^TR^{-1}(A_b\delta z^*-d),\\
   J^*&=\frac{1}{2}\delta z^{*T}\delta z^*+\frac{1}{2}(\delta z^{*T}A_b^TR^{-1}A_b\delta z^*-d^TR^{-1}A_b\delta z^*-\delta z^{*T}A_b^TR^{-1}d+d^T R^{-1} d)\\
   J^*&=\frac{1}{2}\delta z^{*T}\delta z^*+\frac{1}{2}\big(\delta z^{*T}(A_b^TR^{-1}A_b\delta z^*-A_b^TR^{-1}d)-d^TR^{-1}A_b\delta z^*+d^T R^{-1} d\big) \\
   J^*&=\frac{1}{2}\delta z^{*T}(\delta z^*+A_b^TR^{-1}A_b\delta z^*-A_b^TR^{-1}d)+\frac{1}{2}(-d^TR^{-1}A_b\delta z^*+d^T R^{-1} d) 
\end{align}
Note that $\delta z^*$ is a solution of $(I+A_b^TR^{-1}A_b)x-A_b^TR^{-1}d=0$, so
\begin{align}
   J^*&=\frac{1}{2}(-d^TR^{-1}A_b\delta z^*+d^T R^{-1} d) \\
      &=\frac{1}{2}G_0^T\delta z^*+J_0
\end{align}

If we have the original from: 
\begin{align}
   J&=\frac{1}{2}(\delta x-\delta x_b)^TB^{-1}(\delta x-\delta x_b)+\frac{1}{2}(H\delta x-d)^TR^{-1}(H\delta x-d),\\
   G&=B^{-1}(\delta x-\delta x_b)+H^TR^{-1}(H\delta x-d).
\end{align}
Usually we have the initial vector equals zero, so:
\begin{align}
   J_0&=\frac{1}{2}\delta x_b^TB^{-1}\delta x_b+\frac{1}{2}d^T R^{-1} d,\\
   G_0&=-B^{-1}\delta x_b-H^TR^{-1}d.
\end{align}
The cost function at minimization is:
\begin{align}
   J^*&=\frac{1}{2}(\delta x^{*}-\delta x_b)^TB^{-1}(\delta x^{*}-\delta x_b)+\frac{1}{2}(H\delta x^*-d)^TR^{-1}(H\delta x^*-d),\\
   J^*&=\frac{1}{2}(\delta x^{*T}B^{-1}\delta x^*-\delta x_b^TB^{-1}\delta x^{*}-\delta x^{T*}B^{-1}\delta x_b+\delta x_b^TB^{-1}\delta x_b)+\frac{1}{2}(\delta x^{*T}H^TR^{-1}H\delta x^*-d^TR^{-1}H\delta x^*-\delta x^{*T}H^TR^{-1}d+d^T R^{-1} d)\\
   J^*&=\frac{1}{2}\delta x^{*T}\big(B^{-1}(\delta x^*-\delta x_b)+H^TR^{-1}H\delta x^*-H^TR^{-1}d\big)-\frac{1}{2}\delta x_b^TB^{-1}\delta x^{*}+\frac{1}{2}\delta x_b^TB^{-1}\delta x_b+\frac{1}{2}(-d^TR^{-1}H\delta x^*+d^T R^{-1} d)
\end{align}
we solve actually $(B^{-1}+H^TR^{-1}H)x-B^{-1}\delta x_b-H^TR^{-1}d=0$, so
\begin{align}
 J^*&=-\frac{1}{2}\delta x_b^TB^{-1}\delta x^{*}+\frac{1}{2}\delta x_b^TB^{-1}\delta x_b+\frac{1}{2}(-d^TR^{-1}H\delta x^*+d^T R^{-1} d)\\
 J^*&=-\frac{1}{2}(\delta x_b^TB^{-1}+d^TR^{-1}H)\delta x^{*}+\frac{1}{2}\delta x_b^TB^{-1}\delta x_b+\frac{1}{2}+d^T R^{-1} d\\
 J^*&=\frac{1}{2}G_0^T\delta x^*+J_0
\end{align}