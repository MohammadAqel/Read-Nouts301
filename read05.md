# Heroku
at the first we need to creat account on heroku so we created one to deploy the app 


* Node.js is an open source, cross-platform runtime environment, which allows you to build server-side and networking applications. It's written in JavaScript and can be run within the Node.js runtime on any platform

* Heroku is a cloud platform as a service  It allows you to deploy our web server

1. create javascript file 
2. tested it by ` node server.js`in your terminal

* to deploy our web server 
3. in terminal `heroku login`
*  the creation. It will be a simple blog with basic functionality. It will show you requested web pages and the error page in case of an error

4. declare this var
```
var http = require("http");
var fs = require("fs");
var path = require("path");
var mime = require("mime");
```

* The first one will give you the key to Node's HTTP functionality. The second one is for possibility to interact with the file system. The third one allows you to handle file paths. The last one allows you to determine a file's MIME-type. And it's not a part of Node.js, so we need to install third-party dependencies before using it. We need to create the package.json file for that purpose. It will contain project related information, such as name, version, description, and so on. For our project we will use MIME-types recognition, because it's not enough to just send the contents of a file when you use HTTP. You also need to set the Content-Type header with proper MIME-type. That's why we need this plug-in

* then follow steps of functionality then open your Heroku project in your web browser and share it with the world by this step 

 >*git push heroku master*

 >*heroku ps:scale web=1* to  Ensure that at least one instance of the app is running

 >*heroku open*  to open the url