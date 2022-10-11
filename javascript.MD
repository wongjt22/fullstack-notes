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

