## Day 31 - 26 Oct 2020

## REACT

### Intro

* React is a JavaScript framework created by Facebook for the purposes of allowing quick, dynamic updates on a webapp
* It is a *declarative* framework, you tell it what to make and it makes it using its own algorithms. So it's a higher-level way of coding a webapp than just writing JS
* The basic unit of React is a component 
* Components can be created either using JS classes or functions
* The advantage here is that React provides a system where component *states* can be saved in code

### A React App

* *create-react-app* is a tool that creates a template (boilerplate) React app
* it comes with:
  * a *public* folder, in which *index.html* is the main web page (React is mainly designed for single-page applications e.g. Facebook News Feed, but there is a React router which allows multi-page applications to be built). In practice, you won't be changing much in the public folder, index.html is just a foundation into which you'll inject components using React
  * a *src* folder, containing all .js and .css files for individual components

### JSX

* A templating language, combining JS and HTML, used in React
* Each component is defined as a function, whose return value is the HTML for the component
* In JSX, you use { ... } to place JS expressions inside HTML (kind of like <% %> in EJS)
* JSX allows you to do funky stuff like define an entire HTML node as a variable and using {} to interpolate it
* All tags must be self-closing. <input ...> is valid HTML but in JSX you must write <input ... />
* in JSX, you set CSS classes with "className", not "class"

### React Tools

* *Babel*: a tool which translates JSX into JS and HTML to put into your browser
* *Webpack*: a dev-tool that compiles a React app into static webpages to send to the browser (so there is actually no need to have a server constantly sending data back and forth with the client)

### State

* A property of a component which is variable when the component is active, in real time (not to be confused with a *prop*, a variable which is passed to a component as an argument, but once the component is created it doesn't change)
* Note: You *cannot* just define a property inside a component and change it afterwards and expect that to change the page; a component is a JS function and once the function is finished running, the property is out of scope
  * So state has to be set up; React doesn't render anything unless it knows something has changed. This is why it's so quick to load.
  * This is done using something called a *hook*: a method of a React class  
  * using array destructuring:
  ```javascript
  const [name, setName] = useState('initial value');
  ```
* To pass a state back to a parent function, you have to use some kind of callback e.g. a prop which is a function

### React

* Every time you use a list or array, expect to use *map* in order to convert a raw array into a format that React can use


