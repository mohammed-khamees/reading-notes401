# Stacks and Queues

**What is a Stack?**

A stack is a linear data structure with a “last in first out” principle. What does that mean? Imagine we have a list of information. When we add something to the list it gets added to the end. When we remove something from the list, we remove it from the end. It is like a stack of paper we add pieces of paper to the stack, and we remove pieces of paper for the top of the stack (We don’t pull from the bottom, or the middle). The important thing to remember is that the same end of the data structure is used to insert and delete data.

```
const stack = []            // create a new array
stack.push(‘google’)        // push 'google' onto the stack
stack.push(‘instagram’)     // push 'instagram' onto the stack
stack.push(‘youtube’)       // push 'youtube' onto the stack
stack = [‘google’, ‘instagram’, ‘youtube’] // current stack
stack.pop()                 // remove last element added to stack
//stack = [‘google’, ‘instagram’] // current stack

```

**What is a Queue?**

A Queue is a linear data structure with a “first in first out” principle. Sounds familiar right? It is similar to a stack but what is different is how information is removed. Imagine we have a list of information. When we add something to the list it gets added to the end, just Like with a stack. However, instead of removing information from the end we will remove it from the line. It is like standing in a line (or queue _hint hint_ if you are British). People enter the line at the end of it. People leave a line when they reach the front.

```
Const queue = [];           // create a new array
queue.push (‘first”)        // add 'first' to the queue
queue.push (“second”)       // add 'second' to the queue
queue.push (“third”)        // add 'third' to the queue
queue = [‘first’, ‘second’, ‘third’] // current queue
queue.shift()               // remove the first element of the queue
queue = [‘second’, ‘third’] // current queue

```

### resources

[Stacks and Queues](https://medium.com/@drewisatlas/implementing-stacks-and-queues-in-javascript-b3714dee112f)
