# Event Driven Applications

1. Why is access control important?

   Access control is important because it is a valuable security technique that can be used to regulate who or what can view or use any given resource.

2. Describe an application that would need access control.

   In an I.T security setting this could translate to who can access and edit a particular file, what kinds of equipment can be used or who can access certain devices.

3. What is a role used for?

   Role Manager is an enterprise role management system that provides role lifecycle management capabilities to facilitate the management of business and organizational relationships, roles, and privileges.

4. Why is role based access control more scalable than discretionary or mandatory access control?

   An organization assigns a role-based access control role to every employee; the role determines which permissions the system grants to the user. For example, you can designate whether a user is an administrator, a specialist, or an end-user, and limit access to specific resources or tasks. An organization may let some individuals create or modify files while providing others with viewing permission only.

## Term:

- Authorization:

  Authorization is a security mechanism to determine access levels or user/client privileges related to system resources including files, services, computer programs, data and application features. This is the process of granting or denying access to a network resource which allows the user access to various resources based on the user's identity.

- Role Based Access Control

  Role-based access control (RBAC) is a policy-neutral access-control mechanism defined around roles and privileges. The components of RBAC such as role-permissions, user-role and role-role relationships make it simple to perform user assignments. A study by NIST has demonstrated that RBAC addresses many needs of commercial and government organizations.[5] RBAC can be used to facilitate administration of security in large organizations with hundreds of users and thousands of permissions. Although RBAC is different from MAC and DAC access control frameworks, it can enforce these policies without any complication.

- Capabilities

  what every role can do in the website

### Event-Driven Programming in Node.js:

Event-Driven Programming is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision. In this article we’re going to go over how Event-Driven Programming works and how we can make the best use of it in our Node.js projects.

Most developers are introduced to concepts of Event-Driven Programming early on in their study of programming yet they might not fully realize it until a bit later. You’ll find that the concept is rather ubiquitous. Check any major framework or software out there and odds are you’ll find evidence of Event-Driven Programming.

- Event-Driven Programming makes use of the following concepts:
  - An Event Handler is a callback function that will be called when an event is triggered.
  - A Main Loop listens for event triggers and calls the associated event handler for that event.

```
// Import events module
var events = require('events');

// Create an eventEmitter object
var eventEmitter = new events.EventEmitter();

// Bind event and event  handler as follows
eventEmitter.on('eventName', eventHandler);

// Fire an event
eventEmitter.emit('eventName');

```

![event-driven application](https://www.tutorialspoint.com/nodejs/images/event_loop.jpg)

**more resources:**
[Event Driven Programming](https://www.digitalocean.com/community/tutorials/nodejs-event-driven-programming)
[Node docs: events](https://nodejs.org/api/events.html)
