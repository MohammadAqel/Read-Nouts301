# Sending form data

* An HTML form on a web page is nothing more than a convenient user-friendly way to configure an HTTP request to send data to a server. This enables the user to provide information to be delivered in the HTTP request

* The <form> element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are action and method

* data is sent to an absolute URL
```
 <form action="https://example.com">
```
* use a relative URL — the data is sent to a different URL on the same origin:
 ```
 <form action="/somewhere_else">
```

* The `action` value should be a file on the server that can handle the incoming data

* The `method `attribute defines how data is sent. The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods, the most common being the `GET` method and the `POST` method

* The `GET method` is the method used by the browser to ask the server to send back a given resource
  ```html
  <form action="http://www.foo.com" method="GET">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>

* The `POST method` is a little different. It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request


* If you want to send files, you need to take three extra steps:

1. Set the method attribute to `POST` because file content can't be put inside URL parameters.

2. Set the value of `enctype` to *multipart/form-data* because the data will be split into multiple parts, one for each file plus one for the text data included in the form body (if text is also entered into the form).