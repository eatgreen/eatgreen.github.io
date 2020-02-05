Sequential code:
*  The code is not in a do loop.
*  The do loop contains a read or write.
*  The do loop contains a dependency.
*  The do loop has an ambiguous subscript.
*  The do loop has a call to a subroutine or a reference to a function subprogram.

Sequential code fraction:

Decreasing the sequential code fraction:
*  Removing dependencies
*  Removing I/O
*  Removing calls to subroutines and function subprograms

#Overhead
Parallel overhead is the processing time spent
*  creating threads
*  spin/blocking threads
*  starting and ending parallel regions
*  synchronizing at the end of parallel regions

To reduce parallel overhead:
*  Don't parallelize all the loops.
*  Don't parallelize small loops.
*  Use task parallelism instead of data parallelism. It doesn't generate as much parallel overhead and often more code runs in parallel.
*  Don't use more threads than you need.
*  Parallelize at the highest level possible.

#Load balance
Load balance is the even assignment of subtasks to processors so as to keep each processor busy doing useful work for as long as possible.

ps 

Improving load balance: 
*  changing the loop schedule type
   * static
   * dynamic
   * guided
   * runtime
*  changing the chunk size: means how many iterations are in the grouping