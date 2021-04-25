# functional programming

* Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

* pure functions :It returns the same result if given the same arguments,and It does not cause any observable side effects


* when my function will be impure  which is a function that uses a global object that was not passed as a parameter

1. Reading Files :If our function reads external files, it’s not a pure function


```js
const charactersCounter = (text) => `Character count: ${text.length}`;

function analyzeFile(filename) {
  let fileContent = open(filename);
  return charactersCounter(fileContent);
}
```
2. Random number generation



* Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen

* Basically, if a function consistently yields the same result for the same input, it is referentially transparent

> pure functions + immutable data = referential transparency

* Higher order functions are functions that take multiple arguments or return a function as its result

# Refactoring JavaScript to be more Readability

* Like giving spaces between every block of code to make it more tidy.

* write one function that accepts a list of friendly things

* separated some logic and reduced the number of lines of code

* Using understandable variable names

*  adding comments so we can know this for what or what doing 

**Scenario 1**

We're an URL-shortening website, like TinyURL. We accept a long URL and return a short URL that forwards visitors to the long URL. We have two functions.

**cenario 2**

We're a social media website where user URLs are generated randomly. Instead of random gibberish, we're going to use the friendly-words package that the Glitch team works on. They use this to generate the random names for your recently created projects!