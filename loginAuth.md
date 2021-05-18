# `<Login />` and `<Auth />`

1. Why is the Context API useful?

   The Context API is useful because it can change important values for many components at once from a centralized location, without all of the values having to be passed through many layers of props.

2. Can a component outside of a provider get its context?

   React context is available only when the UI is available. This means that on background tasks you can't access it. But that doesn't mean that you can't access it "outside" of components.

3. What are some common use cases for using the Context API?

   Change the theme and as the profile data for the user to be access in any where inside the components

4. Describe “Context Hell”

   the React Context hell is the nasty code you get taking advantage of the React Context API. More on the subject here

# Terms

- global state

  state in multiple components that are not directly connected.

- global context

  Context is designed to share data that can be considered “global” for a tree of React components

- provider

  a Provider React component that allows consuming components to subscribe to context changes.

- consumer

  a Consumer React component that consumes components that are subscribed to context changes.

# Preparation Materials

- what is Role-Based Access Control (RBAC)?

  It restricts network access based on a person’s role within an organization
  You can designate management or employee roles that allow certain privileges.
  Having roles reduces administrative work, as a new employee can be assigned automatically by job title/function, and can decrease unnecessary access to sensitive information/documents.

- RBAC implementation:

  Define the resources that you need to limit access to.
  Define what roles you need for which resources.
  Assign people to those roles.
  Be careful when changing roles or adding new ones.
  Audit your system.

- Advantages from RBAC:

  Reducing administrative work and IT support.
  Maximizing operational efficiency
  Improving compliance.
