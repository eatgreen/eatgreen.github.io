###In congrad, we have 
\[(I+U^TG^TR^{-1}GU)\delta \tilde{u}=U^TG^TR^{-1}d\]
where
\[\tilde{A}=I+U^TG^TR^{-1}GU\]
In this case, we have the tridiagonal matrix $T_l$ by $\tilde{Q}_l^T\tilde{A}\tilde{Q_l}=T_l$
where $\tilde{Q}_l=(\tilde{q}_1,...,\tilde{q}_l)$.

The first residual equals the negative gradient:
\begin{align}
\tilde{r}_0&=U^TG^TR^{-1}d \\
&=U^Tr_0
\end{align}
the Euclidean norm of the redisual:
\begin{align}
||\tilde{r}_0||&=\sqrt{\tilde{r}_0^T\tilde{r}_0} \\
&=\sqrt{r_0^TBr_0}
\end{align}
The Lanczos vector $\tilde{q}_1=\tilde{r}_0/||\tilde{r}_0||$ whichis orthonomal to each other.

###In cgmod, we have 
\[(I+G^TR^{-1}GB)\delta \bar{u}=G^TR^{-1}d\]
The first residual equals the negative gradient:
\begin{align}
\bar{r}_0&=G^TR^{-1}d
\end{align}
and $z_0=B\bar{r}_0$
Two Lanczos vector $\bar{q}$ and $\hat{q}$ where
$\bar{q}_1=r_0/\sqrt{r_0^Tz_0}$ and $\hat{q}_1=z_0/\sqrt{r_0^Tz_0}$

we can see directly that $\sqrt{r_0^Tz_0}=\sqrt{\tilde{r}_0^T\tilde{r}_0}$ so we have the link with the Lanczos vector under congrad case:
$\tilde{q}=U^T\bar{q}$  
$\hat{q}=U\tilde{q}$.
Note that $\bar{q}$ and $\hat{q}$ are orthonoraml to each other.
$\bar{q}^T\hat{q}=\hat{q}^T\bar{q}=I$
$\bar{q}$ is not orthonormal to itself, but B-orthonoraml
$\bar{q}^TB\bar{q}=I$
$\hat{q}$ is not orthonormal to itself, but $B^{-1}$-orthonoraml
$\hat{q}^TB\bar{q}=I$





In order to formulate the tridiagonal matrix, we start by inserting $\bar{q}$: 
\begin{align}
\bar{Q}^TU(I+U^TG^TR^{-1}GU)U^T\bar{Q}&=T_l \\
\bar{Q}(B+BG^TR^{-1}GB)\bar{Q}&=T_l \\
\bar{Q}B(I+G^TR^{-1}GB)\bar{Q}&=T_l \\
\hat{Q}(I+G^TR^{-1}GB)\bar{Q}&=T_l \\
\hat{Q}(I+G^TR^{-1}G)\hat{Q}&=T_l \\
\end{align}
This $T_l$ is the same as the congrad form. But it is different from the unpreconditionned form.
 
###The unpreconditionned form 
$A\delta x=G^TR^{-1}d$ where $A=B^{-1}+G^TR^{-1}G$
we have $r_0=G^TR^{-1}d$ which equals $\bar{r}_0$ but the Lanczos vector $q_1=r_0/||r_0||$ which has nothing to do with $||\tilde{r}_0||$
we can formulate $Q^TAQ=T_l'$ but this $T_l'$ is not the same as $T_l$.