 # jQuery

* jQuery is a JS file that lets you find elements using css-style selectors and then apply something using it's methods, which jQuery has a simple way: select elements, perform tasks and handle events.
* the jQuery selectors start with `$` and `()`
* when ever select any element we can apply method to it.
> $('li.hot').addClass('complete');

* There are several ways to start using jQuery on your web site and reference it with the HTML `<script>` tag which should be inside the `<head>` section
1. Download the jQuery library from jQuery.com
```js
<head>
<script src="jquery-3.5.1.min.js"></script>
</head>
```
2. Include jQuery from a CDN
```html
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
</head>
```
* we use jQuery because it make cods simpler and it's allows you to achieve
the same goals but in fewer lines of code

*  when we getting and setting data we have to store it into variable like
> $listItem= $('li')

* when a selector returns multiple elements,we can update all of them using the one method. There is no need to use a loop. which it known as **implicit iteration** and If we want to use more than one jQuery method on the same selection of elements, you can list several methods at a time using dot notation to separate each one.
> $( 'l i [i d!="one"] ') . hide() .delay(SOO) . fadeln(1400);

* we must use the ready function for jquery to check that the page is ready for the code and instead of `$(document).ready()` we can use shortcut for ready `$(function) (){//script goes here })`;

## Getting And Setting Attribute Values
1. .attr() for getting the value of an attribute 
2. .removeAttr() for removing any attr of an element
3. .html() to get the content of the selected element
4. .text() if we need only the test content without html markup 
5. .html() and .text() can be used to change the content of HTML element
6. .before(),.after() to add new element to page
7. .addClass() add one or more classes
8.  .css() get and set CSS properties
9.  .each() to loop through multiple element selections and $(this) to access the current element
10. .on() apply event methods.


# Pair Programming Reasons

pair programming is a strategy when two developers are working together on a project which they called ( driver and navigator)  the driver is the programmer who types, while the navigator guides the driver and thinks about the big picture

### pair programming helps in
1.**efficiency** when two people working on the problem can come with solutions faster than one person.

2.**focusing** it will extremely better than one 

3.engaging more experience

4.improves your social skills 

5.Job, interview and work environment readiness