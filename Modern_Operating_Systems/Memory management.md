Memory Hierarchy, smaller and faster memory closer to cpu, and bigger but slower memory further.

Memory manager: keep track, allocate, deallocate

1. No memory abstraction
   one process at a time.

2. a memory abstraction: address spaces
   2.1 a set of addresses that a pocess can use to address memory.
         base and limit registers:  base register->starts of the program in memory
                                    limit register->length of the program
                                    con: additon and comparison must be performed upon every memory reference
   2.2 swapping
         to tackle overload, 
            memory compaction: compact memory to avoid holes between two program memory chunks.
   2.3 managing free memory
         bitmaps: 
         linked lists: specified hold or process, the starting address, the length and a pointer to next entry.
            * search for memory allocation, first fit, next fit, best fit, worst fit
            * seperate list for process and holes, quick fit

3. Virtual memory
   pages
   3.1 paging, MMU (memory management unit) 