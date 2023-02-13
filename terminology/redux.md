# Redux
- a JS library for managing centralized application state
- **Flux**
  -   an architectural pattern that splits an app into 3 or 4 parts: (Store, Dispatcher, View, Action)
![Flux](https://static.javatpoint.com/tutorial/reactjs/images/react-flux-concept.png)
- **Stores** - Manages the state of the application through methods
- **Dispatchers** - a single object that broadcasts actions to the store
- **View** - the user interface component
    - listens for store changes and re-renders
- **Action** - a plain object that contains all the information required to perform the action
    - Have a type property and sometimes a payload
- **Action Creator** - a function that creates and dispatches actions

## Redux Saga
- **Redux middleware**
  - It is designed to integrate into Redux not be a standalone library
  - primary reason is to work with asynchronous code
- **generator function**
  - A function that will **yield** mutiple values as opposed to return a single value
-  **Worker Saga** - generator function that takes an action, processes it, and typically sends another action to the actual reducer
-  **Watcher Saga** - generator function that intercepts actions and triggers the corresponding worker function
-  **Root Saga** - a generator function that contains all the watcher sagas you've created
-  **Effect**
   -  An object that will be processed by Saga
   -  Methods that generate effect objects
      -  put()
      -  call()