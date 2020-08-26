Fetching data at request time
-----------------------------

There are a few strategies for fetching data at request time (instead of at build time):

* Using `getServerSideProps`:
  ```
  export async function getServerSideProps(context) {
	  return {
		  props: {
			  // props for component here
		  }
	  }
  }
  ```

* Client-side rendering: works well for something like user dashboards, which are private and do not need
  SEO optimization.

* SWR: a React hook for data fetching made by the Next.js team.
