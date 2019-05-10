---
layout: default
title:  'What is express.js?'
nav_order: 8
description: "A breif explaination of express.js, a framework for NodeJS and how to use it."
---

[Express](https://expressjs.com)

## A fast and minimal framework for Node.js

Express.js is one of the most popular Node frameworks.

### How to install express from the command line

Start from creating a directory.

```js
mkdir directoryname // create a directory with a desired name.
cd directoryname // change directory to the created one.
npm init // create a package.json file.
```

```js
entry point: (app.js) // enter the file name you want node to read as entry point.
```

```js
npm install express --save // install express in the directory and save it as a dependency.
npm install express --no-save // install express temporarily without save it as a dependency.
```

### A simple express example

```js
const express = require('express' 4.16.4); // save express module with version in a constant named express.
const app = express(); // save express function in app as convention.
const port = 5000; // specify a port number.

app.get('/', (req, res) => res.send('This is Express')); // responds with "This is Express" to the browser."

app.listen(port, () => console.log(`Example app is listening on port ${port}!`));
```

This will start a server and listens on port 5000 for connections responding with ```This is Express``` for requests to the root URL ```'/'``` or ```route```. It will respond with a 404 Not Found for other paths.

### To run the app locally

```js
node app.js
```

## What is Express application generator

It is for rapidly creating an app skeleton. For installing, use:

```js
npm install express-generator -g
```
