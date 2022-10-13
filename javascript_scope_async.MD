# JavaScript: Scope and Asynchronous JS

## Functions
1. 
```
function adder (x, y) {
  return x + y;
}
```
  - has `this` keyword and also `arguments` binding
2. 
```
const add = (x, y) => {
  return x + y;
}

// or
const add = (x, y) => x + y;
```

## Scope
- Global
- Local
- Block
- Lexical

### Global Scope
- variables/functions defined outside of a function

### Local Scope
- Variables/functions defined inside of a function

### Block Scope
- variables/functions defined inside of {} e.g. if (x) {...}

## Variable Declaration
1. var
  - Can be changed
2. let
  - Cannot be redeclared
3. const
  - Cannot be redeclared

### Lexical Scope
- Works like functions normally, i.e. anything defined inside of it is not accesible outside of it but global variables are accessible inside of the function

## `this`

### `this` in a method
- Refers to the owner of the method i.e. functions declared in an object can access other attributes of the object with this
- Arrow function does not have a `this` binding

### `this` alone
- Refers to the Global object, `[object window]`

### `this` in an arrow function
- Searches `this` upwards from its parent scope

## Asynchronous
- Allows multiple things to happen at the same time instead of waiting for an action to finish
- Different from the thread model

### Callbacks
- Functions that perform a slow action can contain an extra argument, a *callback function*
- When the slow action finishes, the callback is called with the result
- Weird

### Promises
- An object that may produce a single value some time in the future
- Has three states
  1. fulfilled
  2. Rejected
  3. Pending
- Can use the `.then` method to pass in two functions

e.g.
```
const wait = (time) => new Promise((resolve) => setTimeout(resolve, time));

const responsePromise = wait(3000); // this is a promise returned by the wait function
responsePromise.then(
  () => console.log('Hello!'),
  () => console.log('error')
); // 'Hello!'
```

## Fetch
- We can fetch data from another API

e.g.
```
fetch(some_random_url)
  .then((response) => response.json())
  .then((data) => console.log(data));
```