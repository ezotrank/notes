# NATS

tags: #nats

> Effortless M:N connectivity: NATS manages addressing and discovery based on subjects and not hostname and ports. 
> Defaulting to M:N communications, which is a superset of 1:1, meaning it can do 1:1 but can also do so much more. 
> If you have a 1:1 system that is successful in development, ask how many other moving parts are required for 
> production to work around the assumption of 1:1? Things like load balancers, log systems, and network security models, 
> as well as proxies and sidecars. If your production system requires all of these things just to get around the fact 
> that the connective technology being used, e.g. HTTP or gRPC, is 1:1, it’s time to give NATS.io a look.

> The 'Core NATS' functionalities are publish/subscribe with subject-based-addressing and queuing, with 'at most once' 
> quality of service.

> The one-to-many pattern is sometimes called fan-out.

> Messages have a maximum size (which is set in the server configuration with max_payload) which is set to 1 MB by 
> default, but can be increased up to 64 MB if needed (though we recommend keeping the max message size to something 
> more reasonable like 8 MB).

> Because the NATS protocol is text-based, you can use NATS across virtually any platform or language. In the 
> following demo we use Telnet.

## Subject-Based Messaging

**What is a Subject?**

At its simplest, a subject is just a string of characters that form a name which the publisher and subscriber can use to
find each other. It helps scope messages into streams or topics.

**Matching A Single Token**

The first wildcard is * which will match a single token. For example, if an application wanted to listen for eastern 
time zones, they could subscribe to time.*.east, which would match time.us.east and time.eu.east.

**Matching Multiple Tokens**

The second wildcard is > which will match one or more tokens, and can only appear at the end of the subject. 
For example, time.us.> will match time.us.east and time.us.east.atlanta, while time.us.* would only match time.us.east 
since it can't match more than one token.

**Subject Tokens**

It is recommended to keep the maximum number of tokens in your subjects to a reasonable value of 16 tokens max.

## Pub/Sub

`nats sub msg.test`
`nats pub msg.test hello`
`nats sub msg.*`

## Request-Reply

Request-Reply is a common pattern in modern distributed systems. A request is sent and the application either waits on 
the response with a certain timeout or receives a response asynchronously.

## Queue Groups

NATS provides a built-in load balancing feature called distributed queues. Using queue subscribers will balance message 
delivery across a group of subscribers which can be used to provide application fault tolerance and scale workload 
processing.

## JetStream

**KV**

Another functionality (typically not available in or even associated with messaging systems) is the JetStream
Key/Value store: the ability to store, retrieve and delete value messages associated with a key, to watch (listen) 
for changes happening to that key and even to retrieve a history of the values (and deletions) that have happened on 
a particular key.


# Links

- [Docs](https://docs.nats.io)
- [Contrasting NATS with Apache Kafka](https://itnext.io/contrasting-nats-with-apache-kafka-1d3bdb9aa767)