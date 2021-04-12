# Message Queues

1. What does it mean that web sockets are bidirectional? Why is this useful?

   enables the server to send real-time updates asynchronously, without requiring the client to submit a request each time.

2. Does socket.io use HTTP? Why?

   The premise on which your question seems to be based is that socket.io is a websocket library, which it isn't. ... Even when websockets can be used, the initial connection setup it done over HTTP. Also, a socket.io server will attach to an HTTP server so it can serve its own client code through /socket.io/socket.io.js .

3. What happens when a client emits an event?

   The event gets passed to the server through websockets. Its a tcp connection from the browser to the server. The connection is full duplex meaning the server can send real time data to the client and vise versa.

4. What happens when a server emits an event?

   This code asks the server for a tcp connection using web sockets. Once the browser is connected to the server through websockets, socket.io can send events to the send through the connection.

5. What happens if a client “misses” an event?

   The issue you are experiencing seems consistent with a message buffer overflow. When SignalR releases messages from its buffer, it does so in 250 message fragments by default.

6. How can we mitigate this?

   - Track risks before they escalate, becoming issues that derail a development project
   - Address the riskiest parts of the development process first
   - Tackle risks immediately by using an Agile development approach
   - Create plans for potential risks at the beginning of the project, and share all risks with clients to be transparent
   - Track development and client team temperature metrics along with project timeline, budget, and scope
   - Encourage open communication and feedback throughout the development process to maintain team morale

# Terms:

- Socket

  one endpoint of a two-way communication link between two programs running on the network. A socket is bound to a port number so that the TCP layer can identify the application that data is destined to be sent to. An endpoint is a combination of an IP address and a port number.

- Web Socket

  A communication Protocol which provides bidirectional communication between the Client and the Server over a TCP connection, WebSocket remains open all the time so they allow the real-time data transfer. When clients trigger the request to the Server it does not close the connection on receiving the response, it rather persists and waits for Client or server to terminate the request.

- Socket.io
  It is a library which enables real-time and full duplex communication between the Client and the Web servers. It uses the WebSocket protocol to provide the interface. Generally, it is divided into two parts, each of which use WebSockets, but also provide additional functionality such as broadcasting, namespacing, and other means of segmenting connected clients into groups.

- Client

  Client Side: it is the library that runs inside the browser or a "satellite" server that connects to a "hub"

- Server

  Server Side: It is the library for Node.js that serves as "hub" or "traffic cop"

- OSI Model

  (Open Systems Interconnection Model) is a conceptual framework used to describe the functions of a networking system. The OSI model characterizes computing functions into a universal set of rules and requirements in order to support interoperability between different products and software.

- TCP Model

  The TCP/IP model was developed prior to the OSI model. The TCP/IP model is not exactly similar to the OSI model. The TCP/IP model consists of five layers: the application layer, transport layer, network layer, data link layer and physical layer.

- TCP

  The Transmission Control Protocol (TCP) is widely used by application layer protocols in the Internet Protocol Suite. TCP creates a two way communication between two hosts and provides reliable, ordered, and error checked byte streams between the applications. TCP data transfers manage network congestion and use flow control to limit the rate a sender transfers data to guarantee reliable delivery. Each IP packet between the hosts carries a single TCP Segment. A TCP segment is made up of header and data sections.

- UDP

  (User Datagram Protocol) is a communications protocol that is primarily used for establishing low-latency and loss-tolerating connections between applications on the internet. It speeds up transmissions by enabling the transfer of data before an agreement is provided by the receiving party.

- Packets

  a small amount of data sent over a network, such as a LAN or the Internet. Similar to a real-life package, each packet includes a source and destination as well as the content (or data) being transferred.

**Rooms**
A room is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients:

![room](https://socket.io/images/rooms.png)

**Namespaces**
A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called “multiplexing”).

![Namespaces](https://socket.io/images/rooms.png)

**Emit cheatsheet**
Server-side:

```
io.on("connection", (socket) => {

// basic emit
socket.emit(/_ ... _/);

// to all clients in the current namespace except the sender
socket.broadcast.emit(/_ ... _/);

// to all clients in room1 except the sender
socket.to("room1").emit(/_ ... _/);

// to all clients in room1 and/or room2 except the sender
socket.to("room1").to("room2").emit(/_ ... _/);

// to all clients in room1
io.in("room1").emit(/_ ... _/);

// to all clients in namespace "myNamespace"
io.of("myNamespace").emit(/_ ... _/);

// to all clients in room1 in namespace "myNamespace"
io.of("myNamespace").to("room1").emit(/_ ... _/);

// to individual socketid (private message)
io.to(socketId).emit(/_ ... _/);

// to all clients on this node (when using multiple nodes)
io.local.emit(/_ ... _/);

// to all connected clients
io.emit(/_ ... _/);

// WARNING: `socket.to(socket.id).emit()` will NOT work, as it will send to everyone in the room
// named `socket.id` but the sender. Please use the classic `socket.emit()` instead.

// with acknowledgement
socket.emit("question", (answer) => {
// ...
});

// without compression
socket.compress(false).emit(/_ ... _/);

// a message that might be dropped if the low-level transport is not writable
socket.volatile.emit(/_ ... _/);

});

```

**Client-side**

```
// basic emit
socket.emit(/_ ... _/);

// with acknowledgement
socket.emit("question", (answer) => {
// ...
});

// without compression
socket.compress(false).emit(/_ ... _/);

// a message that might be dropped if the low-level transport is not writable
socket.volatile.emit(/_ ... _/);
```
