###### Objective
I have been reflecting on what I did implemented for the estimation of $Q$, the model error covariance, and I have found something rather vague to me. This short document is to present my understanding of this problem along with possible solutions. You are welcome to correct any wrong statements that I made.

#### Gaussian noise
We start from the following system (6) in the manuscript
\\[x_k=\phi_k(x_{k-1},a)+\xi_k\\]
where $\xi_k$ is a zero mean Gaussian process with \\(\xi_k\in \mathcal{N}(0,Q)\\). The objective is to find the optimal $a$ and $Q$ given observations $y$ from 0 to K alongside with systems (7) and (8).  Our decoupled strategy for $a$ and $Q$ is plausible because $Q$ is independent of $a$.

#### Diffusion process
Our system (5) is not as simple as system (6). We know that the model error covariance matrix $Q$, is related to the stochastic parameter, namely the diffusion tensor $\sigma$ in system (5) in the manuscript. Recall the starting point of stochastic formulation, we decompose the Eulerian velocity field $U$ according to
\\[U=w+\sigma d\dot{B}_t\\]
or the displacement field $X$:
\\[dX=wdt+\sigma dB_t\\]
where $w$ and $\sigma$ encode, in simple expressions, the mean and the variance of $U$.

We know the system (5) can be written as:
\\[d_t x = F(x,a)dt + G(x,\sigma)dB_t\\]
where the variance tensor $a$ is related to $\sigma$ through relationship, not rigorously put, $a=\sigma\sigma^T$. Again, $F$ and $G$ represent the conditional mean and covariance of the infinitesimal change of state $x$ respectively. But the transition distribution $p(x_t|x_{t-1})$ is not easily known. 

##### What the algorithm should be done
###### Estimating and resampling $Q$
As we discussed, we can estimate $Q$ using equation (45) in the manuscript and resample the noise $\xi$ using SVD technique. In this vein, we pretend \\(p(x_t|x_{t-1})=\mathcal{N}(\mu(x_{t-1}),Q)\\) to be Gaussian distributed with mean $\mu(x_{k-1})$ and covariance $Q$. 
This assumption coincides with formula (13) in the manuscript that is based on the system (6) where a Gaussian noise is assumed. 

###### Estimating $\sigma$ directly
An alternative way is, I think, to estimate $\sigma$ directly. Unfortunately, the method discussed in current manuscript can not be used. Again the reason is that the formulations (12), (13) and (14) are derived from equation (11) based Gauss-Markov process assumption.

##### What I implemented
So in my algorithm, in practice, I did compute the optimal model error covariance $\hat{Q}$ as suggested in algorithm (1) but I do not do a SVD on it to resample the noise. On the contrary, as soon as I obtain the optimal $\hat{a}$ in the M-step, I do a SVD on $\hat{a}$ and obtain $\hat{\sigma}$ that is directly used to agitate the system. The fact that there are other terms such as \\(\partial_x h\\) contributing the noise terms, makes obtaining $\sigma$ interesting. Although this approach is wrong, theoretically.

##### Numerical results
Despite the fundamental theoretical differences between resampling the covariance matrix $Q$ and employing directly the parameterized $\sigma$, I presume that the numerical results should be largely independent of the noise terms. Because the magnitude of $\sigma$ needs to be severely reduced by order of magnitude to avoid numerical instability.

#### Pulido et al. (2018)
The noise term in Pulido et al. (2018) assumes following: