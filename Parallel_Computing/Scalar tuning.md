Tune scalar code to decrease the runtime
1. Aggresive compiler options: It should be noted that -O3 might carry out loop transformations that produce incorrect results in some codes.
2. compiler optimization
   * statement level: 
      1. constant folding
      2. short circuiting
      3. register assignment
   * block level:
      1. dead code elimination, Remove unreachable code and code that is never executed or used.
      2. instruction scheduling, Reorder the instructions to improve memory pipelining.
   * runtine level:
      1. Strength Reduction, Replace expressions in a loop with an expression that takes fewer cycles.
      2. Common Subexpressions Elimination, Expressions that appear more than once, are computed once, and the result is substituted for each occurrence of the expression.
      3. Constant Propagation, Compile time replacement of variables with constants.
      4. Loop Invariant Elimination, Expressions inside a loop that don't change with the do loop index are moved outside the loop.
   * software pipelining: Software pipelining allows the mixing of operations from different loop iterations in each iteration of the hardware loop. It is used to get the maximum work done per clock cycle.
   * loop unrolling: In loop unrolling the loops stride (or step) value is increased, and the body of the loop is replicated. It is used to improve the scheduling of the loop by giving a longer sequence of straight line code. 
   * subroutine inclining: inline function.
   * optimization report: 
   * profile-guided optimization(PGO)
3. Vendor tuned code
      
      