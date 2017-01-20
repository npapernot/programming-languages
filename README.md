## Welcome

I am listing here some notes about programming languages.

### Content

* [Proofs of equivalence (by induction) for standard ML functions](standard-ml-function-equivalence.html) 
* [Notes on recursion](recursion.html) 
* [Notes on grammars](grammars.html) 
* [Notes on object-oriented programming](oop.html) 
* [Notes on scoping](scoping.html) 

### Other notes

**Higher-order function**: a function that takes a function as
at least one of its arguments.

**Parameter passing strategies**:

* **call-by-value**: the parameter's value is evaluated and passed as an argument
* **call-by-value-result**: same than call-by-value, but the parameter value updated by the callee is copied back to the caller on return of the callee
* **call-by-name**: the parameter value is not resolved, and the name is passed. The value is evaluated lazily upon usage.
* **call-by-reference**: pass reference to callee (thus the callee and caller have access to the same object)

### Support or Contact

If you have any suggestions or happen to catch a typo/error in
these notes, feel free to reach out to me
on [Twitter](https://twitter.com/NicolasPapernot).
