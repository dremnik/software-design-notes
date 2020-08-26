# Dynamic Routes in Next.js

* Create file with form "/posts/[id].js"
* The page file must contain:
  1. A react component to render this page
  2. getStaticPaths which returns array of possible values for the *id*
  3. getStaticProps which fetches necessary data for the post with **id**
