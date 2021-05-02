# Component Composition

1. Can a parent component access the state of a child component?

   In React we can access the child's state using Refs. we will assign a Refs for the child component in the parent component. then using Refs we can access the child's state. Creating Refs Refs are created using React.

2. What can be passed along in a prop variable?

   props enable you to pass variables from one to another component down the component tree. In the previous example, it was only a string variable. But props can be anything from integers over objects to arrays.

3. How can a child component “know” the state of another component?

   The most common method is to make a callback function that the child component will trigger and toss the state values upward.

## Term

- component props

  Props are arguments passed into React components. Props are passed to components via HTML attributes.

- component state

  an object that determines how that component renders & behaves. In other words, “state” is what allows you to create components that are dynamic and interactive.

- application state

  represents the totality of everything necessary to keep your application running

## Preparation Materials

React is a JavaScript library developed at Facebook for building user interfaces. This Track will give you a solid foundation for working with React.

React allows you to describe how your app should be displayed in an easy to understand way. It also helps eliminate the complexity that comes with updating your DOM elements when users interact with your application. React will change the way you think about building web applications!

Before enrolling in this Track, we recommend the courses JavaScript Loops, Arrays, and Objects, and Object-Oriented JavaScript as prerequisites.

We'll begin with an introductory course on React, where you'll learn about components, props, state, and a few other foundational things. Next, you'll level-up your React skills by gaining a better understanding of class vs. functional components, state and lifecycle methods, and how to split your UI into reusable and composable components.

The next part of the Track will walk you through how to use the Create React App, and then we'll learn how to use the React Context API. Then, our React Router 4 Basics course will teach you to use React Router v4, a declarative routing solution for React, to manage navigation and rendering of components in your applications.

When building an application using React, it is usually the case that developers will want to re-use component code. Developers new to React will often, instinctively, try to achieve this using inheritance. However, it is nearly always better to use React's composition model.

A good example of components that often need to re-use component code is tabs which show different content when selected. This guide will start with a set of tabs that re-use no code whatsoever and build specialized components, container components, and a combination of both to achieve re-use through composition.

You have seen how multiple functions can be composed together to achieve something bigger. The same applies to HTML elements and beyond to React components too. Let's encounter both, HTML element composition and React component composition, with a form that submits data.
