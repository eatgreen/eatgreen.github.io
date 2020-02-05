## Monte Carlo Markov Chain

### The Metropolis-Hastings algorithm

1. Draw initial $\theta^0$ from $p_0(\theta)$. 

2. For $t=1,2,\cdots$

   - Sample $\theta^*$ from $J_t(\theta | \theta^{t-1})$

   - calculate the ratio of the densities
     $$
     r=\frac{p(\theta^*|y)/J_t(\theta^*|\theta^{t-1})}{p(\theta^{t-1}|y)/J_t(\theta^{t-1}|\theta^*)}
     $$

   - Set 
     $$
     \begin{align}
     \theta^t&=\theta^*\quad &\text{with probabilit min}(r,1) \\
     \theta^t&=\theta^{t-1}\quad &\text{otherwise.}
     \end{align}
     $$


Gelman, A., Carlin, J. B., Stern, H. S., Dunson, D. B., Vehtari, A., & Rubin, D. B. (2015). Bayesian Data Analysis, Third Edition, 1–656.