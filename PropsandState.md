# Props and State

1. Does a deployed React application require a server?

   You don't necessarily need a static server in order to run a Create React App project in production. It also works well when integrated into an existing server side app.

2. Why do we prefer to test a React application at the behavior rather than the unit level?

   teration speed vs Realistic environment: Some tools offer a very quick feedback loop between making a change and seeing the result, but don’t model the browser behavior precisely. Other tools might use a real browser environment, but reduce the iteration speed and are flakier on a continuous integration server.

3. What does `npm run build` do?

   `npm` run build runs the script `"build"` and created a script which runs your application - let's say server.js.

4. Describe the actual composition / architecture of a React application

   Reactjs doesn’t enforce an architecture pattern. It is just a view that caters to the user interface.

## Terms:

- BDD

  In software engineering, behavior-driven development (BDD) is an Agile software development process that encourages collaboration among developers, QA, and non-technical or business participants in a software project.

- Acceptance Tests

  acceptance testing is a test conducted to determine if the requirements of a specification or contract are met. It may involve chemical tests, physical tests, or performance tests

- mounting

  Mounting can be defined as the software process that activates a particular disk by making its content available to the computer's file system. ... In Unix systems, all file systems other than the root user are mounted during the boot time. Before the mounted device is removed from the computer, it must be unmounted.

- build

  build React applications. It saves you from time-consuming setup and configuration. You simply run one command and create react app sets up the tools you need to start your React project.

## State and Props in React:

In a React component, props are variables passed to it by its parent component. State on the other hand is still variables, but directly initialized and managed by the component.

The state can be initialized by props.

- State

The state is an updatable structure that is used to contain data or information about the component and can change over time. The change in state can happen as a response to user action or system event. It is the heart of the react component which determines the behavior of the component and how it will render. A state must be kept as simple as possible. It represents the component's local state or information. It can only be accessed or modified inside the component or by the component directly.

- Props

  Props are read-only components. It is an object which stores the value of attributes of a tag and work similar to the HTML attributes. It allows passing data from one component to other components. It is similar to function arguments and can be passed to the component the same way as arguments passed in a function. Props are immutable so we cannot modify the props from inside the component.

`useState` is a Hook (we’ll talk about what this means in a moment). We call it inside a function component to add some local state to it. React will preserve this state between re-renders. `useState` returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler or somewhere else. It’s similar to this.setState in a class, except it doesn’t merge the old and new state together. (We’ll show an example comparing `useState` to this.state in Using the State Hook.)

**Handling events** with React elements is very similar to handling events on DOM elements. There are some syntax differences: React events are named using camelCase, rather than lowercase. With JSX you pass a function as the event handler, rather than a string.
