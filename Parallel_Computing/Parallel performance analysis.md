#Speedup
sp=time for single run/time using p processors

##scalability
 The scalability of a parallel code is defined as its ability to achieve performance proportional to the number of processors used.
 
#Speedup extremes
* Super-linear speedup, the smaller problem can make better use of the memory hierarchy, that is, the cache and the registers
* Parallel Code Slower than Sequential Code
   The overhead of creating and controlling the parallel threads outweighs the benefits of parallel computation, and it causes the code to run slower. 

#Efficiency
Ep=Sp/p

#Amdahl's law
sequential part and paralleized part.

#Speedup limitations
* Too much I/O
* Wrong algorithm
* Too much memory contention
   delay
   A good way to reduce memory contention is to access elements from the processor's cache memory instead of the main memory. Some programming techniques for doing this are:
   *  Access arrays with unit stride.
   *  Order nested do loops (in Fortran) so that the innermost loop index is the leftmost index of the arrays in the loop. For the C language, the order is the opposite of Fortran.
   *  Avoid specific array sizes that are the same as the size of the data cache or that are exact fractions or exact multiples of the size of the data cache.
   *  Pad common blocks.
* Wrong problem size
   * The additional parallel overhead, compared to the amount of computation, causes the speedup curve to start turning downward
* Too much sequential code
* Too much parallel overhead
* Load imbalance