\alpha matrix size: n * N
\delta x = \sum_i=1^N X'^i_b \dot \alpha_i 

w: weight  matrix size: n * N
\delta x= [... X'^i_b \dot C' ...] w

Nemovar using hybrid B but without square root CVT. 
B-precondioned CG: no need to have the square root of B.