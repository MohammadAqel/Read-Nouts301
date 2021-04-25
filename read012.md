# EJS PARTIALS

* Partials it's a layout  come in handy when you want to reuse the same HTML across multiple views


* it is as functions, they make large websites easier to maintain as you don’t have to go and change a piece of text in every page it appears in. Instead, you define that reusable bundle of code in a file and include it wherever you need it.

* we creat folders `views` then `partials`folder then the files

* You can use the same partials in different page using include function and then add it wherever you need it to be added to.

* We can use that for repititive elements such as header and footer

* And its that simple how we can easily add chunks of reusable elements using EJS,express and NodeJS!
  
  Note: The <%- %> tags allow us to output the unescaped content onto the page (notice the -). This is important when using the include() statement since you don’t want EJS to escape your HTML characters like ‘<’, ‘>’, etc…
Let’s create the homepage template in views/home.ejs and include the navbar and footer partial we just created:

``` html
<!-- views/home.ejs -->
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Node.js Blog</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
        <style>
            body {
                padding-top: 20px;
                padding-bottom: 20px;
            }
            .jumbotron {
              margin-top: 10px;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <%- include('partials/navbar') %>
            <div class="jumbotron">
                <h1>All about Node</h1>
                <p class="lead">Check out our articles below!</p>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <div class="list-group">
                      <!-- loop over blog posts and render them -->
                      LIST_OF_POSTS
                    </div>
                </div>
            </div>
            <%- include('partials/footer') %>
        </div>
    </body>
    </html>
    `````