##Average variance

Note that the horizontal average variance computed directy from ensemble_variance netcdf file is averaged over mask and non-mask. The online computation is right because it excludes the mask points.

###For T variance
* No variance eduction for T when $Bmod_{varpar,hespar}$
* Very small T variance reduction for Bmod with ensemble estimated/filtered variance and diffusion tensor $Bmod_{varpar,hesens}$
* Progressively smaller for T variance reduction for $Bmod_{varens,hesens}$
* For $Bmod_{varpar,hesens}$, the T variance reduction, we have a curve lying between v1 and v2 at higher levels, and a curve very close to v1 at lower levels.

###For S variance
* No variance eduction for S when $Bmod_{varpar,hespar}$ for all levels
* Significant reduction for S variance for $Bmod_{varens,hespar}$ for upper and middle levels
* Even more reduction for S when $Bmod_{varens,hesens}$ for upper and middle levels, very close to Bens case
* No reduction for all Bmod cases in deep level

| level | T varens | T varpar | S varens | S varpar | level | T hesens | T hespar | S hesens | S hespar |
|-------|----------|----------|----------|----------|-------|----------|----------|----------|----------|
| 1     | 0.08777  | 0.23419  | 0.04663  | 0.11042  | 1     | 3.41E+9  | 3.24E+9  | 1.52E+9  | 3.24E+9  |
| 11    | 0.13665  | 0.34342  | 0.02705  | 0.13383  | 11    | 1.92E+9  | 3.11E+9  | 1.91E+9  | 3.10E+9  | 
| 21    | 0.05827  | 0.08485  | 0.00663  | 0.02072  | 21    | 2.40E+9  | 3.03E+9  | 2.86E+9  | 3.02E+9  |
| 31    | 0.00835  | 0.00587  | 0.00146  | 0.01396  | 31    | 3.20E+9  | 2.70E+9  | 3.62E+9  | 2.77E+9  |
| 41    | 0.00137  | 0.00014  | 0.00007  | 0.00243  | 41    | 5.76E+9  | 9.48E+8  | 3.62E+9  | 9.47E+8  |

The increasing of the Hessian eigen spectrum is mostly due to the small variance at deep level with longer correlation length.

####salinity ensemble variance
* For S, S2 and S3 reduction of variance progressively diminish along depth > 21, why?
   var too small
* For S, S4 increase a bit from level 1->level 11, then diminish, what happened?
* For S, S1 show very small reduction, in terms of magnitude, larger at shallow levels, smaller at deeper levels.

####temparature ensmeble variance

