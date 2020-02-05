##Variance filtering
1. allocate variance (i,j,k) and cm4
2. computer variance
   1.var(i,j,k)=Xb'(i,j,k,n)*Xb'(i,j,k,n);
   2.cm4(i,j,k)=...
3. filtering variance
   1.call ens_par_fil
      1. if using prescribed scale, call dif_opt_3d directly
      2. if using optimized scale, solve function $\mu^S [\tilde{v}^2]-\frac{N+1}{N-1}\mu^S [\tilde{v}\cdot\hat{v}]$ using bisection method.
         1. in the bisection method, using const diffusion tensor to accept the length scale
         2. call dif_opt_3d 
         3. compute the function, if not zero, reduce the length scale
      
   how $\mu^S$ is calculated? in the code, simply sum all horizontal variance(scaled by the volumn element and scaled back afterwards), 
      
      