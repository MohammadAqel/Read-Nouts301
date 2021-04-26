State and Lifecycle
Converting a Function to a Class:
You can convert a function component like Clock to a class in five steps:
1 - Create an ES6 class, with the same name, that extends React.Component.
2 - Add a single empty method to it called render().
3 - Move the body of the function into the render() method.
4 - Replace props with this.props in the render() body.
5 - Delete the remaining empty function declaration.
Adding Local State to a Class
1) Replace this.props.date with this.state.date in the render() method
2) Add a class constructor that assigns the initial this.state
3) Remove the date prop from the element
Adding Lifecycle Methods to a Class
In applications with many components, it’s very important to free up resources taken by the components when they are destroyed.
We want to set up a timer whenever the Clock is rendered to the DOM for the first time. This is called “mounting” in React.
We also want to clear that timer whenever the DOM produced by the Clock is removed. This is called “unmounting” in React.
Handling Events
Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences:
React events are named using camelCase, rather than lowercase. With JSX you pass a function as the event handler, rather than a string
When using React, you generally don’t need to call addEventListener to add listeners to a DOM element after it is created. Instead, just provide a listener when the element is initially rendered. When you define a component using an ES6 class, a common pattern is for an event handler to be a method on the class. For example, this Toggle component renders a button that lets the user toggle between “ON” and “OFF” states.

