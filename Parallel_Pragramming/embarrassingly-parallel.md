## Embarrassingly parallel computations
### An ideal parallel computation can be dived into completely independent parts. _No Communication_

### Examples:
#### Geometrical transformation of images
many image processing operations are embarrassingly parallel.

####Static Task Assignment

####Dynamic Task Assignment-Work Pool/Processor Farms
load balancing:
work-pool approach, individual processors are supplied with work when they become idle.

The program is structured in the sense that the slave process receives the workload and then do the work, as the work is finished, it send result_tag to the master, and wait for the next workload to be send to it.

* Monte-carlo code: 