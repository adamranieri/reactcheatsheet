# Hooks
- Hooks are the primary way of adding functionality to your ***Functional Components***

## useState
- Encapsulate a ***stateful value*** within an instance of the component
- Only useful for values that must be re-rendered over the life of a component
- NEVER edit or mutate a stateful value, it must be completely replaced in the setter function


```jsx
import { useState } from "react"

export default function Counter(){

    // [stateful-value (read-only), function that calls a re-render using the new value]
    const [num,setNum] = useState(0); // default value

    function addToNum(){
        const newValue = num + 1;
        setNum(newValue)// replace the old value with a new value
        
    }

    return(<>
        <h3>Counter Value {num} </h3>
        <button onClick={addToNum}>Add one to num</button>
    </>)
}



```

```JSX
import {useState} from 'react';

export default function RandomNumberList(){

    const [nums,setNums] = useState([]);
    const numItems = nums.map(t => <li>{t}</li>)

    function addRandom(){
        const randomNumber = Math.random();
        setNums([...nums, randomNumber]); 
    }
    

    return(<>
        <button onClick = {addRandom} >add random number</button>
        <ul>
            {numItems}
        </ul>
    </>)

}
```

```JSX
import {useState} from 'react';

export default function TaskTracker(){

    const [task,setTask] = useState({name:"laundry", status:"pending"});

    function markComplete(){
        setTask({...task, status:"Complete"})
    }

    return(<>
        <h3> Task to do: {task.name} </h3>
        <h3> Status : {task.status} </h3>

        <button onClick = {markComplete}>Mark Complete </button>
    </>)
}
```

</hr>

## useRef
- Creates a mutable object that ***references*** a DOM element.
- DOES NOT trigger re-render.
- Useful for getting information from inputs.
```JSX
import {useRef} from 'react'

function App() {
  
  const nameInput = useRef(null);

  function hello(){
      alert(`Hello ${nameInput.current.value}`)
  }

  return (<>

      <input ref={nameInput}/>
      <button onClick={hello}>Say Hello</button>

    </>);
}
```

## useEffect

- Connect into the parts of the component lifecycle
- code that exexutes with a ***side effect***
    - Code that interacts outside of react
        - Calling an API
        - interacting directly with the dom
- Useful for async functions when intializing component first time.

```JSX
import {useEffect} from 'react'

function App() {

  const [num1,setNum1] = useState(0);
  const [num2, setNum2] = useState(0);

  function addNum1(){
    setNum1(num1 + 1)
  }

  function addNum2(){
    setNum2(num2 + 1)
  }

  useEffect(() => console.log("Execute once on Mouting"), [])

  useEffect(() =>{
    return ()=> console.log('excute once on Unmounting')
  },[])

  useEffect(() => console.log('Executes every render'))

  useEffect(() => console.log("num1 was updated"), [num1])

  useEffect(()=> console.log("num2 was updated"), [num2])
  
  return (<>
    <h3>Number 1 is: {num1}</h3>
    <button onClick={addNum1}>add</button>

    <h3>Number 2 is: {num2}</h3>
    <button onClick={addNum2}>add</button>

    </>);
}

```

```JSX

function App() {

  const [pokemon,setPokemon] = useState();

  useEffect(()=>{

     async function getThatPokemon()  {
        const response = await fetch('https://pokeapi.co/api/v2/pokemon/ditto')
        const pokemon = await response.json()
        setPokemon(pokemon)
    }

    getThatPokemon()

  },[]);

 
  return (<>
      {pokemon ? <h3>name {pokemon.name}</h3> : <h3>Loading</h3> }
    </>);
}

```

## useContext
- A dependency injector for components
- allows you to avoid passing in props for nested components

```JSX

import { createContext, useContext, useEffect, useRef, useState } from 'react';


const guestContext = createContext()

function App() {

  const guestInfo = {username:"adamGator", fname: "Adam"};

  return (<>
  <guestContext.Provider value={guestInfo}>
    <UserInfo/>
  </guestContext.Provider>
      
    </>);
}


function UserInfo(){

  const guest = useContext(guestContext)

  return(<>
  <h3> logged in as: {guest.username}</h3>
  <h4> Welcome {guest.fname}</h4>
  </>)
}
```
