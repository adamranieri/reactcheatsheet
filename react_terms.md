## React
1. React - a front-end JavaScript library for building user interfaces based on components
1. One Way Data Flow - data flows in one direction in React, such as from parent component to child component
1. Single-Page Application - an application that loads a single page and all the necessary assets (JS and CSS) required for it to run
    - Interactions with the page do not require another trip to the server
1. ES6 - ECMAScript Language Specification standard version 6, introducing arrow functions, classes, template literals, let and const, etc.
    - JS is an implementation of this standard
1. JSX - a syntax extension to JavaScript. It is similar to a template lanuage but has access to JS
    - JSX is compiled to plain JS objects called "React elements"
1. Elements - the building blocks of React applications, what you want to see on the screen
    - Typically returned from components
1. Components - small, reusable pieces of code that return a React element to be rendered on the page
    - Can be functions or ES6 classes
1. Nested Component - any child component linked to a parent component
1. Higher-Order component - a component that takes a component and returns a new component
1. props - inputs to a React component, should never be modified
1. props.childen - contains the content between the opening and closing tags of a component
1. state - data associated with a component that changes over time
1. context - allows for sharing data between components
1. key - a string attribute included when creating an array of elements
    - should give each element in the array a stable identity
1. ref - provide a way to access DOM nodes
1. Routing - the process of redirecting a user to different pages based on a request/action
1. Hook - introduced in React 16.8, lets you use state and other features without writing a class
1. useState hook - lets us keep track of a stateful value in a React component
    - Initialize it by giving the initial state, returns the current state and a function to update it
1. useEffect hook - lets you perform side effects in function components
    - Pass in a function and an optional dependencies array
1. Side Effect - an action that is performed with something outside of React such as an API request
    - Unpredictable
    - Other examples: interact with browser APIs or using timing functions like setTimeout or setInterval
1. useReducer hook - lets us add a reducer to our component
    - Takes in a reducer function and initial state as arguments
    - Returns the current state and a dispatch function
1. Reducer - a function that specifies how our state is updated
    - should take the state and action as arguments and return the new state
## Redux
1. Redux - a JS library for managing centralized application state
1. Flux - an architectural pattern that splits an app into 3 or 4 parts: (Store, Dispatcher, View, Action)
1. Stores - Manages the state of the application through methods
1. Dispatchers - a single object that broadcasts actions to the store
1.  Views - the user interface component
    - listens for store changes and re-renders
1.  Action - a plain object that contains all the information required to perform the action
    - Have a type property and sometimes a payload
1. Action Creator - a function that creates and dispatches actions
1. Redux Saga - a middleware library that allows us to intercept actions
    - primary reason is to work with asynchronous code
1. Worker Saga - takes an action, process it, and typically send another action to the actual reducer
1. Watcher Saga - intercepts actions and trigger the corresponding worker function
1. Root Saga - a generator function that contains all the watcher sagas you've created
