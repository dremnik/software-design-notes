# Performance

**Use a profiler**
* Use a profiler to find the *hot spots* in your program which consume the most time and resources.
* "less than 4 percent of a program accounts for more than half of the running time."

**Draw a picture**
* If you plot the performance of your program using different implementations, that will give a good
  sense of the differences visually.

Strategies for Speed
--------------------
**Use a better algorithm or data structure**
* This is the most important factor in making a program faster.
* Make sure that the complexity is really what you expect, otherwise there may be a hidden performance bug.

**Enable Compiler Optimizations**

**Tune the code**
* This means adjusting the details of loops and expressions to make things go faster.
* One example I am thinking of is checking for presence of a key in a python dictionary.
  * My original thought was `key in dictionary.keys()` but you could obviously just do `dictionary.get(key)`,
    which returns None if the key isn't in the table, eliminating the necessity of checking the entire list of keys.

**Don't optimize what doesn't matter**
* Sometimes tuning will do nothing because it is applied where it doesn't make a difference.
* How much effort should you spend making a program faster? - Do the changes yield enough to be worthwhile?
* The personal time should not be more than the time the speedup will recover over the lifetime of the program.

Tuning the Code
---------------
**Collect common subexpressions**
* If an expensive operation occurs multiple times, do it once and remember the result.

**Replace expensive operations by cheap ones**
* Perhaps you want to decide which of two points is further away in a plane, but don't need the actual distance.
  Instead of computing the distance formula with the sqrt, you could omit the sqrt and compare the squares. 
  (The bigger distance will also have a bigger square). This avoids unnecessary computatation.

**Cache frequently used values**
* Cached values don't have to be recomputed, they can simply be looked up for later.
