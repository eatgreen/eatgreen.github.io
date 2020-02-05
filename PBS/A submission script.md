Suppose we want to run a molecular dynamics MPI application called foo with the following requirements

the run uses 32 processes,
the job will not run for more than 100 hours,
the job is given the name "protein123" and
the user should be emailed when the job starts and stops or aborts.

```js
#!/bin/bash

# set the number of nodes and processes per node
#PBS -l select=4:mpiprocs=8

# set max wallclock time
#PBS -l walltime=100:00:00

# set name of job
#PBS -N protein123

# mail alert at (b)eginning, (e)nd and (a)bortion of execution
#PBS -m bea

# send mail to the following address
#PBS -M my.address@dept.ox.ac.uk

# use submission environment
#PBS -V

# start job from the directory it was submitted
cd $PBS_O_WORKDIR

# define MPI host details
. enable_hal_mpi.sh

# run through the mpirun launcher
# mpirun $MPI_HOSTS foo
```

\#PBS -l walltime=100:00:00 time limite
\#PBS -l select=4:mpiprocs=8 select the nodes and mpiprocs is the number of mpi processors

###PBS array jobs
a series of jobs using a single submission command with a single script

###PBS jobs with conditional execution
qsub -W depend=afterok:7777 second_job.sh