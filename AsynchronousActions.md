# Redux - Asynchronous Actions

1. How granular should your reducers be?

   There should be a separate reducer function for each slice of data. They are combined before being put into the store.

2. Pro or Con – multiple reducers can “fire” when a commonly named action is dispatched

   When your reducer has finished and returned the new application state, asyncDispatch will trigger store. dispatch with whatever action you give to it. You might try using a library like redux-saga.

3. Name a strategy for preventing the above

   You can use more specific names that represent the reducer and data want to change .

# Term

- store

  Holds the whole state tree of the application, only way to change the state inside is to dispatch an action on it.

- combined reducers

  It turns out that Redux lets us combine multiple reducers into one that can be passed into createStore by using a helper function named combineReducers . The way we combine reducers is simple, we create one file per reducer in the reducers directory. We also create a file called index. js inside the reducers directory.

# Preparation Materials

Redux Middleware Store only knows how to synchronously dispatch actions, update the state by calling the root reducer function, and notify the UI that something has changed. Any asynchronicity has to happen outside the store. Some common kinds of side effects are things like: Generating random numbers or unique random IDs (such as `Math.random()` or `Date.now`)

Redux’s actions are dispatched synchronously, which is a problem for any non-trivial app that needs to communicate with an external API or perform side effects. Redux also allows for middleware that sits between an action being dispatched and the action reaching the reducers.

There are two very popular middleware libraries that allow for side effects and asynchronous actions: Redux Thunk and Redux Saga. In this post, you will explore Redux Thunk

Thunk is a programming concept where a function is used to delay the evaluation/calculation of an operation.

Redux Thunk is a middleware that lets you call action creators that return a function instead of an action object. That function receives the store’s dispatch method, which is then used to dispatch regular synchronous actions inside the function’s body once the asynchronous operations have been completed.
