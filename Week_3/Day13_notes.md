## Day 13 - 30 Sep 2020

### Definitions

* A server is *stateless* if it doesn't store info about previous request and responses from the same user
* Cookies give servers *state*

### Cookies

* Cookies are chunks of data about a user that are saved in a browser
* Third-party cookies can allow you to be tracked between sites
* May cause security issues. Not going to cover those now, but remember that for the future
* Every HTTP request includes all the cookies for that domain name saved on the browser

* Use *res.status(num)* to send back an HTTP response status
* *res.status(num).json(message)* sends back an HTTP response status along with an actual JSON message
* You should only have a single instance of an Express app across all your files in a project, so you only need to put 
things like *app.use(cookie-parser)* once.
* Normally, you would store most of the info on the server side in a database, and just store a small piece of data (usually the unique
ID of the server data that corresponds to a user) in a user's browser as a cookie
* Typically, you would *never* store cookies in unecrypted form, unless it's something that's completely not sensitive (like
a client's language purposes)

### Server-Side Session Storage

* In some cases, it may be better to store a client's data on the server side, and just store a key on the client's side in a cookie that maps
to the data on the server side
* This way, you get around client-side size restrictions (if you have to save **a lot** of data for this client)




