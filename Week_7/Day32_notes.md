## Day 32 - 27 Oct 2020

### State

* React is only monitoring variables within its JSX functions. If you try to create a global variable to set state and change it, React will *not* update the page as it does not monitor the global variable.
* The *proper* way to save the state is with *useState*

### Immutable Update Patterns

* In Javascript, by default arrays and objects are mutable ... we can add new keys or push values to arrays
* In React, if we have a state variable which is an *object* or *array*, we should create a new object (not just a new variable which points to the same object in memory)
* To illustrate the difference, see what happens when we use a spread operator: 
```js
const userCopy = {...user}; //Copies the key-value pairs of user but saves to a new object - now changing the new object does not change the original
```

* Benefits of immutability:
  * Easier to test and reason about
  * Removes side effects (called *pure functions*)
  * **Makes it possible to compare current function to previous version** (in React, re-renders only happen when current state doesn't match the previous state)

* Bottom line: Never use Arr.push or Object.assign to modify a state which is an array or oejct!!! Always use setState like this:

```js
  const [text, setText] = useState(['a', 'b', 'c']);
  /* DO NOT WRITE
  text.push('d');
  */
  // INSTEAD WRITE:
  setText[...text, 'd'];
```

* When state is updated with setState, React will actually register the change and know it's time to re-render

### Andy's Tips

* Good to have a *components* folder to hold all your components
* JSX can be written in .js or .jsx files (either works, they are equivalent in a React app) - but by convention I use .jsx for files containing components
* When using an array as a state variable, it's useful to include a "key" property when iterating over it to create nodes (so React can internally tell the difference between the nodes ... otherwise it generates a warning)