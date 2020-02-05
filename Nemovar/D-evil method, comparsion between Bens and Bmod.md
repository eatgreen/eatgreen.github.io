The question remaing to be answered is 
1. why the variance decreases more when we put more weight on Bens and
2. why the ensemble increment norem increases more when we put more weight on Bens?

\[\mathbf{X}^a_j=(\mathbf{I}_m-\hat{\mathbf{Z}}_K(\mathbf{I}_K-\Theta^{-\frac{1}{2}}_K)\bar{\mathbf{Z}}_K^T)\mathbf{X}^b_j,\, j=1,\cdots, N\]
Output: $\delta \mathbf{X}^a_j=\mathbf{X}^a_j-\mathbf{X}^b_j,$ and $\mathbf{X}^a_j$.

$||\delta \mathbf{X}^a_j||$ is increasing and increases more with more weight on Bens.
$V_a^K$ decreases more with more weight on Bens.

**This explanation is wrong**: usually when we have more weight on Bens, the Ritz values are increased as well. We know that
$\hat{\mathbf{Z}}_K\Theta^{-\frac{1}{2}}_K\bar{\mathbf{Z}}_K^T$ is an approximation of the square root of the inverse of $I+BG^TR^{-1}G$. When $\Theta_K$ is larger, $\Theta_K^{-\frac{1}{2}}$ is thus smaller, $\hat{\mathbf{Z}}$ and $\bar{\mathbf{Z}}$ are orthogonal vectors, so $\mathbf{X}^a_j$ should be smaller which contradicts the behavior.

Another explanation is: We know that
$\hat{\mathbf{Z}}_K\Theta^{-\frac{1}{2}}_K\bar{\mathbf{Z}}_K^T$ is an approximation of the square root of the inverse of $I+BG^TR^{-1}G$. 

The Ritz values $\Theta_K$ corresponds to the Hessian $I+U^TG^TR^{-1}GU$. 

We know that $\hat{\mathbf{Z}}_K=B\bar{\mathbf{Z}}_K$, so we have $B\bar{\mathbf{Z}}_K\Theta^{-\frac{1}{2}}_K\bar{\mathbf{Z}}_K^T$

