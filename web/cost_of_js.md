# The Cost of JavaScript in 2019

Actionable high-level guidance
------------------------------
* **Improve download time.**
  * Keep your JS bundles small. This improves download speeds, lower memory usage, and reduce CPU costs.
  * Avoid having just once large bundle; if a bundle exceeds 50-100 kB, split it up into separate smaller
    bundles. (With HTTP/2 multiplexing, multiple request and response messages can be in flight at the same time,
	reducing the overhead of additional requests.)

* **Improve execution time**
  * Avoid long tasks that keep the main thread busy and delay TTI. Post-download, script execution is now a dominant cost.

* **Avoid large inline scripts** (they are still parsed on the main thread). A good rule of thumb is: if the script
  is over 1 kB, avoid inlining it (also because 1 kB is when code caching kicks in for external scripts).

There is a large discrepancy between lower end phones and higher end phones in CPU speed. This means that the more JS that
you load on the site, the slower the experience will be for users with lower end devices.

*Long Tasks* monopolize the main thread and delay user interaction. A Long Task is JS code that monopolizes the main
thread for extended periods of time and causes the UI to freeze. These are also shown in Chrome DevTools with
red flags on the corner of the rectangle.
