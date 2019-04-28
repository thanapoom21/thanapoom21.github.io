---
layout: default
title:  'What is node.js?'
nav_order: 3
description: "A breif explaination of node.js and its popularity."
---

## Asynchronous vs Synchronous

One of the terms that we have encountered with NodeJS is ```Asynchronous``` but what does it mean? Asynchronous execution means that the program doesn't run in the sequence it appears in your code editor from line 1 to line 100 chronologically. In NodeJS, async as its default, the program doesn't wait for the fist task to finish and execute the next line of code.

On the other hand, ```Synchronous``` execution generally refers to code that is transpiled or compiled and executed sequentially. In synchronous programming, the program is executed from line 1, then the next line until it reaches the last one at a time. The program waits for function to return something before continuing, everytime a function is called.

```javascript
// Asynchronous: 1,2,3,4,5
alert(1);
setTimeout(() => alert(2), 0);
alert(3);

// Synchronous: 1,3,2,4,5
alert(1);
alert(2);
alert(3);
```

## I/O(input/output)

It refers to program's interaction with the system disk and network.