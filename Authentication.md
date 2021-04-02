# Authentication

1. Explain what a “Singleton” is (in Computer Science terms)

   The singleton design pattern restricts the instantiation of a class to a single instance. This is done in order to provide coordinated access to a certain resource, throughout an entire software system. Through this design pattern, the singleton class ensures that it’s only instantiated once, and can provide easy access to the single instance.

2. Explain how the Singleton pattern can be used with Node modules, specifically with classes

   - Singleton instance fields don’t take up space in the global namespace
   - Singletons may be lazily initialized
   - Singletons can implement interfaces
   - Singletons can be passed as parameters
   - Singletons can have their instances swapped out (such as for testing purposes)
   - Singletons can be handled polymorphically, so there may exist multiple implementations

3. If you were tasked with building a middleware system like Express uses, what approach might you take to construct/operate it?
   create function that has access to the request object (req), the response object (res), and the next function in the application’s request-response cycle. The next function is a function in the Express router which, when invoked, executes the middleware succeeding the current middleware.

```
   var express = require('express')
   var app = express()



    var myLogger = function (req, res, next) {
    console.log('LOGGED')
    next()
    }

    app.use(myLogger)

    app.get('/', function (req, res) {
    res.send('Hello World!')
    })

    app.listen(3000)

```

## Terms:

- Router Middleware
  Router-level middleware works in the same way as application-level middleware, except it is bound to an instance of `express.Router()`.

- Dynamic Module Loading
  Mechanism by which a computer program can, at run time, load a library (or other binary) into memory, retrieve the addresses of functions and variables contained in the library, execute those functions or access those variables, and unload the library from memory.

- Singleton Pattern
  pattern restricts the instantiation of a class to a single instance. This is done in order to provide coordinated access to a certain resource, throughout an entire software system. Through this design pattern, the singleton class ensures that it’s only instantiated once, and can provide easy access to the single instance.

- CRUD -> REST Method Matches
  `GET/Read` , `DELETE/Delete`, `PUT` can map to both **Create** and **Update** depending on the existence of the URI used with the `PUT`. `POST` maps to Create. `POST` can also map to Update although it's typically used for Create. `POST` can also be a partial update so we don't need the proposed `PATCH` method.

- Mock Testing
  an approach to unit testing that lets you make assertions about how the code under test is interacting with other system modules. In mock testing, the dependencies are replaced with objects that simulate the behaviour of the real ones. The purpose of mocking is to isolate and focus on the code being tested and not on the behaviour or state of external dependencies.

## Authentication && Authorization

Authentication is the process of determining if the user is who he/she claims to
be. It involves validating their email/password.

- Authorization is the process of determining if the user has permission to perform
  a given operation.
- To hash passwords, use `bcrypt`:

```
  // Hashing passwords
  const salt = await bcrypt.genSalt(10);
  const hashed = await bcrypt.hash(‘1234’, salt);
  // Validating passwords
  const isValid = await bcrypt.compare(‘1234’, hashed);

```

- A JSON Web Token `(JWT)` is a JSON object encoded as a long string. We use
  them to identify users. It’s similar to a passport or driver’s license. It includes a
  few public properties about a user in its payload. These properties cannot be
  tampered because doing so requires re-generating the digital signature.

- When the user logs in, we generate a `JWT` on the server and return it to the
  client. We store this token on the client and send it to the server every time we
  need to call an API endpoint that is only accessible to authenticated users.

- To generate JSON Web Tokens in an Express app use jsonwebtoken package.

```
  // Generating a JWT
  const jwt = require(‘jsonwebtoken’);
  const token = jwt.sign({ \_id: user.\_id}, ‘privateKey’);

```

**more resources:**
[Securing Passwords](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html) /
[Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication) /
[OWASP auth cheatsheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) /
[bcrypt docs](https://www.npmjs.com/package/bcrypt)
