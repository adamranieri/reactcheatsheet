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
