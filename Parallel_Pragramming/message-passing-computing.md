##MPC, message passing computing
###Process creation
master process and slaves/workers
####static process creation
SPMD. single program multiple data: the program is compiled into executable code for each processor
####Dynamic process creation
compile on master and slave can be done separately. Spawn

###Message-Passing routines
* Synchronous Message-Passing:
* Blocking and NonBlocking Message-Passing:
  * Blocking, process can not continue until the transfer is completed
  * NonBlocking, routines that return whether or not the message had been received.
  * Locally Blocking, routines that return after their local actions complete.
* Message-Selection:
* Broadcast, Gather, Scatter:

###Using a cluster of computers
###MPI
####进程创建和运行
* A communicator defines the scope of a communication process.
* **Any global variable will be duplicated in each process.**
* Blocking routines: return when locally completed.
* NonBlocking routines: returns immediately. Isend, Irecv, Wait, Test.
* Send communication modes:
  * standard, buffered, synchronous, ready
* Collective communication

###Evaluating parallel programs
####Execution time
$t_p=t_{comp}+t_{comm}$
* **communication time will depend on the number of messages, the size of each message, the underlying intercommunication structure, the mode of transfer**.
* Speedup factor: $\frac{t_s}{t_{comp}+t_{comm}}$.
* Startup time one or two orders of magnitude greater than the transmission time.

####Time complexity
* when considering parallel computers, we need to identify the **scatter time, computing time on each process, gather time, root computing time**.
* Cost and Cost-optimal algorithms: the parallel algorithm is optimal if **parallel time complexity x number of processors = sequential time complexity**
* **the communication aspect does not exist for shared memory programs**

####Communication time of Broadcast/Gather
* whether the message sent or received are sequential.

###Debugging and Evaluating parallel programs empirically
####Low level Debugging???
####Evaluating programs
* measuring execution time, clock(), time(), gettimeofday(), MPI_Wtime()
* Profiling, a histogram showing the time spent on different parts of a program.

###Optimizing parallel code
* increase the amount of data sent
* recompute values locally than to send them
* overlap communication and computation
* critical path analysis: find the longest path that dominate the entire program
* memory hierarchy: cache is quick but small.