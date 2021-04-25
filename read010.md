# The Call Stack and Debugging

* A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc


* When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.

* The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous


* In Asynchronous JavaScript, we have a callback function, an event loop, and a task queue. The callback function is acted upon by the call stack during execution after the call back function has been pushed to the stack by the event loop

* At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).
  
```js
function greeting() {
   // [1] Some code here
   sayHi();
   // [2] Some code here
}
function sayHi() {
   return "Hi!";
}

// Invoke the `greeting` function
greeting();

// [3] Some code here
```
***The code above would be executed like this:***
1. Ignore all functions, until it reaches the greeting() function invocation.
2. Add the greeting() function to the call stack list.
 ```
Call stack list:
- greeting
````
3.Execute all lines of code inside the greeting() function.
4. Get to the sayHi() function invocation.
Add the sayHi() function to the call stack list.
```
Call stack list:
- sayHi
- greeting
```
4. Execute all lines of code inside the sayHi() function, until reaches its end.
5. Return execution to the line that invoked sayHi() and continue executing the rest of the greeting() function.
6. Delete the sayHi() function from our call stack list.
```
Call stack list:
- greeting
```
7. When everything inside the greeting() function has been executed, return to its invoking line to continue executing the rest of the JS code.
8. Delete the greeting() function from the call stack list.
```
Call stack list:
EMPTY
````

## JavaScript error messages && debugging

* Types of errors in JavaScript:
 1-Reference errors 

 > console.log(foo) // Uncaught ReferenceError: foo is not defined
 2-Syntax errors

 >JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o inJSON 

 3-Range errors

 ```
 var foo= []
foo.length = foo.length -1 // Uncaught RangeError: Invalid array length
```

 4-Type errors
 
 ```
 var foo = {}
foo.bar // undefined
foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined
```

> Best way to debug your code in javascript is to use console.log();
