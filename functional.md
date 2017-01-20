[Back to home](https://npapernot.github.io/programming-languages)

## Functional languages

**Side effects** occur when a function modifies the
program state outside of its scope. They made formal
verification harder. Since pure functional languages
do not have side effects, they cannot immediately
accomodate I/O. Solutions exist: losing the pure
functionality, stream transformations, continuation-passing I/O. 

While **control-flow** relies on `while, for` loops
and other branching statements in iterative programming, 
functional programming only uses recursion. It is
completely state-less.

**First-class** objects can be dynamically created,
destroyed, passed to a function, returned as a value.
They have all the ''rights'' of other variables, and
can be functions. 

**Higher-order function**: a function that takes a function as
at least one of its arguments.

### Haskell

**Functor**: function on morphism. For instance, the
length of a list can be computed by concatenation and
addition. 

In Haskell, **types** are analog to sets of values. They
don't include type values and how to manipule them
(e.g., methods in OOP).
