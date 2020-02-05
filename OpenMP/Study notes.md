1.loop level, each thread has a unique range of the loop index. 
2.parallel regions. 
3.data dependencies. 
   All assigments are performed on arrays.
   Each element of an array is assigned to by at most one iteration.
   No loop iteration reads array elements modified by any other iteration.
4.parallel for
5.clauses:  
   shared vs private variables
   private variable: a separate memory location is allocated for each specified variable on each thread.
   loop index, i is always private in the loop.
   FIRSTPRIVATE: 
   LASTPRIVATE:
   
   Reduction operations:
   