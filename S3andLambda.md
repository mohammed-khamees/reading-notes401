# AWS: S3 and Lambda

1. What’s the difference between a FIFO and a standard queue?

   FIFO queues have essentially the same features as standard queues, but provide the added benefits of supporting ordering and exactly-once processing. FIFO queues provide additional features that help prevent unintentional duplicates from being sent by message producers or from being received by message consumers.

2. How can the server be assured a message was properly received?

   A Message Authentication Code (MAC) is a tag attached to a message to ensure the integrity and authenticity of the message. It is derived by applying a MAC algorithm to a message in combination with a secret key.

3. What classic design pattern is best represented by event driven programming?

   The observer pattern is a software design pattern in which an object, named the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.

4. How do you test an event driven system?

   Event-driven programming is a paradigm that is widely used in many fields. Processing is a set of programming languages and environments specialized in event-driven programming for interactive graphical applications. It provides only low-level event-handling functions, which imposes difficulty on novice programmers in programming complex behaviors. This paper proposes a method for unit-testing event-driven Processing programs. It allows writing testable Processing programs and test programs in Java. To demonstrate how it works, this paper presents case studies on testing whether mouse and key events are correctly handled.

## Terms:

- Server Instances

  A server instance is a collection of SQL Server databases which are run by a solitary SQL Server service or instance. The details of each server instance can be viewed on the service console which can be web-based or command-line based.

- Containers

  The application container technology provided by Docker promises to change the way that IT operations are carried out just as virtualization technology did a few years previously.

- Cloud Services

  services available via a remote cloud computing server rather than an on-site server. These scalable solutions are managed by a third party and provide users with access to computing services such as analytics or networking via the internet.

- Cloud Architecture

  Cloud Architecture refers to the various components in terms of databases, software capabilities, applications, etc. engineered to leverage the power of cloud resources to solve business problems. Cloud architecture defines the components as well as the relationships between them.

- AWS

  Amazon Web Services offers reliable, scalable, and inexpensive cloud computing services. Free to join, pay only for what you use.

- EC2/Beanstalk vs Heroku

  If we search for a comparison of Heroku and AWS, we’ll see a bunch of articles that juxtapose AWS Elastic Compute Cloud (EC2) with Heroku. But is the Heroku vs AWS Elastic Beanstalk comparison reasonable? Comparing these two products isn’t very logical for several reasons, as we’ll explain shortly. We'll also mention what are the advantages and disadvatanges of one hosting provider vs another.

### AWS S3

mazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. This means customers of all sizes and industries can use it to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics. Amazon S3 provides easy-to-use management features so you can organize your data and configure finely-tuned access controls to meet your specific business, organizational, and compliance requirements. Amazon S3 is designed for 99.999999999% (11 9's) of durability, and stores data for millions of applications for companies all around the world.

### AWS Lambda Basics

AWS Lambda is a service which computes the code without any server. It is said to be serverless compute. The code is executed based on the response of events in AWS services such as adding/removing files in S3 bucket, updating Amazon DynamoDB tables, HTTP request from Amazon API Gateway etc.

### AWS Lambda Functions

AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers, creating workload-aware cluster scaling logic, maintaining event integrations, or managing runtimes. With Lambda, you can run code for virtually any type of application or backend service - all with zero administration. Just upload your code as a ZIP file or container image, and Lambda automatically and precisely allocates compute execution power and runs your code based on the incoming request or event, for any scale of traffic. You can set up your code to automatically trigger from 140 AWS services or call it directly from any web or mobile app. You can write Lambda functions in your favorite language (Node.js, Python, Go, Java, and more) and use both serverless and container tools, such as AWS SAM or Docker CLI, to build, test, and deploy your functions.
