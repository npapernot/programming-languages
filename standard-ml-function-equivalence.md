## Proofs of equivalence (by induction) for standard ML functions

Assume you are given the following function definitions
in [standard ML](https://en.wikipedia.org/wiki/Standard_ML).
The three functions all compute the factorial of an integer
n but are defined differently. The first function, `fact`,
is the naive tail-recursive definition of the factorial.
The second function, `ffact`, uses an accumulator. And
finally, the third one, `cpsfact` is a [curried](https://en.wikipedia.org/wiki/Currying)
version of the factorial.
