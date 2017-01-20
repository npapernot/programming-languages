[Back to home](https://npapernot.github.io/programming-languages)

## Object-oriented programming

**Overloading**: multiple functions have the same name, but
different signatures. 

**Overriding**: a function was inherited from a parent class,
but then modified in the children class.

**Generational garbage collection**: 

* heuristic: most objects have a short life

* generational garbage collection divides the heap in two parts: one for short-life objects, one for long-life objects

* it is not comprehensive (some old objects may never be collected)

* the short-life part is very small, and the long-life part is much larger

**Ideal collection algorithms for generational garbage collection**:

* stop and copy is best for short-life objects (cheap allocation, avoids fragmentation, run time proportional to number of objects) but not idea for long-life objects (half of the heap remains unused, lots of copying)

* mark-and-sweep is better for long-life objects (handles cycles, only requires one bit) but not good for short-life objects (need to stop program execution, runtime proportional to size of heap, ignores fragmentation)

* mark-and-compact is the same than mark-and-sweep but it handles fragmentation

**Value semantics**: value is copied upon assignment 

**Reference semantics**: pointer is copied upon assignment

Java uses value semantics for built-in types and reference
semantics for objects. C gives the choice: using the
assignment `operator` copies the value, and using a pointer
copies the reference. In Java all arays have reference
semantics. In C++, arrays are passed by pointer value, which
is not exactly either value or reference semantics.

**`Final` vs. `const`**: both are designed to hold variables
with a constant value. In C++, the value can only be modified
before the class is finished being constructed.
In Java, the value can be modified *once* after construction.
