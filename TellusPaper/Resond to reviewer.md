1. observation localization instead of domain localization
   B localization
   R localization, positive exponential function

2. inflation, 
   diffusion and trunction: `higher instrinsic growth rates of model and reduced error permit the simulation of a larger fraction of the error with the internal dynamics.

3. 4denvar vs enkf
   localization in state space.

4. denkf, no observation pertubation, simply halve the analysis pertubation. The same applies to eda-d where the spread is obtained without perturbing the observation. 

About the inflation, we can not use directly the identical inflation scheme as in enkf where either the forecast stare or the forecast covariance matrix is inflated. In 4DEnVar, each analysis is obtained through 4D ensemble. So we need to use sth similar to Fairbairn et al. 2014. 

Additive inflation: 
for PO-LC approach,

for DEn-LC approach,

for ET-LA approach,