# Queue

## Semantics

**At-most once**

As the name suggests, At-most-once means the message will be delivered at-most once. Once delivered, 
there is no chance of delivering again. If the consumer is unable to handle the message due to some exception, 
the message is lost. This is because Kafka is automatically committing the last offset used.

**At-least once**

At-least once as the name suggests, message will be delivered atleast once. There is high chance that message will be 
delivered again as duplicate.

**Exactly once**

Exactly-once as the name suggests, there will be only one and once message delivery. It difficult to achieve in practice.