#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
  * Complication process (Grunt, Gulp)
  * Hosting on a CDN (Optimise to get best number of active HTTP requests per domain)
* Can you describe the difference between progressive enhancement and graceful degradation?
  * Progressive Enhancement
    * Conforms to lowest common denominator amongst supported browsers. This way, the application is built upon a foundation that works across all supported platforms. However, when a browser that supports improvements visits the application, those improvements are dynamically added.
  * Graceful degradation 
    * Assumes that all users visiting the application are using the latest browser and support the latest features. However, when a user that does not support these features visits the website, the website gracefully removes the advanced features infavor for accepted features. 
* How would you optimize a website's assets/resources?
  * Image Spites
    * Used to smash a bunch of commonly used icons or assets into a single image. This image is then used in conjunction with [CSS](https://css-tricks.com/css-sprites/) (background-image, background-repeat, height and background-position)
  * Compress images
    * Compressing images can be part of your assets pipeline / build proceess. 
  * Browser Caching
    * Static resources such as CSS, PDFs, JS and HTML (when possible) utilise the HTTP header for caching. This is done through a expiry date and maximum age
  * GZIP
    * Most servers (nginx) have this turned on be default. However, it's always worth a check that all static resources are being GZIP'd
  * Ensure Parallel Requests
    * Difficult topic, but optimsing load order (load important stuff first, nice features next) is one way. 

* How many resources will a browser download from a given domain at a time?
  * Depending on the browser, anywhere between (IE6)2 - (IE10)8
  * What are the exceptions?
* Name 3 ways to decrease page load (perceived or actual load time).
  * Browser Caching
    * Use the HTTP headers to ensure appropriate cache times are set. 
  * Image Spites
    * Smaller resources and smarter CSS equals less resouces to load
  * GZIP
    * GZIPing static contents (can be setup via http-server) can decrease the size of the content sent over the wire. 
* If you jumped on a project and they used tabs and you used spaces, what would you do?
  * really?
* Describe how you would create a simple slideshow page.
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
  * Standards bodies 
    * do the work the rest of us can't do. They take seamingly trivial items (var, let) and discuss the semeantics, the impacts and implecations of implemeting something into a language. 
  * Standards
    * Standards exist in an effort to unify the way web development is done. However, such standards have netoriously not been followed by major browser vendors (Microsoft). Regardless of this, standards serve as a benchmark for each browser to follow, and as assuances for web developers.
* What is Flash of Unstyled Content? How do you avoid FOUC?
  * A FOUC is when uncompiled / unloaded  or otherwise 'not ready' content is shown to the user before it is ready. 
  * To midigate this, complication steps can be done before run time (handlebars, JSX) to increase performance 
  * spinners / loading spinners could be used inplace while content is being assembled. 
  * Alternitvly, content could be loaded in a 'progressive enhancement' type of way. Ensure that the most important content (text of a blog post) is made available instantly, and secondary content (ads, comments) are loaded in async. 
* Explain what ARIA and screenreaders are, and how to make a website accessible.
  * complex peices of software that read a html and interperite their markup so vision impared users can access web content. 
  * ARIA tags on html elements assist screen readers in creating additional content and intent for the existing html
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
  * JS animation
    * Fine grain control over speed, distance and how it's down
    * Performed on the CPU. The CPU isn't very good at graphical calculations
  * CSS Animation
    * Less control over the fine grained details, however you still have control over the easing and type of animation that is performed. 
    * Animation is performed on the GPU, which is much better at these types of calculations 
* What does CORS stand for and what issue does it address?
  * Cross Origin Resource Sharing
    * It addresses the issue of sharing content (static or otherwise) across domains (origins).
    * A REST API that sits at foo.com/api, and a website that sits at foo.com have the same origin (foo.com)
    * however a website that sits at bar.com has a different origin, and when a request from bar.com is made to foo.com/api it will receive a 'CORS' error, where the remote API does not accept request from differnet origins

#### HTML Questions:

* What does a `doctype` do?
* What's the difference between standards mode and quirks mode?
* What's the difference between HTML and XHTML?
  * HTML
    * Is less fussy and allows for incomplete tags
  * XHTML
    * More fussy and requires a extended doc type
* Are there any problems with serving pages as `application/xhtml+xml`?
* How do you serve a page with content in multiple languages?
* What kind of things must you be wary of when design or developing for multilingual sites?
* What are `data-` attributes good for?
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
* What is progressive rendering?
* Have you used different HTML templating languages before?

#### CSS Questions:

* What is the difference between classes and ID's in CSS?
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* Describe BFC(Block Formatting Context) and how it works.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for. 
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

* Explain event delegation
* Explain how `this` works in JavaScript
* Explain how prototypal inheritance works
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or `undeclared`?
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
* What's a typical use case for anonymous functions?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
* What's the difference between `.call` and `.apply`?
* Explain `Function.prototype.bind`.
* When would you use `document.write()`?
* What's the difference between feature detection, feature inference, and using the UA string?
* Explain AJAX in as much detail as possible.
* Explain how JSONP works (and how it's not really AJAX).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?
* Difference between document load event and document ready event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, `"buzz"` at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP actions? List all HTTP actions that you know, and explain them.

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).
