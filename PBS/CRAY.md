###CRAY

###MPI-3

###module framework

module load ...
module unload ...
module avail
module swap PrgEnv-cray PrgEnv-intel

PATH, MANPATH, LA_LIBRARY_PATH

tip
1. put module list in job script
2. use the module info to find documentation

###TOOLS
modify->debug->optimise
debug: DDT, Totalview
profiling: Apprentice2, MPIIO Stats

module load atp

STAT

LGDB

CCDB

###Performance Analysis
performance is not portable!
* effective algorithms
* implementation: process and memory usage
* parallel scalability

###end of scaling
comptational time for each task is small compared to communication

###instrumentation of code
* adding special measurement code to binary

###point-to-point communication consuming time
* post MPI_Irecv before MPI_Isend
* minimizing data to be communicated
* eager protocal

###Expensive collectives
* all-to-all -> one-to-all or all-to-one
* basic version instead of vector version
* hand-written RDMA (Remote direct memory access) 

###Bottlenecks due to I/O
* paralleliza I/O, netcdf, hdf5
* hide I/O
* Tune filesystem (Lustre) parameters
* Use I/O buffering for all sequential I/O
* When using MPI-I/O and making non-contiguous writes/reads (e.g. multi-dimensional arrays), always define file views with suitable user-defined types and use collective I/O

###Apprentice2
qsub run_XXX.pbs
sampling and tracing

####Automatoc program analysis