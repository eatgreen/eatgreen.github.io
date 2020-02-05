###Synchronization
####MPI_Barrier
called by each process.
* counter implementation:
* tree implementation:
* butterfly barrier

Deadlock: may occur using synchronous routines if both process perform the send first because neither will return.

combined blocking sendrecv().

####Synchronized computations
* data parallel, forall. explicit barrier is needed for MPI.
* synchronous iterations: termination, MPI_Allgather
* heat distribution system:
  $x_i=\frac{x_{i-1}+x_{i+1}+x_{i-m}+x_{i+m}}{4}$.
  this is quite universal in the sense that it reflects the idea of solving any linear equation, a point's value is impacted by its nearest neighbors.
  * block partition: communication happens on all edges
    $t_{comm}=8(t_{start}+\frac{n}{\sqrt{p}}t_{data})$
  * strip partition: communication happens at two longevity edges.
    $t_{comm}=4(t_{start}+nt_{data})$
  * ghost points.
  * safety and deadlock. only one process perform send first.
    * sendrecv routines
    * buffered send where explicit storage space is provided
    * non blocking, isend, irecv.

###Partially synchronous methods
synchronous degrades parallel power:
**asynchronous iterative methods**