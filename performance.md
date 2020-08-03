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
* Caching takes advantage of *locality*, the tendency for programs (and people) to re-use recently accessed or nearby items.
* It's best if the caching operation is invisible from the outside, so it doesn't affect the rest of the program except runtime.

**Write a special purpose allocator**
* Often of hot spot in a program is memory allocation, which manifests as a lot of calls to malloc or new. When most request are for
  blocks of the same size, a special purpose allocator can make one call to malloc to get a big array of items, and hand them out
  one at a time. Freed items are placed in a *free list* to be reused quickly.

**Precompute results**
* Sometimes you can precompute values so they are ready when they are needed. If a graphics system needs to repeatedly compute a math
  function like sine, but only for a discrete set of values, it would be faster to precompute a table with the values and then
  refer to them when necessary.

Space Efficiency
----------------

The first approach these days to optimizing space should be the same as improving speed: *don't bother*.
However, there will sometimes be situations in which it will be necessary to save space.

**Save space by using the smallest possible data type**

**Don't store what you can easily recompute**
* Changes like this are minor. Major improvements are likely to come from better data structures, perhaps with algorithm changes.

Summary
-------

Once you have chosen the right algorithm, performance is usually the last thing to worry about as you write a program. If you must think about it,
however, the general process is to measure, and focus on the hot spots that will make the most difference, and verify that your changes are correct.
Benchmarking can be managed in a similar way to the management of testing. Timing tests are run automatically; outputs include enough
identification that they can be understood and replicated; records are kept and significant changes can be observed.
