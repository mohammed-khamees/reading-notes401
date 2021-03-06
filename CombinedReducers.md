# Redux - Combined Reducers

1. Why choose Redux instead of the Context API for global state?

   Redux works around the idea of having a central state called a store. To change the state, a component has to dispatch an action. The action is then passed on to the reducer, which changes the state of our application

2. What is the purpose of a reducer?

   reducer is a function that determines changes to an application's state. It uses the action it receives to determine this change. We have tools, like Redux, that help manage an application's state changes in a single store so that they behave consistently. 3. What does an action contain?

An action contains a type and whatever payload you want it to have.

4. Why do we need to copy the state in a reducer?

   The reducer needs to be a pure function without any side-effects. It should only take in an action and return the new state.

# Term

- immutable state

  State cannot be modified, reducers must make copies of existing state to make updates.

- time travel in redux

  Redux DevTools records dispatched actions and the state of the Redux store at every point in time, which makes it possible to inspect the state and travel back in time to a previous application state without reloading the page or re-starting the app.

- action creator

  Actions send data from your application to your store, and are the only source of information for the store. An action creator is a function that creates an action.

- reducer

  Functions that take current state and an action as arguments, and return a new state result, `(state, action) => newState`.

- dispatch

  The only way to update the state is to call `store.dispatch()` and pass in an action object

# Preparation Materials

Combine reducers takes a hash of reducers and returns a reducer. The resulting reducer represents an object of the same shape as the hash.

```
const number = (state = 0, action) => {
    switch (action.type) {
            case 'INCREASE':
            return state + 1

            case 'DECREASE':
            return state - 1

            default: return state
        }
    }

    const rootReducer = combineReducers({number});
```

Then change your mapStateToProps to look like this:

`const mapStateToProps = ({number}) => ({number});`
