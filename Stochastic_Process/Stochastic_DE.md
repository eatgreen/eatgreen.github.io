## Stochastic Differential Equation

#### General form
$$d X_t = \mu(t,X_t)dt + \sigma(t,X_t)dB_t$$
#### Constant coefficient form
$$d X_t = \mu X_tdt + \sigma X_tdB_t$$
Its solution can be obtained through matching coeffiencts:
$$X_t=x_0 exp[(\mu-\frac{1}{2}\sigma^2)t+\sigma B_t]$$

#### Ornstain-Uhlenbeck process
$$dX_t=-\alpha X_t dt + \sigma dB_t$$ with $\alpha$ and $\sigma$ are constants representing the infinitesimal change of $X$. 
###### Ito’s Isometry
$$E\Big[( \int_s^t b(w,u)dB_u )^2 |F_s\Big]=E(\int_s^t b^2(w,u)du|F_s)$$
which can be used to evaluate the variance of a stochastic process.

We continue with Ornstain-Uhlenbeck process, whose mean is 
$$E(X_t)=x_0 e^{-\alpha t}$$
and the covariance is
$$Var(X_t)=\frac{\sigma^2}{2\sigma}(1-e^{-2\alpha t})$$
**Note that the mean and variance of $X_t$ are function of parameters $\alpha$ and $\sigma$.** In order to obtain the mean and variance, we need to *solve* the SDE, or obtain the transition distribution $p(X_t|X_{t-1})$.  