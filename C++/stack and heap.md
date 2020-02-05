#The heap: new and delete
*  Allocating memory on the heap is comparatively slow.
*  Allocated memory stays allocated until it is specifically deallocated (beware memory leaks) or the application ends (at which point the OS should clean it up).
*  Dynamically allocated memory must be accessed through a pointer. Dereferencing a pointer is slower than accessing a variable directly.
*  Because the heap is a big pool of memory, large arrays, structures, or classes can be allocated here.

#The call stack
active functions, handles allocation of all function parameters and local variables.
When a function call is encountered, the function is pushed onto the call stack. When the current function ends, that function is popped off the call stack. 
*  Allocating memory on the stack is comparatively fast.
*  Memory allocated on the stack stays in scope as long as it is on the stack. It is destroyed when it is popped off the stack.
*  All memory allocated on the stack is known at compile time. Consequently, this memory can be accessed directly through a variable.
*  Because the stack is relatively small, it is generally not a good idea to do anything that eats up lots of stack space. This includes passing by value or creating local variables of large arrays or other memory-intensive structures.

Basically, you should only use "new" if you want an object to live beyond the lifetime of the scope you create it in. That done, you need to use "delete" to destroy it.

Code that creates an object using new and then deletes it at the end of the same scope is ugly, error-prone, and inefficient.