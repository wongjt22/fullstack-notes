# Node
- JavaScript runtime engine built on Chrome's V8 JavaScript engine that allows you to run JavaScript even without a browser

### NPM
- Node package manager (NPM)
- 'npm init' creates a new npm package 
- use 'npm init -y' to skip config steps and create the most basic package

## JavaScript in Browser vs. Node.js
- Node.js
  - 'require' imports other modules
  - e.g. : 'const axios = require('axios');'
  - no 'document' object
  - no 'fetch' method

# Web Server with Node & Express
- Express is used to set up a web server
- 'npm install express'

### Basic Web Server
'''
const axios = require('axios');
const express = require('express');
const port = 3000;

const app = express();

app.get('/', (req, res) => {
  res.send('Hello World');
});

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`);
});
'''

'const app = express()'
- creates an app object with useful methods

'''
app.get('/', (req, res) => {
  res.send('Hello World');
});
'''
- When a user makes a 'GET' request to the '/' url (root) send a reponse: Hello World!

'''
app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`);
});
'''
- 'listen' listens for any requests at a specific port

### Types of data
1. metadata: data that defines the state of our database and its characteristics
  - e.g. : database capacity
2. data: the items we put

## REST API Principles
- GET returns information that we query to it.
- POST requests that the origin server accept a new entity
  - We don't know the "shape" of our data, so we use the "body" as a container for the data we want to send.
  - e.g. : const item = req.body.item;
- PUT requests that the origin server accept a new entity but if it already exists it modifies the entity

## Node and File System
- Building an API where te user can input the name and type of a file the server creates
- http://localhost:3000/create/?name=resume&type=txt
'''
const fs = require("fs");

...

app.get('/create', (req, res) => {
  let name = req.query.name;
  let type = req.query.type;
  let filename = name + '.' + type;
  fs.appendFile(filename, ' ', (err) => {
    if (err) res.send(err);
    res.send({
      "message": "File created!",
      "name": name,
      "type": type
    })
  })
})
'''



