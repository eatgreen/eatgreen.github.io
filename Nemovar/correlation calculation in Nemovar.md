##bge\_cor\_loc\_tst

First loop *j\_var* in *jp\_totvar* (total variable t,s,u,v...)  
	second loop *j\_loc* in *jp\_totloc* (total localization points)

We have *z\_t*  for single correlation and *z\_tot\_t* for total correlation.

Fill the interesting locations with 1.

###Localization model test

*cormod\_opt\_3d* using *fensloc\_t(1)* and *z\_t*: apply $C$ to *z\_t* in which the correlation matrix $C$ is defined through *fensloc_t(1)*.

$C\cdot z\_t$ then is set to $z\_{dx}$.

###Ensemble raw correlation test

Basically apply $\hat X_b' \hat X_b'^T$ to get the correlation w.r.t different locations.