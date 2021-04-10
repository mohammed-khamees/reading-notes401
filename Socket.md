# Socket.io

1. What is the benefit of transforming data into packets?

   Packet switching is used to optimize the use of the channel capacity available in digital telecommunication networks, such as computer networks, and minimize the transmission latency (the time it takes for data to pass across the network), and to increase robustness of communication.

2. UDP is often refereed to as a connectionless protocol. Why is this?

   No connection needs to be established between the source and destination before you transmit data.

3. Can a socket server application have multiple socket connections?

   A server socket listens on a single port. All established client connections on that server are associated with that same listening port on the server side of the connection. An established connection is uniquely identified by the combination of client-side and server-side IP/Port pairs. Multiple connections on the same server can share the same server-side IP/Port pair as long as they are associated with different client-side IP/Port pairs, and the server would be able to handle as many clients as available system resources allow it to.

4. Can a socket connection application be connected to multiple socket servers?

   A port of a server can be used by many clients (connections). A port of a client can be used by a single connection. The reason is a port can be used by a single process, which allocates the port (doing "bind" as a server that will listen to that port for incoming connections, or doing a sort of "open" as a client wanting to do outbound connections from that port out). Sometimes the notions of "server socket" and "client socket" are used for these, and in fact the Java ServerSocket creates a connection specific socket for each accepted inbound connection, which will represent a file descriptor on its own.

5. Can an application be both a socket server and a socket connection?
   it is possible, and not unusual, to process both input and output streams of a socket on the same thread and supporting a single connection at a time allows the Runnable requirement to be dropped, i.e. no additional thread is needed for the handler and the ServerSocket accept call is postponed until the current connection is closed.

## Term:

- Observer Pattern

  Observer pattern is used when there is one-to-many relationship between objects such as if one object is modified, its depenedent objects are to be notified automatically. Observer pattern falls under behavioral pattern category.

- Listener

  Events are messages that are sent from one object to another. The component sending the event (aka firing the event) is the producer, the component receiving the event (aka handling the event) is the consumer. The producer of an event should have the ability to add and delete listeners for the events produced by itself.

- Event Handler

  Events are actions or occurrences that happen in the system you are programming, which the system tells you about so you can respond to them in some way if desired. For example, if the user selects a button on a webpage, you might want to respond to that action by displaying an information box. In this article, we discuss some important concepts surrounding events, and look at how they work in browsers. This won't be an exhaustive study; just what you need to know at this stage.

- Event Driven Programming

  Node.js uses events heavily and it is also one of the reasons why Node.js is pretty fast compared to other similar technologies. As soon as Node starts its server, it simply initiates its variables, declares functions and then simply waits for the event to occur.

- Event Loop

  The event loop is what allows Node. js to perform non-blocking I/O operations — despite the fact that JavaScript is single-threaded — by offloading operations to the system kernel whenever possible. Since most modern kernels are multi-threaded, they can handle multiple operations executing in the background.

- Event Queue

  The event queue is built into the operating environment that hosts the Javascript interpreter. It isn't fundamental to Javascript itself so it's not part of the actual JS runtime. One interesting indicator of this is that `setTimeout()` is not actually part of ECMAScript, but rather something made available to the Javascript environment by the host.

- Call Stack

  A call stack is many times referred to as "the stack". It stores data about procedures that are currently running in a given program.

- Emit/Raise/Trigger

  Event emitters are objects in Node.js that trigger an event by sending a message to signal that an action was completed. JavaScript developers can write code that listens to events from an event emitter, allowing them to execute functions every time those events are triggered. In this context, events are composed of an identifying string and any data that needs to be passed to the listeners.

- Subscribe

  Subscribe-event is the easiest way to subscribe either dom events in browser or node.js events.

- database

  A database is a collection of information that is organized so that it can be easily accessed, managed and updated. Computer databases typically contain aggregations of data records or files, containing information about sales transactions or interactions with specific customers.

**Socket.IO**

Socket.IO is a JavaScript library for realtime web applications. It enables realtime, bi-directional communication between web clients and servers. It has two parts: a client-side library that runs in the browser, and a server-side library for Node.js. Both components have a nearly identical API. Like Node.js, it is event-driven.

Socket.IO handles the connection transparently. It will automatically upgrade to WebSocket if possible. This requires the programmer to only have Socket.IO knowledge.

Socket.IO is not a WebSocket library with fallback options to other realtime protocols. It is a custom realtime transport protocol implementation on top of other realtime protocols. A Socket.IO implementing server cannot connect to a non-Socket.IO WebSocket client. A Socket.IO implementing client cannot talk to a non-Socket.IO WebSocket or Long Polling Comet server. Socket.IO requires using the Socket.IO libraries on both client and server side.

![Socket](https://images.ctfassets.net/ee3ypdtck0rk/1Lj7lbqX54WCiHI2uVVL3x/e145c3b8194f84b5c1219e6dd3dcb9da/introduction-d4b7a9009c7a7a0306c050af52a4f8be8ddebbece4882ad8128c752da505f8b9.png)

A popular way to demonstrate the two-way communication Socket.IO provides is a basic chat app (we talk about some other use cases below). With sockets, when the server receives a new message it will send it to the client and notify them, bypassing the need to send requests between client and server. A simple chat application shows how this works.

![socket](https://images.ctfassets.net/ee3ypdtck0rk/27G4lHu2Vj0Cm0CUC2x5p7/dc6ec5c252beb97314293937f70ea0d0/chat-2560521f9fe468d126d0e2cad7ee32073fa95a6b59374c3a1700fa41b85df2e2.png)

**Example – Socket.IO for chat**

Server
You will need to have node.js installed. We will be using express to simplify setup.

Create a new folder with:

```
$ mkdir socket.io-example
cd socket.io-example
npm install socket.io express

```

Setup server and import required packages.

```
const app = require("express")();
const http = require("http").createServer(app);
const io = require("socket.io")(http);

```

The server root will send our index.html which we will setup shortly.

```
app.get("/", (req, res) => res.sendFile(\_\_dirname + "/index.html"));

```

Here is where we setup Socket.IO. It is listening for a ‘connection’ event and will run the provided function anytime this happens.

```
io.on("connection", function(socket) {
console.log(“socket connected”);
});

```

This will setup the server to listen on port 3000.

```
http.listen(3000, () => console.log("listening on http://localhost:3000")

```

Run the application with node index.js and open the page in your browser.
