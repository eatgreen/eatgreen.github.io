In nemovar an balance operator is used. The main object is to use a background error covariance matrix without the cross-variant parts.

Say $\delta x$ is in model space, $\delta x_u$ is control space, and
\[\delta x=K\delta x_u
\]
The cost fucntion in terms of $B_{tot}$ is:
\[J=\frac{1}{2}\delta x^T B_{tot}^{-1} \delta x + \frac{1}{2} (H\delta x-d)R^{-1}(H\delta x-d)
\]
with $B_{tot}=KB_uK^T$
\[J=\frac{1}{2}\delta x^T {K^T}^{-1} B_u^{-1} K^{-1} \delta x + \frac{1}{2} (H\delta x-d)R^{-1}(H\delta x-d)
\]
\[J=\frac{1}{2}\delta x_u^T B_u^{-1} \delta x_u + \frac{1}{2} (HK\delta x_u-d)R^{-1}(HK\delta x_u-d)
\]

Thus we have a modified H operator, in exchange we have $B_u$ only containing the auto-covariance part. In order to get the full increment, we must project them back to model space in the end.