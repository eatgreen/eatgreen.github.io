ict(nl*nc)
   ict(il,nc)=1
   ict(il,1) =nc

read fld: nv*nl*ncells

for isub=1
for each ensemble member ie
   for each class ic
      for each variable iv
         for each level il
            for each sampling points is
               iterative computing:
               delta0 is the difference between the sample point and the corresponding m1
               deltai is the difference between the class points around the sample point and the corresponding m1

