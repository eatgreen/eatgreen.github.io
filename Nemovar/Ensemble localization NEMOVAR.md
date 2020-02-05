##Multivariate formulation
The correlation function takes form, 
   \[ \begin{pmatrix}
      C_T & C_T \\
      C_T & C_T
      \end{pmatrix}
   \]
The ensemble sample matrix should be
   \[ \begin{pmatrix}
      \hat{X}'_{T1} & \hat{X}'_{T2}  \\
      \hat{X}'_{S1} & \hat{X}'_{T2} 
      \end{pmatrix}
      \begin{pmatrix}
      \hat{X}'_{T1} & \hat{X}'_{T2}  \\
      \hat{X}'_{S1} & \hat{X}'_{T2} 
      \end{pmatrix}^T
      \odot
      \begin{pmatrix}
      C_T & C_T \\
      C_T & C_T
      \end{pmatrix}
   \]
This equals: 
 \[  \begin{align}
      \begin{pmatrix}
      diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) 
      \end{pmatrix}
      \begin{pmatrix}
      C_T & C_T \\
      C_T & C_T
      \end{pmatrix}
      \begin{pmatrix}
      diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) 
      \end{pmatrix}+ \\
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2}) 
      \end{pmatrix}
      \begin{pmatrix}
      C_T & C_T \\
      C_T & C_T
      \end{pmatrix}
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2})
      \end{pmatrix}
   \end{align}
\]
then
 \[  \begin{align}
      \begin{pmatrix}
      diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) 
      \end{pmatrix}
      \begin{pmatrix}
      I \\
      I
      \end{pmatrix}
      C_T
       \begin{pmatrix}
      I & I \\
      \end{pmatrix}
      \begin{pmatrix}
      diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) 
      \end{pmatrix}+ \\
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2}) 
      \end{pmatrix}
      \begin{pmatrix}
      I \\
      I
      \end{pmatrix}
      C_T
       \begin{pmatrix}
      I & I \\
      \end{pmatrix}
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2})
      \end{pmatrix}
   \end{align}
\]
with  \begin{pmatrix}
      D_t^{1/2}Z_t \\
      D_s^{1/2}Z_s
      \end{pmatrix} on the right positon waiting to be applied
Basically the application process is done through
\[
C_T^{1/2}\big(diag(\hat{X}'_{T2})D_t^{1/2}Z_t + diag(\hat{X}'_{S2})D_s^{1/2}Z_s\big)
\]
In this case the cross-covariance is defined through the same correlation matrix $C_T$, plus the error of T and S. $\sigma_T c \sigma_S$. However, the errors are computed through unbalanced components. The analysis increments, computed based on the error covariance matrix, need to be applied with a balance opearator.
##Univariate formulation
The correlation function takes form, 
   \[ \begin{pmatrix}
      C_T & 0 \\
      0 & C_S
      \end{pmatrix}
   \]
Cross-covariance is defined by $K_{bal}$

The ensemble sample matrix should be
   \[ \begin{pmatrix}
      \hat{X}'_{T1} & \hat{X}'_{T2}  \\
      \hat{X}'_{S1} & \hat{X}'_{T2} 
      \end{pmatrix}
      \begin{pmatrix}
      \hat{X}'_{T1} & \hat{X}'_{T2}  \\
      \hat{X}'_{S1} & \hat{X}'_{T2} 
      \end{pmatrix}^T
      \odot
      \begin{pmatrix}
      C_T & 0 \\
      0 & C_S
      \end{pmatrix}
   \]
This equals 
 \[  \begin{align}
      \begin{pmatrix}
      diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) 
      \end{pmatrix}
      \begin{pmatrix}
      C_T & 0 \\
      0 & C_S
      \end{pmatrix}
      \begin{pmatrix}
      diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) 
      \end{pmatrix}+ \\
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2}) 
      \end{pmatrix}
      \begin{pmatrix}
      C_T & 0 \\
      0 & C_S
      \end{pmatrix}
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2})
      \end{pmatrix}
   \end{align}
\]
 \[  \begin{align}
    = \begin{pmatrix}
      diag(\hat{X}'_{T1}) C_T diag(\hat{X}'_{T1}) & 0  \\
      0 & diag(\hat{X}'_{S1}) C_S diag(\hat{X}'_{S1}) 
      \end{pmatrix}
      + \\
      \begin{pmatrix}
      diag(\hat{X}'_{T2}) C_T diag(\hat{X}'_{T2}) & 0  \\
      0 & diag(\hat{X}'_{S2}) C_S diag(\hat{X}'_{S2}) 
      \end{pmatrix}
   \end{align}
\]