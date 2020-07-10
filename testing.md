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

**Automate regression testing**

