# React 2: More Hooks, Libraries, Styling, and Routing

The most important hooks:
- useEffect
- useState

Example:
'''
import React, { useState } from 'react';

const Counter = () => {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
};
'''

### useState
- e.g. 'const [fruit, setFruit] = useState('banana');'
- Equivalent: 
'''
var fruitStateVariable = useState('banana'); // Returns a pair
var fruit = fruitStateVariable[0]; // First item in a pair
var setFruit = fruitStateVariable[1]; // Second item in a pair
'''
- 'useState(arg)'
- 'arg' is the initial state 
- Additional example:
'''
const ExampleWithManyStates = () => {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
};
'''

### useEffect
- Import:
'import React, { useState, useEffect } from 'react';'
- 'useEffect' is called when React renders/updates. i.e. Another hook is called.
- First argument: function to call when useEffect is triggered
- Second argument: array of dependencies
- e.g.
'''
useEffect(() => {
  setScore(someNewScore);
}, [referee]);
'''
- This code updates our 'score' but only if 'referee' has changed
'''
useEffect(() => {
  setScore(someNewScore);
}, [referee, inning]);
'''
- This code updates score if either 'referee' or 'inning' change

### Running useEffect on First render
- e.g.
'''
useEffect(() => {
  console.log('Hello World');
}, []);
'''

# Styling in React
