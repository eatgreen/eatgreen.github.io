###load balancing
we want all processors to perform evenly on tasks.

static load balancing as mapping problem/scheduling problem.


###dynamic load balancing
####Centralized
* slave processor requires a new task from the master when it finishes the given task.
* master determines when to terminate if
  1. all slaves are idle and made a request for new task
  2. task pool is empty
* bottleneck when many slaves making simultaneous requests.

####Decentralized
todo...