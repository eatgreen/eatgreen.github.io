compute_avg
for each variable
   for another variable
      for each level
         for each class
            **m11(nsub,nv,1,nl,nc,ns) means for each variable and each level, in terms of each sample point, we have nc number of covariance stored**
            avrage covariance(nv,nv,nl,nc)=avg over nsub(avg over ns)

compute_avg_local
for each sample point is
   for each varaible
      for another variable
         for each level
            for each neighbor point around is
               avrage covariance(nneff,nc)=avg over nsub of m11(nsub,iv,1,il,nc,isn)

compute_avg_asy