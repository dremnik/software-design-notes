# Web Vitals

Core Web Vitals
---------------
* Largest Contentful Paint (LCP): measures *loading* performance. For a good experience, this should occur
  within **2.5 seconds** of when the page first starts loading.
* First Input Delay (FID): measures *interactivity*. Good experience: FID of less than **100 ms**.
* Cumulative Layout Shift (CLS): measures *visual stability*. Pages should maintain a CLS of less than **0.1**

### Tools for measuring Web Vitals

The easiest way to measure the web vitals is to use the [web-vitals](https://github.com/GoogleChrome/web-vitals) library.

You can also use Chrome DevTools to measure LCP and CLS in a lab environment.
