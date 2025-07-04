## Where do they fit in?

Lets say there are 2 machines - App A and App B, and they need to communicate with each other. The most direct way is to establish direct connection between the 2 machines but this might not be feasible every time.

There are various cases where they can't communicate such as:

1. Application B might not be running when A tries to reach out.
2. The network might be slow.
3. There might be other networks or firewalls in between, thus a network path might be absent.
4. They might not be written-in or speaking the same language.

### Message Brokers are Intermediaries
Message brokers is the solution. 

A message broker often sits like a proxy between two machines. App A sends the message to this Message broker and then the broker forwards the message to App B when it becomes available.

Now lets understand case by case:

### App B is down

If App B is down, it won't result in message being lost. The message broker has storage and can store all the messages that it receives.
When App B comes back online, it can connect to the broker and receive the messages. This allows reliability to the communication.

### If the network is slow

As the Broker has storage, thus App B being slow is almost the same as the above scenario where the App is unavailable. The message broker stores the messages it receives from App A in such cases.

This also supports the case where App B is busy and can't handle messages as fast as they're being sent.

### What if there are firewalls

When setting up the message broker, we can actually provide a domain name for the broker or an IP address and place it in such a way that it is accessible by both the machines - either in a shared VPC, or via an SSH tunnel, or make the broker public so that both services can handle it.

Once the application is connected to the message broker, they can talk to all the other machines talking to the message broker.

### If they don't speak the same language

