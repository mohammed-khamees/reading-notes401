# Routing

1. Do child components have direct access to props/state from the parent?

   we can see there is no way to pass props from a child component to a parent component. However, we can always pass around functions from the parent to child component. The child component can then make use of these functions. The function can then update the state in a parent component, as we saw above.

2. When a component “wraps” another component, how does the child component’s output get rendered?

   By add the component as a children props

3. Can a component, such as `<Content />`, which is a child also be used as a standalone component elsewhere in the application?

   yes, sure

4. What trick can a parent use to share all props with it’s children
   ou can use `React.Children` to iterate over the children, and then clone each element with new props (shallow merged) using `React.cloneElement.`

## Term

- props.children

  Props are arguments passed into React components. Props are passed to components via HTML attributes.

- composition

  natural pattern of the component model. It’s how we build components from other components, of varying complexity and specialization through props. Depending on how generalized these

## What is React-Router, anyway?

Many modern websites are actually made up of a single page, they just look like multiple pages because they contain components which render like separate pages. These are usually referred to as SPAs - single-page applications. At its core, what React Router does is conditionally render certain components to display depending on the route being used in the URL (/ for the home page, /about for the about page, etc.).

To use React Router, you first have to install it using NPM:

`npm install react-router-dom`
Alternatively, you can just use this playground in Scrimba, which has the completed code already written.

You'll need to import BrowserRouter, Route, and Switch from react-router-dom package:

```
import React, { Component } from 'react';
import { BrowserRouter, Route, Switch } from 'react-router-dom';
```

In my example, I link the landing page with two other "pages" (which are actually just components) called Shop and About.

First, you'll need to set up your app to work with React Router. Everything that gets rendered will need to go inside the `<BrowserRouter>` element, so wrap your App in those first. It's the component that does all the logic of displaying various components that you provide it with.

```
// index.js
ReactDOM.render(
    <BrowserRouter>
        <App />
    </BrowserRouter>,
    document.getElementById('root')
)
```

Next, in your App component, add the Switch element (open and closing tags). These ensure that only one component is rendered at a time. If we don't use this, we can default to the Error component, which we're going to write later.

```
function App() {
    return (
        <main>
            <Switch>

            </Switch>
        </main>
    )
}
```

It's now time to add your `<Route> `tags. These are the links between the components and should be placed inside the`<Switch>`tags.

To tell the `<Route>` tags which component to load, simply add a path attribute and the name of the component you want to load with component attribute.

```
<Route path='/' component={Home} />

```

```
function App() {
    return (
        <main>
            <Switch>
                <Route path="/" component={Home} exact />
                <Route path="/about" component={About} />
                <Route path="/shop" component={Shop} />
            </Switch>
        </main>
    )
}
```
