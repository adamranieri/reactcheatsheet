
## Component Terminology
- **Higher-Order component** - a component that takes a component and returns a new component
- **props** - inputs to a React component, should never be modified
- **props.childen** - contains the content between the opening and closing tags of a component
- **state** - data associated with a component that changes over time


- **Parent Component**
  - A component that returns other components
```jsx
// Home Page is the parent component
export function HomePage(){
    return <>
        <Navbar>
        <UserInfo/>
        <UpcomingEventsList/>
    </>
}
```
- **Child Component/Nested Component**
    - A Component returned by another component
```jsx
// Navbar UserInfo and UpcomingEventsList are all children components of HomePage
export function HomePage(){
    return <>
        <Navbar>
        <UserInfo/>
        <UpcomingEventsList/>
    </>
}
```
- **Sibling Components**
  - Components that are direct children of the same component
```jsx
// Navbar UserInfo and UpcomingEventsList are all sibling components of each other
export function HomePage(){
    return <>
        <Navbar/>
        <UserInfo/>
        <UpcomingEventsList/>
    </>
}
```
- **Container Component**
  - A component that *holds/contains* stateful values and has minimal or no UI

```jsx
//Task Manager is a a container component
export function TaskManager(){

    const [tasks,setTasks] = useState([])

    return <>
        <TaskList tasks={tasks}/>
        <TaskCreationForm setTasks={setTasks}/>
    </>
}
```
- **Presentation Component**
  - A Component that does not have its own state and is focused on presenting the UI

```jsx
//Task List is a presentation component
export function TaskList(props){

    return <ul>
        {props.tasks.map(t => <li key={t.id}> {t.name}</li>)}
    </ul>
}
```
- **Higher Order Component**
  - A component that takes in *another* component has an argument and **return** a new component
  - **Advanced Technique**
