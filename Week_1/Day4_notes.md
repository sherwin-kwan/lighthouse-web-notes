### Day 4 - 17 Sep 2020

### Callback Functions

* It's an anonymous function, usually expressed with arrow notation, that is passed as an argument to another function
* Note: This is possible because functions are objects in Javascript which can do everything that other objects can do
* They're useful because you can make functions modular - you can make a function call a variety of other functions
* Example: the "assertEqual" function can take a callback so it can call any number of other functions (checking if arrays,
objects, or primitives are equal)
* If we're making a 2D game, and we have a number of different functions to print out sprites, we can have a generic UI printing function
which calls the other functions as callbacks.

### Scope

* Warning: Calling a function within another function doesn't affect the scope chain. So if you define a local variable in function A,
and function A calls function B, you can't access that local variable within function B.
* However, you CAN define a function using local variables, return that function, and call it somewher else and still execute the function properly
* Difference between let/const and var: *let* and *const* have block scopes within functions (declaring *let X* inside a loop only makes *X* accessible within
that loop. However, declaring *var X* inside a loop makes it accessible in the whole function)

### Dev Pro Tips

* In real life, you'll rarely be coding anything from scratch. You'll be asked to improve existing code.
* Because time is short, you'll normally just find a small number of related functions and build on them, without understanding
what the rest of the code does. This is why callbacks and really valuable.