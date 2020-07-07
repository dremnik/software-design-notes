# Debugging

**Look for familiar patterns**
* Think about common error patterns that occur, such as not initializing variables, or not using &
  for pointers. (e.g. for `scanf`)

**Examine the most recent change**
* What was the last change? The bug is likely to be in the new code, or was exposed by the new code.
* Keep previous versions of the code that you believe to be correct.


**Don't make the same mistake twice**
* If you fix a bug, ask whether you have made that bug in another place as well.

**Debug it now, not later**
* Being in too much of a hurry will lead to undesirable consequences later, when you accrue technical debt.

**Read before typing**
* One underrated technique is to read the code very carefully and think about it for a while, without making changes.
* Chances are if you don't really know what's broken, you will break other things if you don't think about it first.
* Take a break for a while, sometimes what you see in the code is what you meant rather than what you wrote.


No Clues, Hard Bugs
-------------------

**Make the bug reproducible**
* The first step is to make sure you can make the bug appear on demand. Spend time constructing input and parameter
  settings that reliably cause the problem, then wrap it up in a recipe so it can be run with a few keystrokes.
* Include debugging output options in your programs, such as random seeds or allowing random seeds to be set.

**Divide and conquer**
* Try to narrow down the parts of the program that are definitely not causing the problem, which reduces the
  amount of surface area that you have to worry about.

**Write self-checking code**
* If you need more information, write a function that tests a condition, dumps relevant variables, and aborts the program.
* Leave this function in after you fix the bug, as you might need it later.

**Write a log file**
* Be sure to flush I/O buffers so the final log appears in the log file. In C, a call to `fflush` ensures that all
  output is written before the program dies.
* Network servers often contain extensive logs so that you can see the state of the server at all times.

**Draw a picture**
* If you don't understand what's happening inside your program, try annotating the data structures with stats and then plot the result.
* One example of this being helpful is seeing the distribution of hash table bucket sizes in the markov program
  using different multipliers.


Source: *The Practice of Programming | Kernighan & Pike*
