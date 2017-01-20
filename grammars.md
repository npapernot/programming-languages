[Back to home](https://npapernot.github.io/programming-languages)

## Grammars

**Regular languages** over an alphabet are defined recursively as:

* empty language and empty string are regular languages
* for each alphabet symbol, the singleton is a language
* the union, concatenation, and Kleene star of regular languages is a regular language


**Attribute grammar**: an attribute grammar is a context-free grammar
augmented with attributes, semantic rules, and conditions. It can 
for instance recognize languages such as `S=x^nb^nc^n` for all `n>=0`.
See [this book chapter](http://homepage.divms.uiowa.edu/~slonnegr/plf/Book/Chapter3.pdf) for more details.
