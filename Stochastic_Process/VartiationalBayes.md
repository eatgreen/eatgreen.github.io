## Variational Expectation-Maximization algorithm

### What have I done so far

We concentrate on estimating the parameter as a point estimation (i.e. Dirac delta function).

### Bayes approach

- we search for the mode rather than mean
- mode as a posterior summary
- EM can be used to find the marginal posterior mode
- In the case of many parameters, the joint mode is not helpful. 

### Varitional Bayes

The goal is to estimate $g(\theta)$=that minizes the Kullback-Leibler divergence from the target posterior distribution $p(\theta|y)$
$$
\text{KL}(g||p)=-E_g\Big(\text{ln}(\frac{p(\theta|y)}{g(\theta)})\Big)=-\int\text{ln}\Big(\frac{p(\theta|y)}{g(\theta)}\Big)g(\theta)d\theta
$$




