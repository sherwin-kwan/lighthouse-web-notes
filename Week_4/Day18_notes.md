## Day 18 - 7 Oct 2020

### AJAX

* Uses DOM manipulation to change the content on a webpage without having to refresh
* Can be very convenient for searches that get info out of a database (say, a Pokedex)
* syntax is $().ajax(url, { method: GET/POST}) - returns a promise which resolves if it's successfully found 


### AJAX - Advantages

* Doesn't need a refresh of the whole page just to get some extra data
* Only loads what you need - allows for "infinite scrolling" where only 10 items load at a time
* Much "snappier" and more convenient from the client's perspective

### AJAX - Disadvantages

* The URL doesn't change when you get new data, so there's no way of copying the link and sending it to someone else
* Asynchronous requests do not log to the browser's history
* This also means that you cannot use "Back" button on your browser to see the last-viewed data (Note: There is a way to code around this by changing the history object on the browser)
* Screen readers don't play nicely with AJAX
* AJAX may be a security risk

### CORS

* Cross Origin Resource Sharing: it's when there is a third-party server that you have to request data from in order to load a page from the original server
* Browsers have security features that limit what data you can send or receive from a cross-origin server (a different server than the one you were originally connected to and seeking)

### Travis's Tips

* Use ```<script defer src="...">``` - this means the script will download asynchronously while the page is loading, but does not run until after the HTML is finished loading (the fastest way to get a page to load, usually)
  * Alternatives are ```<script async >``` or just moving the script tag to the end of the body, however these methods are still not as ideal
* For jQuery - I would use the uncompressed version while learning/in development so we can see what it does, but minified (the unreadable compressed version) is going to be faster for production use
* Use the "XHR" tab in the Network section of developer tools, to see Ajax requests
* PokeAPI for all your Pokemon needs!