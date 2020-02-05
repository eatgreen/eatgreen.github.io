\[A= \begin{bmatrix}
   A_{11} & A_{12} & \cdots & A_{1n} \\
   A_{21} & A_{22} & \cdots & A_{2n} \\
   \vdots & \vdots & \ddots & \vdots \\
   A_{21} & A_{22} & \cdots & A_{2n}
   \end{bmatrix}
\]

eliminating $A_{21}$ by multiplying the first row with $A{21}/A{11}$ and substracting it from the second row.
Finally we have an upper triangular matrix

\[U= \begin{bmatrix}
   A_{11} & A_{12} & \cdots & A_{1n} \\
   0 & A_{22} & \cdots & A_{2n} \\
   \vdots & \vdots & \ddots & \vdots \\
   0 & 0 & \cdots & A_{2n}
   \end{bmatrix}
\]

All the elements except the first row differs the orginal matrix.
Complexity $n^3/3$