Recall the devil equation
\[X^{a'}_K=X^{b'}_K+\hat{Z}_K(\Theta_K^{-1/2}-I_K)\bar{Z}_K^T X^{b'}_K
\]
In terms of matrix product, one can write as vector product,
\[X^{a'}_K=\Big(I_n+\sum_{k=1}^K(\Theta_k^{-1/2}-1)\hat{Z}_k\bar{Z}_k^T\Big) X^{b'}_K
\]

Imagine we have an eigenvalue 10,2500 respectively, the eigenvectors are the same:
\[X^{a'}_K=\Big(I_n-0.9\hat{Z}_k\bar{Z}_k^T\Big) X^{b'}_K
\]
\[X^{a'}_K=\Big(I_n-0.98\hat{Z}_k\bar{Z}_k^T\Big) X^{b'}_K
\]
In terms of the magnitude, it is clear that large eigenvalues can cause smaller magnitude of $X^{a'}_K$, so generally v3 and Bens v1,v2 have more compact eigen-specturm. This leads to more reduction of variance. 

But locally at certain levels where there is no variance reduction, simple mean at that level/that point, the effect of bkg matrix is low. This directly relates to the small ritz values. We see no reduction means 
$\sum_{k=1}^K(\Theta_k^{-1/2}-1)\hat{Z}_k\bar{Z}_k^T$ is close to zero. This can nevertheless be true for total points. So for a certain level,
\[X^{a'}_K[T_{lev}]=X^{b'}_K[T_{lev}]+\sum_{k=1}^K(\Theta_k^{-1/2}-1)\hat{Z}_k\bar{Z}_k^T X^{b'}_K
\]

in which the $X^{b'}_K[T_{lev}]$ corresponds the a portion of data. And $\sum_{k=1}^K(\Theta_k^{-1/2}-1)\hat{Z}_k\bar{Z}_k^T$ should be considered as those rows corresponding to the bkg error covariance matrix on that level. to make the product zero, there are two possibilities:

*  for a diagonal bkg matrix, the eigen values are solely determined by the error variances. So if an error is small, thus the inverse of variance is high. When we solve, the first ritz value and ritz vector solved are associated to this particular point. The variance reduction thus is large and only depend on the first ritz value and ritz vector. So basically, the smaller bkg errors, the larger eigen values associated, and larger ensemble variance reduction. So no reduction suggests unit eigenvalues?

*  after introducing correlation


###For SSH variance
* No ssh variance change for Bmod onlt case suggesting no analysis increment for ssh component. This is because no balance operator is posed at this stage (which is applied at the end of minimization process when computing the increments from control space into model sapce).
* Bens case with correlation scale from ensemble-estimated diffusion tensor, $Bens_{mulloc}$, we have significant variance reduction in T, S and SSH.

##Analysis ensemble increments
The norm of $\delta X_a$:
$||Bmod_{par}||<||Bmod_{var}||<=||Bmod_{varhes}||<||Bens_{mulloc}||$
Part of the norm of $Bens_{mulloc}$ comes from the ssh increments.

##Ritz values
Sum of Ritz values, 
* $Bmod_{varpar,hespar}$ nearly linear increasing agaist iterations. 
* $Bmod_{varens,hespar}$ slower increasing but with much lower Ritz values compared to $Bmod_{varpar,hespar}$
* $Bmod_{varpar,hesens}$ is closer to $Bmod_{varpar}$. why?

Slower increasing indicates good preconditioning; smaller Ritz values indicates smaller magnitude of Hessian. Since the Hessian is,
   $\nabla^2 J=B^{-1}+H^TR^{-1}H$
   smaller magnitude of Hessian indicates the smaller $B^{-1}$, consequently with bigger $\sigma_b$
   smaller Ritz values ---> bigger background error.
   so here the ensemble estimated/filtered variance is bigger than the parameterized one.
   
This also explains higher curve of $Bmod_{varpar,hesens}$. Parameterized variance is relatively higher. Even though the correlation operator is constructed using hessian ensemble. 

* $Bmod_{varens,hesens}$ with the highest Ritz values

   but $Bmod_{varhes}$ introduce much higer Ritz value and much faster convengence rate. Note that we are using the same kind of variance but with different diffusion tensor.
   
| case                                                   | conclusion                                                                                  |   |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------|---|
| $Bmod_{varpar,hespar}$ v1 vs $Bmod_{varens,hespar}$ v2 | same structure of correlation matrix, magnitude of variance determines the shape of Hessian |   |
| $Bmod_{varpar,hespar}$ v1 vs $Bmod_{varpar,hesens}$ v4 | similar Hessian profile, slightly smaller for v4 due to longer length scale in correlation function    |   |
| $Bmod_{varens,hespar}$ v2 vs $Bmod_{varens,hesens}$ v3 | different in the sense of few larger eigen values, flatness is similar indicates close convergence issues, this is related to the correlation length scale  |   |
| $Bmod_{varens,hesens}$ v3 vs $Bmod_{varpar,hesens}$ v4 | totally different  |   |

* $Bens_{mulloc}$ with the fastest increasing of Ritz values suggesting a good eigen-spectrum of Hessian, nearly the first 5 iterations can extract a large portion of the eigen-spectrum.

##Filtering, how the filtering works in reducing the variance, and the Hessian tensor.