## Day 38 - 4 Nov 2020

## Cypress

* For end-to-end testing: instead of testing individual components, we test user stories directly (as a user, I should be able to ____), so simulate that happening!
* Generally best to install as a dev dependency (although Compass recommends global install)
* A Cypress directory contains these sub-directories:
  * Fixtures: mock data
  * Integration: the actual tests. There is an example folder by default.
  * Plugins: add-ons for Cypress functionality
  * Support: other extras
* Tests run by default in alphanumeric order (it's normal to use numberings "01", "02", "03" or timestamps to ensure tests run in the correct order)
* No need to import Cypress, it's available automatically within the cypress folder once you've run *node_modules/.../cypress open* (best to write an NPM shortcut here for *cypress open*)
* Cypress uses a Mocha/Chai nucleus, so use the normal syntax
* *cypress.json* is a file where you set your Cypress settings

## How to Use Cypress

* Each test is separate. Thus remember to put *cy.visit* again to ensure each test begins with visiting the webpage.
* Tests should replicate how a user does things - ideally, don't even look at the code at all, design the tests by trying what a user would do
* It is not usually needed to *assert* anything, just ask Cypress to *get* things (if Cypress can't find it, it throws an error to fail the test)
* All Cypress commands return promises (not like Jest where only *find* is asynchronous whereas *get* and *query* are synchronous)
* DOM traversal is a thing in Cypress
* Use { delay: 1000 } [ms] to make things happen on delay
* Remember to test inputs going backwards! Like, what happens if you hit "backspace"?
* cy.____.as('@search') ... creates the variable "@search" which can be called later on (@ is Cypress's equivalent to jQuery's $)
* *cy.server* - creates a fake server
* *cy.route* - allows you to get fake data from the fake server
* Note: Cypress doesn't even know that it's testing a React application! There is total separation of concerns here, we write tests entirely in the "cypress" folder (since it just opens a browser)