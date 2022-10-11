# JavaScript: DOM

## DOM
- Document Object Model

## document
- globally available variable

e.g.
- `const x = document.querySelector('.class');`

### Change CSS with camel case
- x.style.<CSS here>

e.g. 
- x.style.backgroundColor = 'green';

### getElementByID()

### .innerHTML
- property of `<p>`

e.g. 
- `document.getElementByID('demo').innerHTML = 'Hello World';`

### More document methods
- `document.getElementByID`
- `document.getElementByClassName`
- `documentgetElementsByTagName`
- `document.querySelectorAll`

### Window Object
- Object represents the open window of a browser

e.g.

```
<script>
  function openWin() {
    window.open("", "", "width=100, height=100");
  }
</script>
```

## Events and Listeners

`addEventListener`
- attaches an event handler to an element
- Given function is known as a callback
- event.target is the tag the event originated from i.e. a button in example below

e.g. 
- `document.getElementById("button").addEventListener("Click", function (event) {...});`

### Responding to a click when a user clicks a button

```
<button class="event-button">Click me!</button>
<script>
  const button = document.querySelector('.event-button');
  button.addEventListener('click', function () {
    alert('Hey there!');
  });
</script>
```

- We grab the button via querySelector and store it in the JavaScript variable button.
- We then call the addEventListener method on the button.
- We then call a function called alert. alert is a super, super annoying function that pops up a dialog window with whatever you call it with.
- People often get confused seeing }); on the last line. The first } is closing the function, the second ) is closing the function call of addEventListener, and the ; ends the statement.

### `input` tage example

```
<input placeholder="type into me!" class="input-to-copy" />
<p class="p-to-copy-to">Nothing has happened yet.</p>
<script>
  const input = document.querySelector('.input-to-copy');
  const paragraph = document.querySelector('.p-to-copy-to');

  input.addEventListener('keyup', function () {
    paragraph.innerText = input.value;
  });
</script>
```

## Inline Event Handlers

```
<button id ="button onclick="myFunction()">Button 1</button>

<script>
  myFunction = () => {...}
</script>
```

## Event Delegation
- Event Bubbling: After firing click handler attached to a target, the browser will look in the level  above and execute any click handler attached
- Instead of attaching an event listner to every element, attach an event listener to the parent element

e.g.
- Element button => Element div => Element body => Element html => Document

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