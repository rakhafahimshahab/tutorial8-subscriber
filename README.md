# Reflection
## Questions
*What is AMQP?* The Advanced Message Queuing Protocol (AMQP) is an open standard for passing messages between applications or organizations with a lot of flexibility in terms of message routing, reliability, and security.

*Understanding `amqp://guest:guest@localhost:5672:`*
- `guest:guest` represents the default username and password.
- `localhost:5672` is the network address and port where the AMQP server (like RabbitMQ) listens by default.
## Message Broker with RabbitMQ
### Simulation slow subscriber.
<img src="image/image0.png">

In the image above, I made the subscriber slow in receiving or processing data from the message broker by adding a 1-second delay to each process. As a result, the number of queued messages at the message broker increased as the delay lengthened because the publisher was sending data faster than the subscriber was receiving it. In my case, the number of queued messages at the message broker was 6 after running the Publisher twice.
### One publisher and three subscribers.
<img src="image/image1.png">

<img src="image/image2.png">

I did the same as in the "Simulation slow subscriber" section. If we run more than one subscriber, the data transmission is much faster, and in my case, it appeared that nothing was added to the queued messages at the message broker. This happens because the message broker distributes the data received from the Publisher to all connected subscribers.

Without changing the program's code, we can achieve different outcomes by altering the message broker's configuration or the number of running subscribers. This is what is referred to as event-driven.