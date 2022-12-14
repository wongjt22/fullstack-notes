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

## CSS-in-JS
- CSS is global in react
  - If you import a CSS file into one component it will apply to all of your components

## CSS Modules
- Component scoped
- '<file name>.module.css'
- Change from:
'''
//Importing Regular CSS
import './styles.css';

//Using Regular CSS
<div className="container">
  <h3>Hi There!</h3>
</div>;
'''
- To:
'''
//Importing CSS Modules
import styles from './styles.module.css';

//Using CSS Modules
<div className={styles['container']}>
  <h3>Hi There!</h3>
</div>;
'''
- Treat your CSS file as an object and access the class names like an object's attributes
[Documentation](https://github.com/css-modules/css-modules)

## Styled Components

Installation
'npm i styled-components'

e.g.
'''
const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: palevioletred;
`;

const Wrapper = styled.section`
  padding: 4em;
  background: papayawhip;
`;

render(
  <Wrapper>
    <Title>Hello World!</Title>
  </Wrapper>
);
'''

'''
const Button = styled.button`
  background: ${(props) =>
    props.primary === true ? 'palevioletred' : 'white'};
  color: ${(props) => (props.primary ? 'white' : 'palevioletred')};
  font-size: 1em;
  margin: 1em;
  padding: 0.25em 1em;
  border: 2px solid palevioletred;
  border-radius: 3px;
`;

render(
  <div>
    <Button>Normal</Button>
    <Button primary={true}>Primary</Button>
  </div>
);
'''

[Documentation](https://styled-components.com/)

# Component Libraries
- Popular libraries: React-Bootstrap, Theme UI, Chakra UI

## Chakra UI
- Style Props: All component styles can be overridden or extended via style props to reduce the use of css prop or styled(). Compose new components from Box.
- Dark Mode: Make components dark mode compatible. Use useColorMode hook to handle styling. Learn more about dark mode.
- Naming Props: We all know naming is the hardest thing in this industry. Generally, ensure a prop name is indicative of what it does. Boolean props should be named using auxiliary verbs such as does, has, is and should. For example, Button uses isDisabled, isLoading, etc.

[Documentation](https://chakra-ui.com/docs/comparison)

Installation
'yarn add @chakra-ui/react @emotion/react@^11 @emotion/styled@^11 framer-motion@^5'

Setup Provider
'''
import * as React from 'react';

// 1. import `ChakraProvider` component
import { ChakraProvider } from '@chakra-ui/react';

function App({ Component }) {
  // 2. Use at the root of your app
  return (
    <ChakraProvider>
      <Component />
    </ChakraProvider>
  );
}
'''

## React-Bootstrap

Installation
'yarn add react-bootstrap bootstrap'

Incorporating Bootstrap
'''
import React, { Component } from 'react';
import Alert from 'react-bootstrap/Alert';

const Example = () => {
  return (
    <Alert dismissible variant="danger">
      <Alert.Heading>Oh snap! You got an error!</Alert.Heading>
      <p>Change this and that and try again.</p>
    </Alert>
  );
};

export default Example;
'''

[Documentation](https://react-bootstrap.github.io/getting-started/introduction/)

## Other Libraries
- [Material-UI](https://material-ui.com/)
- [Ant Design - The world's second most popular React UI framework](https://ant.design/)
- [Semantic UI](https://semantic-ui.com/)

### Alternatives to a component library
- [Tailwind](https://tailwindcss.com/)
- [Pure](https://purecss.io/)

## Package Managers

### Node
- 'npm'
- Packages are stored in 'node_modules'

### Yarn
- No practical difference with NPM
- Slight speed and security advantages

# React Router
- Rather than creating a route for each video on youtube, use dynamic routing to display countless similar pages using a variable in the URL
- Routing is client-side rather than having to reload your entire app all over again

[Documentation](https://v5.reactrouter.com/web/guides/quick-start)

Installation
'yarn add react-router-dom'

## Basic Routing
'''
import React from 'react';
import { BrowserRouter, Switch, Route, Link } from 'react-router-dom';

const App = () => {
  return (
    <BrowserRouter>
      <div>
        {/* The HTML */}
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/users">Users</Link>
            </li>
          </ul>
        </nav>

        {/* The React Router that makes the HTML above work */}
        <Switch>
          <Route path="/about">
            <About />
          </Route>
          <Route path="/users">
            <Users />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </BrowserRouter>
  );
};

const Home = () => <h2>Home</h2>;
const About = () => <h2>About</h2>;
const Users = () => <h2>Users</h2>;

export default App;
'''

## Dynamic Routing
- What if we have too many routes to write down manually?
'''
import React from 'react';
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link,
  useParams,
} from 'react-router-dom';

function DynamicRouting() {
  const data = [
    { name: 'Netflix', route: 'netflix' },
    { name: 'Zillow', route: 'zillow' },
    { name: 'Yahoo', route: 'yahoo' },
    { name: 'Instagram', route: 'instagram' },
  ];

  return (
    <Router>
      <div>
        <h2>Accounts</h2>

        <div>
          {data.map((item) => (
            <Link to={`/${item.route}`}>
              <div>
                <h3>{item.name}</h3>
              </div>
            </Link>
          ))}
        </div>

        <Switch>
          <Route path="/:id" children={<Child />} />
        </Switch>
      </div>
    </Router>
  );
}

function Child() {
  let { id } = useParams();

  return (
    <div>
      <h3>{id}</h3>
    </div>
  );
}

export default DynamicRouting;
'''

## Complet Routing - WDB Website example
'''
import { BrowserRouter as Router, Switch, Route } from 'react-router-dom';

import Navbar from './components/navbar';
import Footer from './components/footer';

import Landing from './pages/landing';
import About from './pages/about';
import Initiatives from './pages/initiatives';
import Error from './pages/error';

import './App.scss';

function App() {
  return (
    <Router>
      <Switch>
        <Route exact path="/">
          <Navbar landing />
        </Route>
        <Route path="*">
          <Navbar />
        </Route>
      </Switch>

      <Switch>
        {/* About Us */}
        <Route path="/about">
          <About />
        </Route>

        {/* Initiatives */}
        <Route path="/initiatives">
          <Initiatives />
        </Route>

        {/* Landing Page */}
        <Route exact path="/">
          <Landing />
        </Route>

        {/* 404 no page found */}
        <Route path="*">
          <Error />
        </Route>
      </Switch>

      <Footer />
    </Router>
  );
}

export default App;
''

The exact prop tells our router to only show the landing version of the navbar when there are no extensions to the URL, which makes sense since we want our landing page to be the default page. Using * as the path for our regular navbar tells the router that for all other pages, render the regular navbar.

Using a single variable as a prop (such as exact or landing above) is equivalent to setting exact={true} or landing={true} as a prop. Thus we just use exact or landing instead of the whole statement as shorthand.

