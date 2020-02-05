### List of changes
1. Add $ln Q$ in equations 13 and 38.
2. Delete $\beta$ in equations 38, 39 and 42. Corresponding discussion on $\beta$  is also deleted.
3. Add a resampling procedure in algorithm 1.
4. Substantial changes to section 5.3.1 about the comparison made regarding dimension of $Q$. 
5. Substantial changes to section 3 about the (additional) optimization strategy on $Q$.
#### some discussions
1. We have a rather vague preset about system (5) that describes a diffusion process whose transition distribution $p(x_t|x_{t-1})$ can hardly be Gaussian.  Nevertheless, in the practice of the manuscript, we **pretend** the transition distribution given by system (5) is Gaussian. Then we are able to estimate the covariance matrix $Q$ and subsequently resample the model noise from $Q$. A point needing specified is that, by such resampling procedure, which is the same as in Dreano et al. (2017) and Pulido et al. (2018), we will use the square root of $Q$ directly to agitate the system, rather than using the structural coefficient $\partial_x h \sigma$ and $u\partial_x h \sigma$. 
2. On point 4 in list of changes: since we use similar resampling procedure to obtain additive Gaussian noise, the negative arguments that we made on the inability of EM in Dreano et al. (2017) in dealing with high dimensional system, needs to be withdrawn. On the contrary, the arguments on equation (45) involving ensemble anomaly matrix that admits better decompositions can be added. 
3. I think the current EM method is unable to deal with the parameter estimation problem associated with the original system (5). Because the formulations (12), (13) and (14) are derived from equation (11) based Gauss-Markov process assumption.
4. A notable difference compared to Delsole and Yang (2010) is that, Delsole and Yang (2010) considered the problem of estimating the stochastic parameter (the constant diffusion coefficient), whilst our approach focused on estimating the deterministic parameter (the variance tensor) combined with a (pretended) Gaussian error covariance matrix.  
