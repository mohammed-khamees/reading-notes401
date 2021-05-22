# Application State with Redux

1. What are the advantages of storing tokens in “Cookies” vs “Local Storage”

   Cookies are read server-side, and local storage is read client-side, so if the server needs the data, then it is better to use cookies.

2. Explain 3rd party cookies.

   Third-party cookies are cookies that are set by a website other than the one you are currently on. For example, you can have a “Like” button on your website which will store a cookie on a visitor’s computer, that cookie can later be accessed by Facebook to identify visitors and see which websites he visited.

3. How do pixel tags work?

   Pixel tags are typically single pixel, transparent GIF images that are added to a web page. Even though the pixel tag is virtually invisible, it is still served just like any other image you may see online.

## Term

- cookies

  They are pieces of code that web servers use to put information on a user’s browser, and then retrieve that information at a later time for various uses

- authorization

  Authorized the user to go to different areas based on what they are allowed to see and do

- access control

  is a fundamental component of data security that dictates who’s allowed to access and use company information and resources. Through authentication and authorization, access control policies make sure users are who they say they are and that they have appropriate access to company data.

- conditional rendering

  a term to describe the ability to render different user interface (UI) markup if a condition is true or false. In React, it allows us to render different elements or components based on a condition. This concept is applied often in the following scenarios: Rendering external data from an API.

## Preparation Materials

Redux is a predictable state container for JavaScript applications. It helps you write apps that behave consistently, run in different environments (client, server, and native), and are easy to test. Redux manages an application’s state with a single global object called Store.

Redux solves the state transfer problem by storing all of the states in a single place called a store. So, managing and transferring states becomes easier as all the states are stored in the same convenient store. Every component in the application can then directly access the required state from that store.

- What Redux does in a very general sense, is that it creates a global state for the whole application, that can be accessed by any of your component
- It is a state management library
- You have only one state for your whole app, and not states for each of your components

### When working with Redux, you will need three main things:

- actions: these are objects that should have two properties, one describing the type of action, and one describing what should be changed in the app state.

- reducers: these are functions that implement the behavior of the actions. They change the state of the app, based on the action description and the state change description.

- store: it brings the actions and reducers together, holding and changing the state for the whole app — there is only one store.

**Benefits and limitations of Redux**

- State transfer: State is stored together in a single place called the ‘store.’ While you don’t need to store all the state variables in the ‘store,’ it’s especially important to when state is being shared by multiple components or in a more complex architecture.

- As your application grows larger, it can be increasingly difficult to identify the source of the state variables, which is why a ‘store’ is useful. It also allows you to call state data from any component easily.

- Predictability: Redux is “a predictable state container for JavaScript apps.” Because reducers are pure functions, the same result will always be produced when a state and action are passed in. Furthermore, the slices of state are defined for you, making the data flow more predictable.

- Maintainability: Redux provides a strict structure for how the code and state should be managed, which makes the architecture easy to replicate and scale for somebody who has previous experience with Redux.

- Ease of testing and debugging: Redux makes it easy to test and debug your code since it offers powerful tools such as Redux DevTools in which you can time travel to debug, track your changes, and much more to streamline your development process.
