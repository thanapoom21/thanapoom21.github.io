---
layout: default
title:  'React - State and Lifecycle'
nav_order: 9
description: "Introducing the concept of state and lifecycle in a React component"
---

## React State and Lifecycle

Calling `ReactDOM.render()` to change the rendered output:

```js
function tick() { // a functional component
    const element = (
        <div>
            <h1>Hello, world!</h1> {/* A JSX element */}
            <h2>It is {new Date().toLocaleTimeString()}.</h2> {/* create and use Date object and convert it to locale time. */}
        </div>
    );
    ReactDOM.render(
        element, // element constant to be rendered.
        document,getElementById('root') // to where the selected element should be rendered.
    );
}

setInterval(tick, 1000); // wait 1 second before executing tick function component.
```

Making the `Clock` component reuseable and encapsulated. It will set up its own timer and update itself every second.

We can start by encapsulating how the clock looks:

```js
function Clock(props) {
    return (
        <div>
            <h1>Hello, world!</h1>
            <h2>It is {props.date.toLocaleTimeString()}.</h2>
        </div>
    );
}

function tick() {
    ReactDOM.render(
        <Click date={new Date()} />,
        document.getElementById('root')
    );
}

setInterval(tick, 1000);
```

However, it misses a crucial requirement: the fact that the Clock sets up a timer and updates the UI every second should be an implementation detail of the Clock.

Ideally we want to write this once and have the Clock update itself:

```js
ReactDOM.render(
    <Clock />,
    document.getElementById('root')
);
```

To implement this, we need to add `state` to the `Clock` compoment.

State is similar to props, but it is private and fully controlled by the component.