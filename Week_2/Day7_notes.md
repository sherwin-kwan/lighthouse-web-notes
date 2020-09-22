## Day 7

### Instructor

* New instructor: Andy Lindsay, Lighthouse alumni, worked in a blockchain-adjacent company before joining LHL full-time as an instructor

### Asychronous Code

* Asychronous code always runs after synchronous code. 
* Example: if a timer before an alert is set for 0.1 seconds, and the rest of the synchronous code in the file takes 1 second to run, all of the latter runs before the timer-enabled
alert appears.
* Exception: Using "async - await", you can force asychronous code to run as though it were synchronous

### setTimeout and setInterval

* setTimeout(cb, X) causes callback to run after X milliseconds
* setInterval(cb, X) causes callback to run repeatedly every X milliseconds
* clearInterval is used to cancel a setInterval call (it's usually done in response to an event, like the user leaving a webpage)

### Reading Files

* fs.readFile(*file*, *encoding*, *callback*)
* failing to enter encoding will cause the computer to attempt to read it as a string of binary/hex numbers
* the callback for this kind of function always takes two arguments in Node: *(err, data)* so it's called "error first". This means that if the function throws an error for any reason,
the error object will be accessible through that first argument; and if the function successfully obtains data, it will be accessible through the second argument.
* you do NOT need to actually call the two arguments *err* and *data*, it's just conventional to do so to make the code easier to understand

### Andy's Tips

* prefer to use *const* over *let*, a useful check to make sure when I use constants, I mean it
* if you define an asynchronous function, *const abc = setTimeout(cb, timer)*, abc is assigned the value of an object of the Timeout class (so you can use it to clearInterval 
if you need)
* DO NOT, EVER, use *eval*. (It's a function that allows you to run code in a user-submitted file. It's valid JavaScript but a huge security risk)