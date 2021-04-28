# Component Based UI

1. Name 5 Javascript UI Frameworks (other than React)?

   Ember.js, Vue.js, Angular, Polymer, Meteor

2. What’s the difference between a framework and a library?

   The technical difference between a framework and library lies in a term called inversion of control. When you use a library, you are in charge of the flow of the application. You are choosing when and where to call the library. When you use a framework, the framework is in charge of the flow.

## Term

- Rendering

  is the process of generating an image from a model by means of computer software. In the context of computer graphics rendering, software rendering refers to a rendering process that is not dependent upon graphics hardware ASICs, such as a graphics card. The rendering takes place entirely in the CPU.

- Templates

  A template is a form, mold, or pattern used as a guide to making something. Here are some examples:

  - A ruler is a template when used to draw a straight line.
  - A document in which the standard opening and closing parts are already filled in is a template that you can copy and then fill in the
  - variable parts.
  - An overlay that you put on your computer keyboard telling you special key combinations for a particular application is a template for selecting the right keys to press.
  - Flowcharting templates (not used much now) help programmers draw flowcharts or logic sequences in preparation for writing the code.
  - In programming, a template is a generic class or other unit of source code that can be used as the basis for unique units of code. In C++, an object-oriented computing language, there are Standard Template Libraries from which programmers can choose individual template classes to modify. The Microsoft Foundation Class Library (MFCL) is an example.

- State

  when you need to remember something. Functions (not "methods" or whatever) ideally only depend on their inputs. If you ask a question where the answer can change over time, even if the inputs are the same, you need something to remember that difference in the answer, correct? Otherwise, you are unable to give a different answer because no other factors have changed

## React

**What are the features of React?**

- JSX is a syntax extension to JavaScript. It is used with React to describe what the user interface should look like. By using JSX, we can write HTML structures in the same file that contains JavaScript code.

- Components: Components are the building blocks of any React application, and a single app usually consists of multiple components. It splits the user interface into independent, reusable parts that can be processed separately.

- Virtual DOM: React keeps a lightweight representation of the real DOM in the memory, and that is known as the virtual DOM. When the state of an object changes, virtual DOM changes only that object in the real DOM, rather than updating all the objects.

- One-way data-binding: React’s one-way data binding keeps everything modular and fast. A unidirectional data flow means that when designing a React app, you often nest child components within parent components.

- High performance: React updates only those components that have changed, rather than updating all the components at once. This results in much faster web applications.

**What is JSX?**

JSX is a syntax extension of JavaScript. It is used with React to describe what the user interface should look like. By using JSX, we can write HTML structures in the same file that contains JavaScript code.

**Can web browsers read JSX directly?**

Web browsers cannot read JSX directly. This is because they are built to only read regular JS objects and JSX is not a regular JavaScript object
For a web browser to read a JSX file, the file needs to be transformed into a regular JavaScript object. For this, we use Babel
