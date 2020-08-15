# Netflix Web Performance Case Study

Reducing Time-to-Interactive by shipping less JavaScript
--------------------------------------------------------
* If you can ship less JS, you will get a better loading time for users, particularly if they are
  using suboptimal connections.
* In the case of Netflix, they switched their home landing page from React to vanilla JS to improve performance.
* They were able to reduce the TTI for logged-out homepage by over 50%.

Prefetching React for subsequent pages
--------------------------------------
Another performance optimization involves using the time that users are spending on the homepage in order to prefetch
pages that they are likely to visit next.

* There are two techniques for prefetching which are the in-built browser API of using <link rel=prefetch>, while the
  other technique is to use XHR. XHR cannot fetch HTML docs, but it is better at fetching CSS and JS bundles.
* By using these two techniques to prefetch, TTI was reduced by 30%.

These optimizations show that React is a great library for many instances, but it is not always the best solution.
This makes sense as the main benefit of using React is the handling of changing state. If on the home page, for instance,
there is no changing state, it doesn't necessarily make the most sense to add the overhead of loading React.
However, despite them removing React from the homepage, they were still able to prefetch it for the subsequent pages.

Source : [netflix-web-performance](https://medium.com/dev-channel/a-netflix-web-performance-case-study-c0bcde26a9d9)
