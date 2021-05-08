# Custom Hooks

1. What does a component’s lifecycle refer to?

   React components do as well. Components are created (mounted on the DOM), grow by updating, and then die (unmount on DOM). This is referred to as a component lifecycle.

2. Why do you sometimes need to “wrap” functions in useCallback when called from within `useEffect`

   useCallback will help in avoiding regeneration of functions when the functional component re-renders. However there isn't much of a performance difference caused by recreation of functions. You are specifying a function as a dependency to useEffect .

3. Why are functional components preferred over class components?

   you should use functional components if you are writing a presentational component which doesn’t have its own state or needs to access a lifecycle hook. Otherwise you can stick to class components or take a look into the library recompose which allows you to write functional components and enhance them with a state or lifecycle hooks with HOCs!

4. What is wrong with the following code?

**Hooks inside loops** which useEffect

```
import React, {useState, useEffect} from 'react';

function MyComponent(props) {
  const [count, setCount] = useState(0);

  function changeCount(e) {
    setCount(e.target.value);
  }

  let renderedItems = []

  for (let i = 0; i < count; i++) {
    useEffect( () => {
      console.log('component mount/update');
    }, [count]);

    renderedItems.push(<div key={i}>Item</div>);
  }

  return (<div>
     <input type='number' value={count} onChange={changeCount}/>
      {renderedItems}
    </div>);
}
```

## Term

- state hook

  We call it inside a function component to add some local state to it. React will preserve this state between re-renders. useState returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler or somewhere else.

- effect hook

  adds the ability to perform side effects from a function component. It serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes, but unified into a single API

- reducer hook

  a reducer of type (state, action) => newState, and returns the current state paired with a dispatch method.

## other hooks

`useToggle`
Basically, what this hook does is that, it takes a parameter with value true or false and toggles that value to opposite. It's useful when we want to take some action into it's opposite action, for example: show and hide modal, show more/show less text, open/close side menu.

`useFirestoreQuery`
This hook makes it super easy to subscribe to data in your Firestore database without having to worry about state management. Instead of calling Firestore's query.onSnapshot() method you simply pass a query to useFirestoreQuery() and you get back everything you need, including status, data, and error. Your component will re-render when data changes and your subscription will be automatically removed when the component unmounts. Our example even supports dependent queries where you can wait on needed data by passing a falsy value to the hook.

`useMemoCompare`
This hook is similar to useMemo, but instead of passing an array of dependencies we pass a custom compare function that receives the previous and new value. The compare function can then compare nested properties, call object methods, or anything else to determine equality. If the compare function returns true then the hook returns the old object reference.

It's worth noting that, unlike useMemo, this hook isn't meant to avoid expensive calculations. It needs to be passed a computed value so that it can compare it to the old value. Where this comes in handy is if you want to offer a library to other developers and it would be annoying to force them to memoize an object before passing it to your library. If that object is created in the component body (often the case if it's based on props) then it's going to be a new object on every render. If that object is a useEffect dependency then it's going to cause the effect to fire on every render, which can lead to problems or even an infinite loop. This hook allows you to avoid that scenario by using the old object reference instead of the new one if your custom comparison function deems them equal.

`useAsync`
It's generally a good practice to indicate to users the status of any async request. An example would be fetching data from an API and displaying a loading indicator before rendering the results. Another example would be a form where you want to disable the submit button when the submission is pending and then display either a success or error message when it completes.

Rather than litter your components with a bunch of useState calls to keep track of the state of an async function, you can use our custom hook which takes an async function as an input and returns the value, error, and status values we need to properly update our UI. Possible values for status prop are: "idle", "pending", "success", "error". As you'll see in the code below, our hook allows both immediate execution and delayed execution using the returned execute function.`

`useRequireAuth`
A common need is a way to redirect the user if they are signed out and trying to view a page that should require them to be authenticated. This example shows how you can easily compose our useAuth and useRouter hooks to create a new useRequireAuth hook that does just that. Of course, this functionality could be added directly to our useAuth hook, but then we'd need to make that hook aware of our router logic. Using the power of hook composition we can keep the other two hooks as simple as possible and just utilize our new useRequireAuth when redirection is needed.

`useRouter`
If you use React Router you might have noticed they recently added a number of useful hooks, specifically useParams, useLocation, useHistory, and use useRouteMatch. But let's see if we can make it even simpler by wrapping them up into a single useRouter hook that exposes just the data and methods we need. In this recipe we show how easy it is to compose multiple hooks and combine their returned state into a single object. It makes a lot of sense for libraries like React Router to offer a selection of low-level hooks, as using only the hook you need can minimize unnecessary re-renders. That said, sometimes you want a simpler developer experience and custom hooks make that easy.

`useAuth`
A very common scenario is you have a bunch of components that need to render different depending on whether the current user is logged in and sometimes call authentication methods like signin, signout, sendPasswordResetEmail, etc.

This is a perfect use-case for a useAuth hook that enables any component to get the current auth state and re-render if it changes. Rather than have each instance of the useAuth hook fetch the current user, the hook simply calls useContext to get the data from farther up in the component tree. The real magic happens in our `<ProvideAuth>` component and our useProvideAuth hook which wraps all our authentication methods (in this case we're using Firebase) and then uses React Context to make the current auth object available to all child components that call useAuth. Whew, that was a mouthfull...

Hopefully as you read through the code below it should all make sense. Another reason I like this method is it neatly abstracts away our actual auth provider (Firebase), making it super easy to change providers in the future.

`useEventListener`
If you find yourself adding a lot of event listeners using useEffect you might consider moving that logic to a custom hook. In the recipe below we create a useEventListener hook that handles checking if addEventListener is supported, adding the event listener, and removal on cleanup.

`useWhyDidYouUpdate`
This hook makes it easy to see which prop changes are causing a component to re-render. If a function is particularly expensive to run and you know it renders the same results given the same props you can use the React.memo higher order component, as we've done with the Counter component in the below example. In this case if you're still seeing re-renders that seem unnecessary you can drop in the useWhyDidYouUpdate hook and check your console to see which props changed between renders and view their previous/current values.

`useDarkMode`
This hook handles all the stateful logic required to add a ☾ dark mode toggle to your website. It utilizes localStorage to remember the user's chosen mode, defaults to their browser or OS level setting using the prefers-color-scheme media query and manages the setting of a .dark-mode className on body to apply your styles.
