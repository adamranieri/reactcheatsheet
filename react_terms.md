## React
1. **React** - a front-end JavaScript library for building user interfaces based on components
1. **One Way Data Flow** - data flows in one direction in React, such as from parent component to child component
3. **Single-Page Application** - an application that loads a single page and all the necessary assets (JS and CSS) required for it to run
    - Interactions with the page do not require another trip to the server
1. **ES6** - ECMAScript Language Specification standard version 6, introducing arrow functions, classes, template literals, let and const, etc.
    - JS is an implementation of this standard
1. **JSX** - a syntax extension to JavaScript. It is similar to a template lanuage but has access to JS
    - JSX is compiled to plain JS objects called "React elements"
1. **Elements** - the building blocks of React applications, what you want to see on the screen
    - Typically returned from components
1. **Components** - small, reusable pieces of code that return a React element to be rendered on the page
    - Can be functions or ES6 classes
2. **Virtual DOM**
   1. A mirror version of the DOM that is stored in JS as 100% JS objects
   2. React does all operations on the virtual DOM and then updates the real DOM selectively as an optimization.

3. **key** - a string attribute included when creating an array of elements
    - should give each element in the array a stable identity
4.  **Routing** - the process of redirecting a user to different pages based on a request/action
5.  Hook - introduced in React 16.8, lets you use state and other features without writing a class
6.  **Side Effect**- an action that is performed with something outside of React such as an API request
    - Unpredictable
    - Other examples: interact with browser APIs or using timing functions like setTimeout or setInterval
7.  useReducer hook - lets us add a reducer to our component
    - Takes in a reducer function and initial state as arguments
    - Returns the current state and a dispatch function
8.  Reducer - a function that specifies how our state is updated
    - should take the state and action as arguments and return the new state
## Redux
1. Redux -
2. Stores - Manages the state of the application through methods
3. Dispatchers - a single object that broadcasts actions to the store
4.  Views - the user interface component
    - listens for store changes and re-renders
5.  Action - a plain object that contains all the information required to perform the action
    - Have a type property and sometimes a payload
6. Action Creator - a function that creates and dispatches actions


