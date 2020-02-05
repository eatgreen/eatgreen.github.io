The randomization method is used to get the estimatio of the standard deviation.
Basically we apply $B^{1/2}dv$ where $dv$ is a random vector $N(0,I)$

But in bge_covsqt_opt, we apply the square root of the background error covariance operator. 
NOTE THAT THE SDV IN THE CONSTRUCTION OF B IS CONSTANT ALL OVER THE PLACE WHICH IS NOT GOOD AND CAN CAUSE SOME LOCAL ISSUES.

