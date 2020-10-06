## Day 17 - 6 Oct 2020

### Client-Side Javascript

* Client-side Javascript is run out of a browser. This is distinct from the server-side Node/Express Javascript we have been doing

Server-side JS | Client-side JS
---|---
JS files are placed on server, compiled into webpages, and the webpages are sent to the client's browser | JS files are sent to the client's browser and run on their computer
Allows you to use templates like EJS or Pug, or tools like Express | Allows you to use tools like jQuery, Angular, or React
Have access to objects like: process, module.exports, fs | Have access to objects like: window, document (DOM), location
You link one script to another with module.exports and require | You link one script to another by calling both in an HTML file

### The DOM

* The main (and in fact, original) purpose of Javascript was to do things to the elements on a web page (you can even add additional pictures, words, etc. that aren't in the HTML with JS!)
* All browsers (for 20+ years) have supported the Document Object Model, which converts every single HTML element (tag) into a Javascript object with properties and methods
* The DOM is arranged as a tree, with "document" at the top. Tags placed within other HTML tags will show up as child nodes in the DOM tree
* You can directly write standard Javascript; however, since browsers don't all work exactly the same way, it's often advisable to instead use a library like jQuery that abstracts out browser differences

### DOM Manipulation

* *document.createElement('tagname')*: create a new HTML tag \<tagname>
* *document.getElementByName*: access the properties and methods of an existing HTML tag
* *\<element\>.createEventListener(type-of-event, callback)*: start listening for events and run the callback function whenever the event fires
* *append*: a very common method to add additional text or HTML to an existing node

### jQuery

* jQuery abstracts away browser differences and has some special features not available in traditional JS
* However, it's starting to be on the way out, as all modern browsers are standard compliant and JS has improved to add a lot of the same special features
* You use ${'CSS_Selector'} to access an element (node) in jQuery
* Use *next* to go to the next element (to traverse the DOM)
https://api.jquery.com/category/traversing/tree-traversal/


### Hafiz's Tips

* Using *this* sometimes doesn't work properly (e.g. if using arrow functions, calling a function within a higher order function, etc.); using *event.target* could be a useful replacement for a function that handles an event firing
* By convention, we begin all variable names with *$* if the variable is assigned to a jQuery object


