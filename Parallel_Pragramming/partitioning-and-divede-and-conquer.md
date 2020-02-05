###Partitioning
####data partitioning/domain decomposition and functional decomposition
a single broadcast has a single startup time compared to separate startup times when using multiple send routines

or scatter and reduce_add.

####Divide and conquer
recursion, a tree construction.

###Examples.
####Bucked sort
* sequential code
* parallel code: one region for each processor, sort into small buckets, communicate into larger buckets.

####Numerical integration

####N-body problem
octtree