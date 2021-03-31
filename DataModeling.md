# Data Modeling

Name 3 advantages to Test Driven Development

- Better program design and higher code quality
- improved design qualities in code
- TDD reduces the time required for project development

In what case would you need to use `beforeEach()` or `afterEach()` in a test suite?

- Use `beforeEach()` if a method needs to be called before a test is run
- Use `afterEach()` if you need to reset the environment after a test has run

What is one downside of Test Driven Development **TDD**?

slow process, tests got to be maintained when requirements change.

What’s the primary difference between **ES6** Classes and `Constructor`/`Prototype` Classes?

**ES6** `Classes` are syntactical sugar so it is easier to read and write.

Why REST?

**REST** is much easier than other approaches such as **SOAP** which keeps developers from having to reinvent the wheel as far as HTTP request operations go. SOAP also requires separate server and client programs. Since REST is based on standard HTTP operations, it uses verbs with specific meanings such as "get" or "delete" which avoids ambiguity. Resources are assigned individual URIs, adding flexibility. With REST, information that is produced and consumed is separated from the technologies that facilitate production and consumption. As a result, REST performs well, is highly scalable, simple, and easy to modify and extend.

## Term:

- _functional programming_
  Software is composed using pure functions (avoid shared state, mutable data, side-effects)
  If functions are interrelated, changing one function could break everything else

- _object-oriented programming_ **(OOP)**
  a computer programming model that organizes software design around data, or objects, rather than functions and logic. An object can be defined as a data field that has unique attributes and behavior.

- `class`
  Classes formalize the common JavaScript pattern of simulating class-like inheritance hierarchies using functions and prototypes.

- `super`
  a keyword to call the super constructor, used when creating a new constructor to inherit its properties

- `this`
  a keyword to define properties inside the {} scope

- _Test Driven Development_ **(TDD)**
  a software creation process in which software specifications are turned into test cases before the software is completely built, and all software development is tracked by comparing the software against all test cases several times.

- **Jest**

- _Continuous Integration_ **(CI)**
  a programming practice that allows developers to commit code to a public repository on a daily basis. After that, an automatic construct verifies each check-in, helping teams to catch issues early.

- _REST_
  Representational state transfer, a style used to create web applications using HTTP

- _Data Model_
  Data model is a diagram that illustrates relationships and behaviors of different pieces of an application and how those pieces depend on one another


### resources
[TDD](https://www.guru99.com/test-driven-development.html)
[OOP](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)
[CI](https://www.infoworld.com/article/3271126/what-is-cicd-continuous-integration-and-continuous-delivery-explained.html)
[Data Model](https://www.guru99.com/data-modelling-conceptual-logical.html)
