## Day 19 - 8 Oct 2020

### Responsive Design

* Use @media queries in CSS to set different styles for different devices and viewports
* It is nowadays common to do "mobile first" design - first make it look good on mobile, and then modify for desktop
* A mobile-default site with extra stylesheets for desktop is better because desktops usually are on faster Internet connections and can load more files quicker


### Hafiz's Tips

* Avoid setting absolute widths for anything, not good for responsive design
* Use relative units like *rem*, *vw*, *vh* liberally
* Note: *rem* stands for *root em*, it's relative to the font size of the root element (usually *html* or *body*)
* To test whether you did responsive design properly, slowly expand and contract your viewport in order to see whether things look good at all sizes

### SASS

* *Syntactically Awesome Style Sheets*: an extended version of CSS
* allows variables to be initialized and defined (so, for example, we can set 10 different classes to a brand colour)
* can place a selector within another selector to select a nested element (for example, ul { .... li { ... }}); everything inside the inner selector will be equivalent to writing ul li { ...} in CSS
* Must be compiled into CSS, browsers don't natively understand it
