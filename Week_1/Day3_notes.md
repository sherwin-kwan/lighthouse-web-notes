### Day 3 - 16 Sep 2020

### Objects Tips

* Don't use dot notation if you're trying to use a variable to access an object key.
  * obj.variableName won't work
  * obj\[variableName\] will work however.
* Use "this" to refer to an object within a method within that object
* Unlike primitive types (e.g. numbers, strings), objects are stored *by reference* (with a pointer). When you write "obj1 = {a :1}", you're saving {a: 1} to a particular place in memory, and then saving the address (pointer) to that place in memory in the variable obj1.
* Corollary 1. You can change a const object.
``` javascript
const obj = {'one': 1, 'two': 2};
obj.one = 'aaa'; // No error
```
  Later, when you change the properties of an object, since it's still stored in the same position of memory, the object *hasn't changed* (still has the same pointer) so it won't throw an error for changing a constant.
  * Corollary 2: if you set one Object equal to another (or any other object type, like an Array), it's saving a reference to the *same* block of memory. Which means, with a primitive type, you can do:
  ``` javascript
let a = 3;
let b = a;
b = 2;
console.log(a); // a still = 3

// BUT

let objA = {a: 3},
let objB = objA;
objB.a = 2;
console.log(objA); // objA.a is now = 2. 
```

Changing the properties of objB changed the properties of objA because they are pointers which point to the same place in memory.

* Corollary 3: You can't use the equals operator on two objects.
```javascript
let arr1 = [1, 2, 3];
let arr2 = [1, 2, 3];
arr1 === arr2; // Expected: false because what's saved in arr1 and arr2 are pointers to separate copies of [1, 2, 3] in memory
```

