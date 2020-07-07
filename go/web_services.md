You want to build a web service?
--------------------------------

**Logging**
* Consider what you are going to include in your logs before you even write any code.
* Your mental models and metrics of the code base has to working during development.


**Config**
* There has to be some kind of centralized configuration structure, so that it doesn't become a mess to find.

**Debug**
* One helpful library for debugging is net/http/pprof

**Shutdown**
* Every week, you want to turn on the server, and then shut it down with an interrupt signal to make sure
  that your shutdown code is working.
* The shutdown should be clean, and only be able to happen at the application level. Packages may be able to signal
  that a shutdown might be necessary, but they shouldn't have the ability to shut it down.

Source: [You want to build a web service?](https://www.youtube.com/watch?v=IV0wrVb31Pg)
