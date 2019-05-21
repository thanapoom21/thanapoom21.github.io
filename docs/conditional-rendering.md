---
layout: default
title:  'React - Conditional Rendering'
nav_order: 11
description: "Conditionally Rendering Components in React"
---

## Conditional rendering is the same in React and JavaScript

It is possible to create distinct components that encapsulate a specific behavior in React. Also, components can be rendered depending on the state of the application.

`if()` or `condition ? expressionTrue : expressionFalse` can be used to create elements representing the current state, and React will update the UI to match them.

Greeting components displaying either of UserGreeting or GuestGreeting components depend on whether a user is logged in:

```js
function UserGreeting(props) {
    return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
    return <h1>Please sign up.</h1>;
}

function Greeting(props) {
    const isLoggedIn = props.isLoggedIn;
    if (isLoggedIn) {
        return <UserGreeting />;
    }
    return <GuestGreeting />;
}

React.DOM.render(
    <Greeting isLoggedIn={false} />,
    document.getElementById('root')
);
```

[Try it on CodePen](https://codepen.io/gaearon/pen/ZpVxNq?editors=0011)

### Element Variables

Elements can be stored in variables and will help conditionallt render a part of the component while the rest of the output doesn't change.

This is an example showing a stateful component called `LoginControl`.

```js
function LoginButton(props) {
    return (
        <button onClick={props.onClick}>
            Login
        </button>
    );
}

function LogoutButton(props) {
    return (
        <button onClick={props.onClick}>
            Logout
        </button>
    );
}

class LoginControl extends React.Component {
    constructor(props) {
        super(props);
        this.handleLoginClick = this.handleLoginClick.bind(this);
        this.handleLogoutClick = this.handleLogoutClick.bind(this);
        this.state = { isLoggedIn: false };
    }

    handleLoginClick() {
        this.setState({ isLoggedIn: true });
    }

    handleLogoutClick() {
        this.setState({ isLoggedIn: false });
    }

    render() {
        const isLoggedIn = this.state.isLoggedIn;
        let button;

        if (isLoggedin) {
            button = <LogoutButton onClick={this.handleLogoutClick} />;
        } else {
            button = <LoginButton onClick={this.handleLoginClick} />;
        }

        return (
            <div>
                <Greeting isLoggedIn={isLoggedIn} />
                {button}
            </div>
        );
    }
}

ReactDOM.render(
    <LoginControl />,
    document.getElementById('root')
);
```

While declaring a variable and using an `if` statement is a fine way to conditionally render a component, sometimes you might want to use a shorter syntax. There are a few ways to inline conditions in JSX.