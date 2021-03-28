# Express

What’s the difference between `PUT` and `PATCH`?

When a client needs to replace an existing Resource entirely, they can use `PUT`. When they're doing a partial update, they can use **HTTP** `PATCH`.

Provide links to 3 services or tools that allow you to “mock” an API for development like json-server?

1. [MongoDB](https://www.mongodb.com/)
2. [Firebase](https://firebase.google.com/)
3. [AWS](https://aws.amazon.com/)

Compare and contrast Swagger and APIDoc.js 1 Which HTTP status codes should be sent with each type of (un)successful API call?

- Informational responses (100–199)
- Successful responses (200–299)
- Redirects (300–399)
- Client errors (400–499)
- Server errors (500–599)

Compare and contrast `SOAP` and `REST`?

- SOAP stands for Simple Object Access Protocol whereas REST stands for Representational State Transfer.
- SOAP is a protocol whereas REST is an architectural pattern.
- SOAP uses service interfaces to expose its functionality to client applications while REST uses Uniform Service locators to access to the components on the hardware device.
- SOAP needs more bandwidth for its usage whereas REST doesn’t need much bandwidth.
- SOAP only works with XML formats whereas REST work with plain text, XML, HTML and JSON.
- SOAP cannot make use of REST whereas REST can make use of SOAP.

## Term:

### Web Server

A web server is a software that uses **HTTP** and other protocols to respond to client requests made over the World Wide Web. The main job of a web server is to display website content through storing, processing, and delivering webpages to users

### Express

`Express` is the most popular **Node** web **framework** and is the underlying library for a number of other popular Node web frameworks.

### Routing

is the process of selecting a path for traffic in a network or between or across multiple networks. Broadly, routing is performed in many types of networks, including circuit-switched networks, such as the public switched telephone network **(PSTN)**, and computer networks, such as the Internet.

### WRRC

1. A user opens his browser, types in a URL, and presses Enter.
2. When a user presses Enter, the browser makes a request for that URL.
3. The request hits the Rails router (config/routes.rb). The router maps the URL to the correct controller and action to handle the request.
4. The action receives the request and passes it on to the view.
5. The view renders the page as HTML.
6. The controller sends the HTML back to the browser. The page loads and the user sees it.
   **In this way, the request/response cycle is a useful way to see how a Rails app’s files and folders are for and how they fit together.**
