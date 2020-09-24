## Day 9 - 24 Sep 2020

### PROMISES!!

* Tired of "callback hell"? Then promises are the solution!

### Callbacks

* When function A is used as an argument to function B, A is called the "callback" and B is called a "higher order function"
* This has a lot of advantages when working with asynchronous code (when code has to wait for an event to happen and respond)
* But you can get into *callback hell*

```javascript

rl.question('aaaaaa', (answer1) => {
  rl.question('bbbbb', (answer2) => {
    rl.question('ccccc', (answer3) => {
      console.log(`${answer1} ${answer2} ${answer3}`);
    })
  })
})

```
* To avoid this, use *promises*

### Promises

* A promise is an agreement to do something later, in common parlance
* so in Javascript, a promise is an object which is created in a *pending* state, and at some future time, it will become either *rejected* (if there is an error) or *resolved* (if not)
* when a promise is resolved, it stores a value (number, string, object, etc.)
* when a promise is rejected, it stores an Error object (which explains why it could not be resolved)
* Most things that can be done with callbacks that can also do with promises
* To access the value of a promise, there are two methods:

*promise.then(callback)*: runs the callback function if/when promise becomes resolved
*promise.catch(callback)*: runs the callback function if/when promise becomes rejected
*promise.finally(callback)*: runs the callback function whenever promises are resolved or rejected (normally we wouldn't use)

* Normally, we will be using methods that return promises (we won't have to construct promises ourselves)
* Promise.then() can be chained in order to create a series of asynchronous code:
```javascript
originalMethodThatReturnsPromise('Hello world')
.then((result) => {
  return doSomethingWhichMakesAPromise();
})
.then((result) => {
  return doSomethingElseWhichMakesAPromise();
})
.catch((err) => {
  console.log(err.message);
})
```
* To actually construct a new promise:
```javascript
const myPromise = new Promise((resolve, reject) => {
  if (predicate) {
    resolve(valueResolved);
  } else {
    reject(valueRejected);
  }
});
```

After this, if myPromise.then() is called, it will receive *valueResolved*, and myPromise.catch() will receive *valueRejected*.

