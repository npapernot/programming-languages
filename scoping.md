[Back to home](https://npapernot.github.io/programming-languages)

## Scoping

## Static scoping

**The static scope of a variable is defined by the most
immediately enclosing block, and excludes all enclosed
blocks redefining the variable.**

Static scope can be determined at compile time, and is
not modified by the order in which functions are executed
at run time. 

**Stack**: as function calls are made, their activation
records are added to the stack, which includes allocated
space for the variables declared in that function. That
activation record is popped from the stack upon return.

**Heap**: memory allocated remains in existence for the
duration of the program, unless explicitely deallocated.
Caller function passes to the callee pointers to its
stack values themselves pointing to the heap. 

## Dynamic scoping

**The dynamic scope of a variable is defined by all
functions called after its decleration, until it is
redeclared by a called function.**

Dynamic scope cannot be determined at compile time, and
is modified by the order in which functions are executed
at run time. 

**Stack**: as activation records are created, they
contain pointers to the most recent declaration of the
variable. All pointers from previous stack frames
are forwarded to the new stack frame. 
