# Common patterns or tips for cleaner React Code

## JS Syntax
- Not specific to React but helpful and commonly used in React

### Array Destructuring
```JavaScript
const people = ["Adam", "Mike","Steve", "Aaron"];

const [adam,mike] = people;
// Equivalent to
const adam = people[0];
const mike = poeple[1];

```
<details>
<summary>React Use Case</summary>

```JSX
import { useState } from "react"

export default function Counter(){

    const [value,setValue] = useState();

    function increment(){
        setValue(value + 1)
    }

    return(<>
        <h3>The value is : {value}</h3>
        <button onClick={increment} >add</button>
    </>)
}
```
</details>
<hr/>


### Object Destructuring
```JavaScript
const user = {username:"adamGator", fname:"Adam", lname:"Ranieri"};

const {fname, lname} = user;
// Equivalent to 
const fname = user.fname;
const lname = user.lname;
```

<details>
<summary>React Use Case</summary>

```JSX
export default function EmployeeDataRow(props){

    const {name, department, salary} = props;

    return(<tr>
            <td>{name}</td>
            <td>{department}</td>
            <td>{salary}</td>
        </tr>)
}
```
</details>
<hr/>

### Spread Operator
```JavaScript
const nums = [10,20,30,40,50];
console.log(nums); // [10,20,30,40,50]

const clonedNums = [...nums, 60]; // this is a new array
console.log(clonedNums); // [10,20,30,40,50,60]


const bankAccount = {id:101, owner: "Bob Smith", amount:2000}
console.log(bankAccount) // {id:101, owner: "Bob Smith", amount:2000}

const clonedAcccount = {...bankAccount, amount: 1500} // this is a new object
console.log(clonedAcccount) // {id:101, owner: "Bob Smith", amount:1500}
```

<details>
    <summary>React Use Case</summary>

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

```JSX

function App() {
  const bill = {fname:"Bill", department:"Marketing", salary:90000}
  return (<>
      <EmployeeInfo fname="Adam" department="Training" salary={400000} />
      <EmployeeInfo {...bill}/> 
    </>);
}

```

</details>
</hr>

### ES6 Modules and Importing

```JavaScript
// math.js
export class Triangle{
    ...
}

export function add(){
    ...
}

export const pi = 3.14;


// dtos.js
export default class Person{
    ...
}
// a file can have one default export. 
// It has no benfit other than cleaner import syntax

// utils.js
export function getConnection(){
    ...
}

export function verifyUser(){
    ...
}


// index.js
import {Triangle, add, pi} from "math.js" // this is an object destructing
import Person from "dtos.js"
import * as util from "utils.js"

util.getConnection();
util.verifyUser();
add()
const adam = new Person()

```
</hr>

### Guards
```JavaScript
console.log(4<5 && "Hello"); // Hello
console.log(10<4 && "Hola"); // false
```
<details>
<summary>React Use Case</summary>

```JSX
function App() {
  const num = Math.random()

  return (<>
      {num <0.1 && <h1>The number was less than 0.1</h1>}
      {num <0.5 && <h1>The number was less than 0.5</h1>}
      {num <0.9 && <h1>The number was less than 0.9</h1>}

    </>);
}
```

</details>

</hr>

### JS DOC

```JavaScript
/** @param {string} message  @param {number} times @returns {string}*/
function multiConact(message, times){
    return message.repeat(10);
}
// appropriate intellisense will be provided
```
<details>
<summary>React Use Case</summary>

```JavaScript

/** @param {{fname:string, salary:number, department:string }} props */
export default function EmployeeInfo(props){

    const {fname, salary, department} = props;

    return(<>
        <h5>First Name : {fname}</h5>
        <h5>Salary : {salary}</h5>
        <h5>Department: {department}</h5>
    </>)
}

<EmployeeInfo fname="Adam" department="Training" salary={400000}/>

```
</details>

</hr>
