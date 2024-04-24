# Reflection
## Questions
*What is AMQP?* The Advanced Message Queuing Protocol (AMQP) is an open standard for passing messages between applications or organizations with a lot of flexibility in terms of message routing, reliability, and security.

*Understanding `amqp://guest:guest@localhost:5672:`*
- `guest:guest` represents the default username and password.
- `localhost:5672` is the network address and port where the AMQP server (like RabbitMQ) listens by default.
## Message Broker dengan RabbitMQ
### Simulation slow subscriber.
<img src="image/image0.png">

In the image above, I made the subscriber slow in receiving or processing data from the message broker by adding a 1-second delay to each process. As a result, the number of queued messages at the message broker increased as the delay lengthened because the publisher was sending data faster than the subscriber was receiving it. In my case, the number of queued messages at the message broker was 6 after running the Publisher twice.