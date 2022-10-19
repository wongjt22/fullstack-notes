# React in a Nutshell
- React is a JavaScript library for building UI
- UIs are built by "UI components"

## Useful Tools
- Prettier
  - create a file called '.prettierrc' and put '{}' inside of it
- ESLint

# Getting Started
1. run 'npx create-react-app my-app'
  - 'my-app' is the name of the directory
2. run 'yarn start' in the 'my-app' directory

# React Basics
- All React files return a function or a class
  - AKA *functional components* and *class components*
  - Note: functional components are being phased out of the React ecosystem
- Functional components
  - Return some HTML
  - 'export default' at the bottom line to use 
- Import the relative path of CSS files to use them in a component
- Import images and define them to use them
  - e.g. 'import logo from './logo.svg';'
- e.g. '<img src={logo} className="App-logo" alt="logo" />'
- 'className' instead of 'class' to specify classes for CSS

## Variables in our code
- Variables can be used like so: '{myVar}'
- e.g.
  - Above return statement:
    - 'const myFavoriteNumber = 7;' 
  - Inside return statement:
    - '<p>My favorite number is {myFavoriteNumber}</p>'
  - Equivalent code:
    - '<p>My favorite number is {3 + parseNumber('4')}</p>'
    - '<p>My favorite number is {'7'}</p>'

# Components
- Reusable code segments
- Need to import them to use them

## What does a component need to have?

'''
import React from 'react';

const component = () => {
  return(
    {/* Component */}
  )
}

export default component
'''

## How to use a component

<Component />

# Index
- Everything in 'Index.js' is what is displayed in your browser
- 'Using document.getEleemntbyId('root')' we render our react code into an HTML element
- html is located in '/public/index/index.html'

## React DOM
- Used to render what is on your screen

## 'React.StrictMode'
- We receive a warning if React deects there might be any potential problems with the code it wraps

## Props
- pass 'props' into a component as a paramter 
- e.g.
'''
import React from 'react';

const component = (props) => {
  return(
    {props.text}
    {props.text}
  )
}

export default component
'''

## State
- Another way to pass around data
- e.g. Whether a door is opened or closed
- e.g. balance of a bank account

## Hooks
- used to engage in state management

## useState
- 'const [count, setCount] = useState(0);'
- count will automatically get set to 0 or any value passed in
- the second variable (setCount) will automatically become an updater function
- e.g. setCount(count + 1) will set the count to count + 1


## Rendering
- React only re-renders your screen when state is updated


