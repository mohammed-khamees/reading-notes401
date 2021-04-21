# AWS: Events

1. What’s the difference between a FIFO and a standard queue?

   FIFO queues have essentially the same features as standard queues, but provide the added benefits of supporting ordering and exactly-once processing. FIFO queues provide additional features that help prevent unintentional duplicates from being sent by message producers or from being received by message consumers.

2. How can the server be assured a message was properly received?

   A Message Authentication Code (MAC) is a tag attached to a message to ensure the integrity and authenticity of the message. It is derived by applying a MAC algorithm to a message in combination with a secret key.

3. What classic design pattern is best represented by event driven programming?

   The observer pattern is a software design pattern in which an object, named the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.

4. How do you test an event driven system?

   Event-driven programming is a paradigm that is widely used in many fields. Processing is a set of programming languages and environments specialized in event-driven programming for interactive graphical applications. It provides only low-level event-handling functions, which imposes difficulty on novice programmers in programming complex behaviors. This paper proposes a method for unit-testing event-driven Processing programs. It allows writing testable Processing programs and test programs in Java. To demonstrate how it works, this paper presents case studies on testing whether mouse and key events are correctly handled.

## Term:

- Serverless API

  a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers

- Triggers

  an AWS Lambda resource or resource in another service that you configure to invoke your function in response to lifecycle events, external requests or on a schedule, a function can have multiple triggers

- Dynamo vs Mongo

  a visual programming tool used to define relationships and create algorithms that then can be used to generate geometry in 3D space and to process data. MongoDB is a source-available cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with optional schemas.

- Dynamoose vs Mongoose

  Dynamoose is a DynamoDB API structured like Mongoose, lets us provide a schema and perform CRUD operations against a DynamoDB table, installed via node and configured based on role

## SQS and SNS Basics

Amazon SQS (Amazon Simple Queue Service) is a pay-per-use web service that stores messages in transit between computers. SQS allows developers to create distributed systems with decoupled modules without the overhead of building and managing message queues.

Amazon SNS (Amazon Simple Notification Service) is a regulated service that delivers messages from publishers to subscribers (also known as producers and consumers). Publishers communicate with subscribers asynchronously by sending messages to a subject, which serves as a logical access point and contact channel for subscribers. Clients will subscribe to the SNS topic and accept published messages via any enabled endpoint, including Amazon Kinesis Data Firehose, Amazon SQS, AWS Lambda, HTTP, twitter, smartphone push alerts, and mobile text messages (SMS).
