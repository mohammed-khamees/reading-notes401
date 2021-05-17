# Context API

1. Describe use cases for `useMemo()` and `useReducer()`?

   `useReducer()`: when you have complex state logic that involves multiple sub-values or when the next state depends on the previous one. It is best used when you are dealing with a complex object where individual properties need to be operated on
   `useMemo()`: when the data doesn’t change between renders.

2. Why do custom hooks need the use prefix?

   This convention is very important. Without it, we wouldn’t be able to automatically check for violations of rules of Hooks because we couldn’t tell if a certain function contains calls to Hooks inside of it

3. What do custom hooks usually do?

   extract component logic into reusable functions.

4. Using any list of custom hooks, research and name one that you think will be useful in your applications

   useWebSocket would be useful when building a game web app that needs to communicate with a websocket api.

5. Describe how a hook that fetches API data might work

   `React.useEffect(() => { // side effect hook // call API with props.greeting parameter setTranslation(response.data.translation); }, [setTranslation]);`

# Term

- reducer

  function that determines changes to an application’s state. It uses the action it receives to determine this change.

# Preparation Materials

Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.

Guide from React docs:

first you need to create a context : `const ThemeContext = React.createContext('light')`;

class App extends React.Component { render() { // Use a Provider to pass the current theme to the tree below. // Any component can read it, no matter how deep it is. // In this example, we're passing "dark" as the current value. return ( `<ThemeContext.Provider value="dark"> <Toolbar /> </ThemeContext.Provider>` ); } } // A component in the middle doesn't have to // pass the theme down explicitly anymore. function Toolbar() { return ( `<div> <ThemedButton /> </div>` ); } class ThemedButton extends React.Component { // Assign a contextType to read the current theme context. // React will find the closest theme Provider above and use its value. // In this example, the current theme is "dark". static contextType = ThemeContext; render() { return `<Button theme={this.context} />`; } }

in the example above we don't need to pass any props to the button to use the theme we are simply pass it to every component.

It' is not very recommended to use context a lot in your app because it will make the components less usable so avoid using them when you can.

### Using Context:

- `React.createContext(default value)`: to create a context
- ` <ThemeContext.Provider value=Current Value>``</ThemeContext.Provider> `: to pass the current value to the tree.
- `Class.contextType`
- `Context.Consumer`
- `Context.displayName`
