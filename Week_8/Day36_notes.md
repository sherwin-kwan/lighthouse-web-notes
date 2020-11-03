## Day 36 - 2 Nov 2020

## Testing with React

* *Test-driven development* (TDD): A style of development where you write your tests before writing your code, to test for what the requirements are
* Initially, all tests will fail (red). After writing code, all tests will pass (green). After that, repeat the test whenever you re-factor.

### Jest

* Syntax and output are similar to Mocha, describe() and test() (which does the same things as *it()*)
* Jest testrunner/framework comes with create-react-app by default
* Jest-dom: an extension to Jest that allows for testing of React components, like "assert if this has a CSS class"
* Jest works like Mocha too: if there is an error inside a test, fail. If no errors, pass. (Yes, this means that an "empty" test always passes)

### Testing Library

* Testing-library: a family of libraries that provide specific testing functionality for front-end frameworks. This includes DOM Testing Library, React Testing Library, Angular Testing Library, etc.
* React Testing Library and DOM Testing Library come with create-react-app by default

### React Router

* Something that lets you use routes in a React app - duh!

### Definitions

* *Integration testing*: A "glorified unit test", testing how components interact
* *End-to-end testing*: The highest level of test, which directly tests whether user stories are fulfilled

### How to Run Tests

* remember: *npm run test -- --verbose* to get details of the tests in Jest
* when running a coverage test, expect lots of errors. This is normal. This will generate a *coverage* folder in your project folder.
* Write a *beforeEach* in your test file, which resets the state to some default. (Otherwise, state persisting from the last test run might interfere with your tests)
* Common edge case: Include a test where functions get no arguments
* *toContain* is a predicate you can write with *expect*, so it tells you "expected X to be part of array Y" instead of "Expected false to be true"

### Using React-testing-library

* *render* function: allows you to render React components which you can evaluate in a test
* *get....* and *query...* methods: the difference is that get throws an error if the node is not found in the DOM, whereas query just returns null if the node is not found. 
* *find...* methods: for asynchronous code, returns a promise which resolves to a node when it appears (i.e. tells Jest to expect a node to appear at some future time)
* *prettyDOM*: a method that prints the entire DOM so you can debug without opening a browser
* *debug*: also shows the DOM
* Two ways to import a method from this library, if we do:
```js
const { container, getByTestId } = render('<Game />');
```
* This getByTestId automatically knows which container to look in (not true for a global import), or in technical terms, it's *bound*
* *fireEvent*: allows an event (like user clicking a button) to be tested
```js
findByText('Carol', {exact: false})
```
* *exact: false* tells Jest not to expect an exact match

### Mocking

* **Never test against live data.** For example, do not test that a real customer, "Mary Jane", has the high score. Your test shouldn't fail because a customer deletes their account!
* Instead, a fake database with known data should be used for testing. This is called *mocking*
* fn() is a Jest method which creates a mock function
* mock('libraryName') is a Jest method which creates a mock library. Every time, say, axios.get() appears in the real code, this mock version of axios will be used instead.
* *axios.get.mockResolvedValueOnce({data: abcde})*: use this to create a mock API call, which will output the object *abcde* as the data response



### Andy's Tips and Advice

* In most small companies, devs also write all the tests
* Large organizations, however, will probably have a dedicated QA team
* Sandi Metz, *POODR*: *If you're the first person to start something in an organization, the code that you write today will echo into eternity*.
* The point: people just follow the coding practices of previous developers, and especially for testing because no one likes writing their own tests. So if you're the first to write tests, better make damn sure it's good testing code!
* *Technical debt*: When a company skips proper testing in the early going because there's no time or resources for it, so-called because it incurs debt just like financial debt; eventually, the bill comes due and you have to spend a lot more time or resources to fix it
* There exist two schools of thought in writing component tests:
  * a) Write tests the same way that your customers will use the site: a test could be like "Find the word 'Click me!' and click on it". Advantage: Closest to user experience, Drawback: If the text ever changes in the future, the test has to be re-written.
  * b) Use an HTML dataset property which will never change, like put a data-attr on 'Click me', so even if it changes in the future, the test does not have to be re-written.
