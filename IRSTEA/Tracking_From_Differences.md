## Tracking from differences Jurie et Dhome 2001

Let $I(\mathbf{x}_{1:N},t)$ the luminance function of location $\mathbf{x}_{1:N}$, we want therefore to track this template at $t+1$.

We assume that the image coordinate $\mathbf{x}_{1:N}$ is the projection of $\mathbf{X}_{1:N}$ the 3D coordinates in object space. And they are linked through:
$$\mathbf{x}=M(\mu(t))\mathbf{X}$$
a linear relationship where $\mu(t)$ contains 3 translational components and 3 Euler angles.

The aim is to minimize the following cost function:
$$J(\mu(t))=|| I(M(\mu(t))\mathbf{X},t) - I(M(\mu_0)\mathbf{X},t_0) ||$$
It is possible to obtain $\mu_{t+\tau}$
$$\mu(t+\tau)=\mu(t)+A(t+\tau)[I(M(\mu(t))\mathbf{X},t) - I(M(\mu_0)\mathbf{X},t_0)]$$
where $A$ is the gradient of $I(M(\mu(t))\mathbf{X})$ with respect to $\mu$.

### Obtain matrix $A$

We can perturb $\mu'_0=\mu_0+\delta \mu$, and recompute its projection in image space 
$$\delta i=I(M(\mu'_0\mathbf{X}) - I(M(\mu_0)\mathbf{X}).$$
Through $N_s​$ samples, it is possible to minimize the least square
\\[
\sum_{k=1}^{N_s} ||\delta \mu^k - A\delta i^k ||^2
\\]
It is then left to compute:
\\[
A=(H^T H)^{-1} H^T Y
\\]
where
\\[
H=(\delta i^0, \cdots, \delta i^{k-1})\quad Y=(\delta \mu^0,\cdots,\mu^{k-1})
\\]

### Efficient 3D matching
