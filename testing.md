# Testing

Systematic Testing
------------------
**Test incrementally**
* Testing should happen alongside program construction. If you try to test large program at once,
  it will likely have more complexity than you can handle.
* Write part of the program, test it, add some more, test it, etc.

**Test simple parts first**
* Only move on to testing and writing more complex components after you are sure the simple ones work.

**Know what output to expect**
* If you don't know what output you should expect, you are wasting your time.
* Compare your program's results to known results.

**Compare independent implementations**
* If two unrelated programs, ( but which do the same computation ) arrive at the same result, they are likely correct.
* If there is a symmetrical process, such as encryption and decryption, one person can write each one, so that bugs
  are unlikely to be duplicated, and therefore caught early.

**Measure test coverage**
* You want to make sure the maximum number of statements have been executed at some time during the sequence of tests.


Test Automation
---------------
* It is tedious and unreliable to do much testing by hand. Proper testing involves lots of tests, lots of inputs, and
  lots of comparisons of outputs.
  It should therefore be done by programs, which don't get tired or careless.
* It is worth taking the time to write a script or trivial program that encapsulates all the tests, a complete suite
  can be run with one push of a button.
* Never throw away a test.

**Automate regression testing**
* Compares previous versions of something to a new version.
* The implicit assumption in regression testing is that the previous version does in fact compute the correct results.
  This is an invariant that must be carefully maintained.


Test Scaffolds
--------------
* Often programs are nested within much larger structures, which means that many times you will have to construct enough
  of an interface to test the individual components on their own; in other words, a scaffold for each of them.
* When you are constructing test suites, you build up incrementally as mentioned earlier. 
  You start by testing the most simple aspect, which gives you confidence in that piece. Then you can compare the more complex
  results to this simpler piece to verify that the additions didn't break anything.


Stress Tests
------------
* Running high volumes of machine input into programs is another good way of finding errors in them.
* Random inputs are another way to assault a program in the hope of breaking something.

**Examples**
* Any program that reads files should be tested on an empty file; any program that reads text on binary data;
  any program that reads text lines on huge lines and input with no newlines.


Tips for Testing
----------------

* Make the hash function return a constant. This will check the chaining mechanism.
* Write a version of your storage allocator that fails early. This will check how your code recovers from out-of-mem errors
* Before you ship code, disable the testing limitations. 
* Initialize arrays and variables with distinct values, rather than zero. If you access out of bounds, you
  are more likely to notice.
* Vary test cases
* Don't keep implementing new features or even testing existing ones if there are known bugs; they 
  could be affecting test results.
* Test output should include all parameter settings, so the tests can be reproduced.


