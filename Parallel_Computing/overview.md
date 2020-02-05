#HPC: fast CPUS, large memory, high speed interconnect, high speed i/o.
Gigabytes of memory and gigaflops of performance.

1. Data Parallelism: same code with its own data
2. Task Parallelism: concurrently running subroutines. Easier to implement and less overhead than DP.

#Operating system: 
#Arithmetic parallelism:
#Memory parallelism: 
1. memory interleaving
2. multiple memory ports
3. multiple levels of the memory hierarchy
4. cache memory

#Disk parallelism
1. RAID disk, redundant array of inexpensive disk
2. disk striping

#Performance measures
1. load balancing: the technique of evenly dividing the workload among the processors.
2. problem size: 
3. good software tools: parallel compilers, debuggers, performance analysis tools, parallel math software
4. workstation farm
5. condor

#HPC features
##Processors: Massively Parallel Processor (MPP). 
##Memory organization: 
1. distributed memory: NUMA, Non-Uniform Memory Access time
   data locality, easy to scale, difficult to implement
2. shared memory: UMA, Uniform Memory Access time
3. distributed shared memory: DSM

##Flow of control
* SIMD, lock step
* MIMD, asynchronously
* SPMD, special MIMD

##Interconnection networks
The time required to transfer data, communication time.
The maximum distance that data must travel for 2 processors to communicate and high, high bandwidth, the amount of data that can be sent through a network connection, are the most important characteristics of a network. 
1. Bus network
2. Cross-Bar switch network
3. Hyper-cube network
4. Tree network/database application

