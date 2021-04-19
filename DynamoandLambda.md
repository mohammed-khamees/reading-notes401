# AWS: API, Dynamo and Lambda

1. What’s the difference between a FIFO and a standard queue?

   FIFO queues have essentially the same features as standard queues, but provide the added benefits of supporting ordering and exactly-once processing. FIFO queues provide additional features that help prevent unintentional duplicates from being sent by message producers or from being received by message consumers.

2. How can the server be assured a message was properly received?

   A Message Authentication Code (MAC) is a tag attached to a message to ensure the integrity and authenticity of the message. It is derived by applying a MAC algorithm to a message in combination with a secret key.

3. What classic design pattern is best represented by event driven programming?

   The observer pattern is a software design pattern in which an object, named the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.

4. How do you test an event driven system?

   Event-driven programming is a paradigm that is widely used in many fields. Processing is a set of programming languages and environments specialized in event-driven programming for interactive graphical applications. It provides only low-level event-handling functions, which imposes difficulty on novice programmers in programming complex behaviors. This paper proposes a method for unit-testing event-driven Processing programs. It allows writing testable Processing programs and test programs in Java. To demonstrate how it works, this paper presents case studies on testing whether mouse and key events are correctly handled.

## Term:

- Serverless Functions

  An Event-Based Serverless Compute Experience to Accelerate Your Development. $200 Free Credit. Try Popular Products Free. 25+ Products Always Free. Learn by Doing.

- Cloud Storage

  cloud storage means, you need to grasp what the cloud is. In one line, that's a resource (usually computing power or storage) that you can access remotely online either for free or for a fee.

- CDN

  A content delivery network (CDN) refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.

## Amazon API Gateway:

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, CORS support, authorization and access control, throttling, monitoring, and API version management. API Gateway has no minimum fees or startup costs. You pay for the API calls you receive and the amount of data transferred out and, with the API Gateway tiered pricing model, you can reduce your cost as your API usage scales.

## AWS DynamoDB:

Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It's a fully managed, multi-region, multi-active, durable database with built-in security, backup and restore, and in-memory caching for internet-scale applications. DynamoDB can handle more than 10 trillion requests per day and can support peaks of more than 20 million requests per second.

Many of the world's fastest growing businesses such as Lyft, Airbnb, and Redfin as well as enterprises such as Samsung, Toyota, and Capital One depend on the scale and performance of DynamoDB to support their mission-critical workloads.

Hundreds of thousands of AWS customers have chosen DynamoDB as their key-value and document database for mobile, web, gaming, ad tech, IoT, and other applications that need low-latency data access at any scale. Create a new table for your application and let DynamoDB handle the rest.

## dynamoose:

Dynamoose is a modeling tool for Amazon's DynamoDB (inspired by Mongoose).

Dynamoose is Sponsored by Dynobase Dynobase helps you accelerate your DynamoDB workflow with code generation, faster data exploration, bookmarks and more: [doc](https://dynobase.dev/)
