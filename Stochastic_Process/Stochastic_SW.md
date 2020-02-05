# The transition distribution of stochastic shallow water model
The system (5) cab be compactly expressed following form:
$$
d_t x = F(x,a)dt + G(x,\sigma)dB_t
$$
where $x$ is the state and a function of space and time.

#### Is the transition distribution Gaussian?
This is an important question. We know that the integral form of above equation is:
$$
x_t=x_0+\int_0^t F(x,a)dt + \int_0^t G(x,\sigma)dB_t
$$

##### Gaussian connection
The Ito integrals will give Gaussian processes if the integrand is nonrandom.

##### Not Gaussian After all 
The Ito integrals of random part $\int_0^t G(x,\sigma)dB_t$ do not yield a Gaussian process because $G$ is a function of $x$ that is random.

#### Approximative solutions

A Euler discretization on system (5) lead to:
$$
h_t-h_{t-1}=F(h_{t-1},a)\Delta t + G(h_{t-1},\sigma)\Delta B_t
$$
Which gives a pseudo-likelihood:

$$
E(h_t|h_{t-1})=F(h_{t-1},a)\Delta t\quad \text{and}\quad Var(h_t|h_{t-1})=G(h_{t-1},\sigma) \Delta t G(h_{t-1},\sigma)^T
$$
$F$ is the deterministic part whose treatment is nothing but follows standard PDE procedures. Here $G=\partial_x h \sigma$, so $\text{Var}(h_t|h_{t-1})=\Delta t \partial_x h \sigma \sigma^T (\partial_x h)^T$.