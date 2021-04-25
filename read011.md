# EJS 

## EJS stands for Embedded JavasScript Templating

* EJS is a simple templaying language that lets you generate HTML markup with vanilla JavaScript.

* EJS is a template system. You define HTML pages in the EJS syntax and you specify where various data will go in the page. Then, your app combines data with the template and "renders" a complete HTML page where EJS takes your data and inserts it into the web page according to how you've defined the template. For example, you could have a table of dynamic data from a database and you want EJS to generate the table of data according to your display rules. It saves you from the drudgery of writing code to dynamically generate HTML based on data

* Important features for EJS: 1- Fast 2- Simple 3- Server JS and browser support

## Get Started

1. to install it
> npm install ejs
2. 
>npm install --save express body-parser cors ejs
3. To use it you need to pass an EJS template, first requiring the ejs database then adding the data.
4. Feed it a template file and a data file, and specify an output file.

>ejs ./template_file.ejs -f data_file.json -o ./output.html


5. creating `index.ejs`
```
<% if (user) { %>
  <h2><%= user.name %></h2>
<% } %>
```

it will take this if statement to to bring out result user.name to view it on the browser

* We can use arrays to inject inside the page.

* Add <% %> and then put for loop inside it, for < var person of people >{ and then put inside the thing that u want inside and close the bracket with another <% } %>

## Add the EJS Partials to Views
We have our partials defined now. All we have to do is include them in our views. Let’s go into `index.ejs` and `about.ejs` and use the `include syntax to add the partials`.

Syntax for including an EJS Partial
> Use <%- include('RELATIVE/PATH/TO/FILE') %> to embed an EJS partial in another file.

* The hyphen <%- instead of just <% to tell EJS to render raw HTML.
* The path to the partial is relative to the current file.