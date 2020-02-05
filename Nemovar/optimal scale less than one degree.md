###Variance filtering
We see the filtering scale halves every iteration.
In the variance filtering procedure, 
* we filtering the raw variance based on the initial local scale.
* we calculate the criterial function value based on the raw variance and the filtered variance.
* if value is not zero, try a new local scale by bisect, until zero out the function.

We see many of the local scale is less than one which is smaller than the grid spacing. Suggesting no filter at all.

###Hessian filtering
* We filter the unnormalized $H_uii$ in order to get the optimal length scale using bisection method.
* We filter the normalized $Hii$ using pre-determined optimal length scale.
* Because we hcange the target, we need to do it twice.

