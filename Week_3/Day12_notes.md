## Day 12 - 29 Sep 2020

### Webapps

* Most webapps are skins that allow functions on a database
* The common functions are called CRUD: Create, Read, Update, Delete
* Another acronym that Andy likes better - BREAD: Browse, Read, Edit, Add, Delete
* *Morgan*, a useful tool that colour-codes request. Install on NPM

### Forms

* Forms can be used to GET or POST data (so even if you want to edit or delete a record in a database, still have to use POST)
* For each form, the HTML attributes *method* and *action* (URL) set the route that the form submits to
* remember that each input has to have a *name* attribute - this is what the property will be called in the *body* object
* POST - REDIRECT - GET: After filling out a form, it's conventional to, after reading the POSTed data, to redirect the user to a new page with a GET request
* In order to do a deletion, you still need to create a form that wraps around a single button (just because a form is the only way to send a POST request from the browser)

### Andy's Tips

* These are identical:
```javascript
const a = (foo) ? foo : default;
const a = foo || default;
```
* Call dynamic parameters in URLs for a CRUD app ":id". Don't need to do anything more specific, it makes it harder to read:
```javascript
app.get('/cheeses/:id') 
// NOT
app.get('/cheeses/:nameOfCheese')
```
* Remember, put your routes from most specific to least! Otherwise, you might accidentally "catch" a *new* route with a generic */:id* 
