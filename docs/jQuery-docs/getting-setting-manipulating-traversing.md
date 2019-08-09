---
layout: default
title: Getting, Setting, Manipulating, and Traversing
nav_order: 2
has_children: true
permalink: /docs/jQuery-docs
description: "Getting, Setting, Manipulating, and Traversing in Action"
---

## Get, Set, Manipulate, and Traverse data in JavaScript using jQuery

```js
/**
  *
  This text() method will add string to the DOM.
  However, this method will not be able to compile html elements.
  *
  **/
$(".selectedElement").text("This is a new text");
```

```js
// This html() method will add strings of texts and html elements to the DOM.
$(".selectedElement").html(
  "This is a text with <strong>an html element</strong>"
);
```

```js
/**
  *
  We can use constant variable to store string value and use it later.
  Then we add newText variable to the selected element using append() method.
  *
  **/
const newText = "This is a new text";
$(".selectedElement").append(newText);
```

```js
/**
  *
  Let's say we want to manipulate the value of a form input.
  <ul id="">
    l
  </ul
  *
  **/
const newText = "This is a new text";
$(".selectedElement").append(newText);

$;
```
