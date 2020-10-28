## Day 33 - 28 Oct 2020

## State

* Every time a component renders, its function is run again
* A "remembered value" for the next time the function runs

## Side Effects

* *Pure function*: A function which does nothing except take inputs and produce an output, with no side effects
* A function ceases to be pure if it either requires variables that are not passed to it as arguments (i.e. env variables) or produces effects other than its return value
* Asynchronous functions inherently have side effects (they do a request and respond to it)

## UseEffect

* A hook of React, used to cause particular actions to asynchronously run, only when necessary
* Takes two arguments: a callback function, and an array containing dependencies. Whenever one of the dependencies changes, the callback runs
* The callback executes solely via *side effects* (not via return values) - because it's running asynchronously, it cannot pass info back into the main function
* Warning: useEffect can cause infinite loops - if the callback increments a counter, and the dependency is "count" ... every time the callback runs, changing the count will call itself to run again, ad infinitum.
* Alternatively, some kinds of actions (setTimeout or event listeners) are dangerous, if you put them in a useEffect, a *new* timer or event listener is created each time the useEffect triggers ... you could eventually end up with hundreds of timers, slowing down your whole app!
* useEffect is most commonly used to fetch data from external APIs or from a database. Use it for **all** asynchronous operations!

## Cleanup

* The way useEffect solves this issue is allowing you to put a *cleanup* function in the return
* Every time the useEffect is run after the first time, or when the component is *unmounted*, the cleanup function is run immediately before running the effect. So a *new* timer or event listener is added, but the *old* one is removed.

## Stale State

* One common bug that happens, for example in this function that creates a timer to increments by one each second
```javascript
useEffect(
  setInterval( () => {
    setTimer(time + 1);
  }, 1000);
, []);
```
* Here useEffect has no dependencies, so it only runs once, and during that single run, it sets *time* to the initial value of 0. So every second, it will run the code *setTimer(1)* and the timer never increments past 1. (Even though the time has been set to 1, since the useEffect never runs a second time, the state of *time* is never updated and remains at 0 forever, so setTimer will only ever set time to 1).
* This is called a *stale state*, where an outdated state is baked into code.
* Avoid this by using functional state, as follows:
```js
setTimer((curr) => (curr + 1));
```
