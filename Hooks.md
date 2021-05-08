# Hooks API

1. Why do we not need more .html pages in a multi-page React app?
   because of `react-router-dom` Many modern websites are actually made up of a single page, they just look like multiple pages because they contain components which render like separate pages. These are usually referred to as SPAs - single-page applications. At its core, what React Router does is conditionally render certain components to display depending on the route being used in the URL (/ for the home page, /about for the about page, etc.).

2. If we wanted a component to show up on every page, where would we put it and why?

   - Inside the `<BrowserRouter />`, outside a `<Route />`

3. What does props.children contain?

   this.props.children does is that it is used to display whatever you include between the opening and closing tags when invoking a component.

## Term

- Composition

  composition is a natural pattern of the component model. It's how we build components from other components, of varying complexity and specialization through props. Depending on how generalized these components are, they can be used in building many other components.

- Children / Child Components

  The React docs say that you can use props.children on components that represent ‘generic boxes’ and that ‘don’t know their children ahead of time’. For me, that didn’t really clear things up. I’m sure for some, that definition makes perfect sense but it didn’t for me.

- Hash Routing
  A `<Router>` that uses the hash portion of the URL (i.e. window.location.hash) to keep your UI in sync with the URL.

- Link Routing
  Provides declarative, accessible navigation around your application.

## React Hooks

React Hooks are in-built functions that allow React developers to use state and lifecycle methods inside functional components, they also work together with existing code, so they can easily be adopted into a codebase. The way Hooks were pitched to the public was that they allow developers to use state in functional components but under the hood, Hooks are much more powerful than that. They allow React Developers to enjoy the following benefits:

- Improved code reuse
- Better code compositions
- Better defaults
- Sharing non-visual logic with the use of custom hooks
- Flexibility in moving up and down the components tree.

With React Hooks, developers get the power to use functional components for almost everything they need to do from just rendering UI to also handling state and also logic — which is pretty neat.

- Basic Hooks

  1. `useState`
  2. `useEffect`
  3. `useContext`

- Additional Hooks

  1. `useReducer`
  2. `useCallback`
  3. `useMemo`
  4. `useRef`
  5. `useImperativeHandle`
  6. `useLayoutEffect`
  7. `useDebugValue`

### Rules of Hooks

- Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use Hooks at the top level of your React function, before any early returns. By following this rule, you ensure that Hooks are called in the same order each time a component renders. That’s what allows React to correctly preserve the state of Hooks between multiple `useState` and `useEffect`

- Don’t call Hooks from regular JavaScript functions. Instead, you can:
  1. Call Hooks from React function components.
  2. Call Hooks from custom Hooks (we’ll learn about them on the next page).
