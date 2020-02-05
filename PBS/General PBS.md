qsub
qdel
qstat
qstat -Q -f queue

1 PE (processing element) = 1 MPI rank = 1 task
1 CU (computational unit) = 1 core = 1 physical CPU
1 CPU = 1 logical CPU (hyperthreading)
1 node = 2 NUMA nodes

PBS job attributes can be set in two ways
1. command line arguments to qsub
2. as PBS directives in a control script submitted to qsub

qsub
-o stdout path
-e stderr path
-p priority
-q destination of the job
-l requesting resources
-I interactive sessions

Vnode: virtual node
chunk, one chunk per MPI process
chunk-level resource, 
   -l select=6:ncpus=2:mem=4gb
   -l select=6:ncpus=2:mem=4gb+3:ncpus=8:mem=4GB   
job-wide resouce,