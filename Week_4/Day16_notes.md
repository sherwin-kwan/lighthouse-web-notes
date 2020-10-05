## Day 16 - 5 Oct 2020

### Introduction to Front End

* HTML (Hypertext Markup Language) forms the *content* of a webpage, and CSS (Cascading Style Sheets) forms the *styles* and *layout*. In other words, the meaning of the page is stored in HTML, and how it's presented and looks is decided by CSS.
* *Semantic* HTML tags like \<article>, \<layout>, etc. are used to help automated systems determine what a page means. This includes:
  * Search engines, their algorithms often use these to determine what the meaning or subject of a page is
  * Accessibility programs, which often have custom styles that replace the styles of your page, that help e.g. visually impaired people view pages in a way they can understand
* It is not best practices to use generic tags like \<div> everywhere.

### CSS

* CSS is *cascading* because it has a system where styles for more specific pieces of content override styles defined less specifically
* HTML uses the *box model*, content is laid out in boxes which have *content* surrounded by *padding*, *border*, and *margin*
* These CSS properties can be set for all four directions at once (*padding: 50px*), or for the four directions separately (*padding: 40px 30px 20px 10px*). When four numbers are provided in this way, they are for top, right, bottom, and left respectively. A useful mnemonic is the word TRouBLe
* In the box model, there is a property called *box-sizing* which is very important. If it is set to *content-box* (or not set, which is the same thing since *box-sizing: content-box* is default in most browsers), it only includes the content itself.
  * So setting width: 100px, height: 100px with a 20px padding and 10px border will create a 160x160 box
  * However, if *box-sizing: border-box* is set, then the entire border falls within 100x100, so the actual content only has 40x40 room
* Depending on the browser or custom settings that a person sets, "default" CSS can be very different. So there are a few tools that people use to ensure that your webpage looks the same in any browser:
  * *Normalize.css* is a common tool that provides "standard" CSS settings
  * *Reset.css* is another common tool that eliminates all styling (padding = 0, border = 0, etc.) so you can write code on a blank slate
  * Then there are other tools like *Bootstrap* that provide a number of default style rules

### CSS Selectors

* If multiple CSS selectors match a particular HTML element, the one with the highest specficity is used:
  * ID selectors
  * Class, attribute, and pseudo-class selectors
  * Type selectors
* If two selectors have the same specificity, the one that comes later in the CSS file is used.
* If two selectors in separate CSS files have the same specificity, the one in the file that is imported into the HTML file later is used.

### CSS Inheritance

* Some CSS properties are inherited, which means that if no value is specified for a particular HTML element, but a value *is* specified for a *parent* element, the parent element's setting will be used. Color is inherited, for example:

```html
<p style="color:green">This text is <em>green</em></p>
```
* The entire thing, including the bold part, will be green.
* However, border styles are not inherited. So if you have an element inside another element, giving the parent element in border doesn't give the child element a border! (otherwise that would be *really* inconvenient) In this case, if no style is set for an element, then the default style remains.

### CSS Flexbox

* A useful tool for modern CSS, enabled by setting *display: flex*
* Then you can do things like *justify-content: space-evenly*
* Note: *display: flex* doesn't inherit, you have to put it on every element selector where you want to use a flexbox property!
* *flex-grow* is a useful property in flexbox that does a similar thing as *width*


