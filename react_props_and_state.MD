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





  



