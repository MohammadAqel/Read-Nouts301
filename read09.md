Concepts of Functional Programming in Javascript

What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia

The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?
So how do we know if a function is pure or not? Here is a very strict definition of purity:
It returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects
It returns the same result if given the same arguments
Imagine we want to implement a function that calculates the area of a circle. An impure function would receive radius as the parameter, and then calculate radius * radius * PI:

Why is this an impure function? Simply because it uses a global object that was not passed as a parameter to the function.
Now imagine some mathematicians argue that the PI value is actually 42and change the value of the global object.
Our impure function will now result in 10 * 10 * 42 = 4200. For the same parameter (radius = 10), we have a different result. Let's fix it!

TA-DA 🎉! Now we’ll always pass thePI value as a parameter to the function. So now we are just accessing parameters passed to the function. No external object.
For the parameters radius = 10 & PI = 3.14, we will always have the same the result: 314.0
For the parameters radius = 10 & PI = 42, we will always have the same the result: 4200
Reading Files
If our function reads external files, it’s not a pure function — the file’s contents can change.

Random number generation
Any function that relies on a random number generator cannot be pure.

It does not cause any observable side effects
Examples of observable side effects include modifying a global object or a parameter passed by reference.
Now we want to implement a function to receive an integer value and return the value increased by 1.

We have the counter value. Our impure function receives that value and re-assigns the counter with the value increased by 1.
Observation: mutability is discouraged in functional programming.
We are modifying the global object. But how would we make it pure? Just return the value increased by 1. Simple as that.

See that our pure function increaseCounter returns 2, but the counter value is still the same. The function returns the incremented value without altering the value of the variable.
If we follow these two simple rules, it gets easier to understand our programs. Now every function is isolated and unable to impact other parts of our system.
Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.
Pure functions benefits
The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:
Given a parameter A → expect the function to return value B
Given a parameter C → expect the function to return value D
A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.

We receive the numbers array, use map incrementing each number, and return a new list of incremented numbers.

For the input [1, 2, 3, 4, 5], the expected output would be [2, 3, 4, 5, 6].

Higher-order functions
When we talk about higher-order functions, we mean a function that either:
takes one or more functions as arguments, or
returns a function as its result
The doubleOperator function we implemented above is a higher-order function because it takes an operator function as an argument and uses it.
You’ve probably already heard about filter, map, and reduce. Let's take a look at these.
Filter
Given a collection, we want to filter by an attribute. The filter function expects a true or false value to determine if the element should or should not be included in the result collection. Basically, if the callback expression is true, the filter function will include the element in the result collection. Otherwise, it will not.
A simple example is when we have a collection of integers and we want only the even numbers.
Imperative approach
An imperative way to do it with Javascript is to:
create an empty array evenNumbers
iterate over the numbers array
push the even numbers to the evenNumbers array

We can also use the filter higher order function to receive the even function, and return a list of even numbers:

One interesting problem I solved on Hacker Rank FP Path was the Filter Array problem. The problem idea is to filter a given array of integers and output only those values that are less than a specified value X.
An imperative Javascript solution to this problem is something like:

We say exactly what our function needs to do — iterate over the collection, compare the collection current item with x, and push this element to the resultArray if it pass the condition.
Declarative approach
But we want a more declarative way to solve this problem, and using the filter higher order function as well.
A declarative Javascript solution would be something like this:

Using this in the smaller function seems a bit strange in the first place, but is easy to understand.
this will be the second parameter in the filter function. In this case, 3 (the x) is represented by this. That's it.
We can also do this with maps. Imagine we have a map of people with their name and age.

And we want to filter only people over a specified value of age, in this example people who are more than 21 years old.

Summary of code:
we have a list of people (with name and age).
we have a function olderThan21. In this case, for each person in people array, we want to access the age and see if it is older than 21.
we filter all people based on this function.
Map
The idea of map is to transform a collection.
The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.
Let’s get the same people collection above. We don't want to filter by “over age” now. We just want a list of strings, something like TK is 26 years old. So the final string might be :name is :age years old where :name and :age are attributes from each element in the people collection.
In a imperative Javascript way, it would be:

In a declarative Javascript way, it would be:

The whole idea is to transform a given array into a new array.
Another interesting Hacker Rank problem was the update list problem. We just want to update the values of a given array with their absolute values.
For example, the input [1, 2, 3, -4, 5]needs the output to be [1, 2, 3, 4, 5]. The absolute value of -4 is 4.
A simple solution would be an in-place update for each collection value.

We use the Math.abs function to transform the value into its absolute value, and do the in-place update.
This is not a functional way to implement this solution.
First, we learned about immutability. We know how immutability is important to make our functions more consistent and predictable. The idea is to build a new collection with all absolute values.
Second, why not use map here to "transform" all data?
My first idea was to test the Math.abs function to handle only one value.

We want to transform each value into a positive value (the absolute value).
Now that we know how to do absolute for one value, we can use this function to pass as an argument to the map function. Do you remember that a higher order function can receive a function as an argument and use it? Yes, map can do it!

Wow. So beautiful! 😍
Reduce
The idea of reduce is to receive a function and a collection, and return a value created by combining the items.
A common example people talk about is to get the total amount of an order. Imagine you were at a shopping website. You’ve added Product 1, Product 2, Product 3, and Product 4 to your shopping cart (order). Now we want to calculate the total amount of the shopping cart.
In imperative way, we would iterate the order list and sum each product amount to the total amount.

Using reduce, we can build a function to handle the amount sum and pass it as an argument to the reduce function.

Here we have shoppingCart, the function sumAmount that receives the current currentTotalAmount , and the order object to sum them.
The getTotalAmount function is used to reduce the shoppingCart by using the sumAmount and starting from 0.