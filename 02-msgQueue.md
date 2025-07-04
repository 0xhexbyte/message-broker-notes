## Message Queues

The basic communication structure we use in Message Broker is that of a Message Queue.

Queues are based on First In First Out concept.

So, if a msg 1 is sent to the queue, followed by msg 2 then it will deliver msg 1 first and then msg 2. Since msg 1 arrived first, it will be allowed first-out of the queue, followed by msg 2.

## Names

Message Brokers aren't just one queue, they can contain multiple queues.

We can give our different queues, their own unique name.

We can allow multiple applications to send a queue, they simply need to know the name of the queue.

So, a Message Broker can have multiple parallel queues where each queue is connecting 2 applications uniquely.