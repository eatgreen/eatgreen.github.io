Conjugate gradient method:
Basically, it is intended to solve Ax=b, which equals minimizing 
￼
The search direction is said to be A-conjugate since 

The gradient is: r=Ax-b, actually the residual, and the gradients are mutually orthogonal.
 
The current search direction is a linear combination of the former search direction  and the former residual 
 
 
Lanczos method: 
In order to solve the  large, sparse, symmetric Eigen problems, a sequences of tridiagonal matrices are generated and the extreme eigenvalues of are progressively better estimates of A's extreme eigenvalues.
The Lanczos vectors 
 
 
 
The relationship between two methods:
Conjugate gradient to Lanczos methods:
When we have the residual matrix and an upper bidiagonal matrix 
 
Lanczos methods to conjugate gradient:
 