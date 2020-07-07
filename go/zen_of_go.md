The Zen of Go
-------------

**A good package starts with a good name**
* In Go, each package should have a purpose, and the best way to determine it is the name (a noun).
* Your program *will* change over time, therefore it is important to make it adaptable to change.
  One way of achieving this is modularization using packages.

**Simplicity matters**
>There are two ways of constructing a software design: One way 
>is to make it so simple that there are obviously no deficiencies, and
>the other way is to make it so complicated that there are 
>no obvious deficiencies. The first method is far more difficult.”

* Often it is more work to make something simple.
* "Controlling complexity is the essence of computer programming." - Kernighan

**Avoid package level state**
* Coupling is a measure of the amount one thing depends on another. If two things are
  tightly coupled, they move together. An action that affects one affects the other.
* When you need to change a piece of code, all the code that is tightly coupled to it must change.
* Avoid package level state. Reduce coupling and spooky action by providing the dependencies a type
  needs as fields on that type rather than package variables.

**Plan for failure, not success**
* Explicit error handling in Go forces programmers to think about failure cases first, and that is
  one of the factors in Go's success as a language. It leads to robust programs.

**Return early rather than nesting deeply**
* Avoid control flow that requires deep indentation.
  * Using guard clauses to return early if a precondition isn't met.
  * Placing successful returns at the end of function rather than inside a condition block.
  * Reducing overall indentaion level of the function by extracting functions and methods.

* Every time you indent you add another precondition to the programmer's stack, consuming one
  of their 7 short term memory slots. Rather than nesting deeply, keep the successful path
  close to the left hand side of the screen.

Source: [Small ideas | Dave Cheney](https://dave.cheney.net/category/small-ideas)
