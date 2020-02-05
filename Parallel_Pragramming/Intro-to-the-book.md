##Introduction terms

###Speedup factor
$S_p=\frac{t_s}{t_p}$
execution time using one processor/execution time using p processors

superlinear speedup with $S_p>p$

###Efficiency
$E=\frac{t_s}{t_p \times p}$

###Overhead
1. Ilde period.
2. Extra computations
3. Communications between processes

####Amdahl's law
$S(p)=\frac{t_s}{ft_s+(1-f)t_s/p}$
* if f=0, then S=p maximum speedup.
* if f=1, then S=1 no speedup at all.

###Scalability
####Scaled speedup factor with constant $t_p$
$S_s(p)=p+(1-p)ft_s$

###Message-Passing Multicomputer
bandwidth, latency, cost

###Shared memory multiprocessor system
NUMA, non-uniform memory access

###Cluster computing
####Ethernet connections
####Network Addressing
####Hardware configuration
master node + compute node.
frontend
####software configuration
NFS file system