## Day 11 - Web Servers

### Hafiz Suara's Rules

* Don't just use chat, I prefer raising-hands & speaking up

### HTTP

* Client-server protocol 
* Transfers "hypertext" (text with links & media) or JSON (so basically, strings)
* HTTP is client-initiated. Servers will only send data when client requests it
* To every client request, there is at most one server response
* To make a request, you need to submit:
  * An address (URL)
  * A method (GET, POST, PUT, DELETE)
  * A body
* *Route* or *endpoint*: a term for the combination of an address + a method

### Response

* Comes with a status code. Examples:
  * 1xx: Sends info messages 
  * 2xx: Successful (for example, 200 OK)
  * 3xx: Not here, look over there (often indicate redirects)
  * 4xx: "You can't do that" (for example, 403 Forbidden or 404 Not Found)
  * 5xx: Server error (some dev made a booboo)

### A Store Metaphor

Physical Store | Web Server
---|---
Create a store | Create a server
Open shop for business | Begin listening on a port
Hire clerk to serve customers | Create a function that handles requests and sends a response back

### The Server

* When a server receives a request, it looks for a matching route (an instruction saying *if a GET request is received at /fff, do this*)
* If no matching route is found, the server will hang (the client is waiting for a response that never arrives)
* To avoid this issue, we need to create a not-found handler which sends back a 404 code
* Express.js (and other server software) will automatically do these kinds of things for us so we don't need to manually handle them all

### Using Express

* In an Express application, if a request is received, it will look for a matching route
* syntax: *app.get(relative path, callback)*
* the callback can be *res.render* (look for a template in the views folder and sent that) or *res.send* (just directly sending a string to the client)
* Common templating engines include: EJS, Pug. These ones use JS on the back end to generate an HTML string dynamically and send it over to the client
* Not to be confused with front-end frameworks like Angular or React, these ones actually run client-side code
* Probably, EJS and React are the most common/valuable ones to learn
