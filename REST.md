# Express REST API

1. Name 3 real world use cases where you’d want to change the request with custom middleware

- Error handling
- Authentication
- Data management

2. True or false: The route handler is middleware? false

3. In what ways can a middleware function end the process and send data to the browser?

If the current middleware function does not end the request-response cycle, it must call `next()` to pass control to the next middleware function. Otherwise, the request will be left hanging.

4. At what point in the request lifecycle can you “inject” middleware?

before the main middleware that should send the response to the client.

5. What can cause express to error with “Request headers sent twice, cannot start a second response”

The error **"Error: Can't set headers after they are sent."** means that you're already in the Body or Finished state, but some function tried to set a header or statusCode. When you see this error, try to look for anything that tries to send a header after some of the body has already been written. For example, look for callbacks that are accidentally called twice, or any error that happens after the body is sent.

Terms:

- Middleware
  a function that takes a request object and either terminates the request/response cycle or passes control to another middleware
  function.
  ![Middleware](https://cdn-images-1.medium.com/fit/t/1600/480/1*NdJKXX4mSin7D3QENE0RJw.png)

- Request Object
  Represents the information in the HTTP request from the client to the server.

- Response Object
  Information in the HTTP response from the server to the client.

- Application Middleware
  Middleware that plays a role in the function of the application.

- Routing Middleware
  Middleware that plays a role in path routing.

- TDD
  Style of programming in which three activities are tightly interwoven - coding, testing (unit tests), and design.

- Behavioral Testing
  Testing of the external behavior of the program (also known as black-box testing), usually a functional testing
