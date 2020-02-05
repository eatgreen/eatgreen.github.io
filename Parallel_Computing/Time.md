#Timing
##Timing a section of code

FORTRAN
* etime, dtime, cpu_time for CPU time
* time and f_time for wallclock time
C
* clock for CPU time
* gettimeofday for wallclock time
 
* CPU time
   * etime: elapsed CPU time since the program started.
   * dtime: the elapsed CPU time in seconds since the last call to dtime.
   * cpu_time: substantially higher resolution and has substantially lower overhead than the older etime and dtime routines
   * clock
   
      Description of the etime and dtime Functions
      *  User time. This is returned as the first element of tarray. It is the CPU time spent executing user code.
      *  System time. This is returned as the second element of tarray. It is the time spent executing system calls on behalf of your program.
      *  Sum of user and system time. This is the function value that is returned. It is the time that is usually reported.
      *  Metric. Timings are reported in seconds. Timings are accurate to 1/100th of a second.

* Wall clock time
   * time 
   * f_time
   * gettimeofday

##Timing an executable
time (options) a.out
 
##Timing a batch run
origin
busage

linux clusters
qstat
qhist