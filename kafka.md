# Kafka

tags: #kafka

## Tips and Tricks

**Compaction**

[link](https://towardsdatascience.com/log-compacted-topics-in-apache-kafka-b1aa1e4665a7)

```
kafka-topics --create --zookeeper zookeeper:2181 --topic latest-product-price --replication-factor 1 --partitions 1 --config "cleanup.policy=compact" --config "delete.retention.ms=100"  --config "segment.ms=100" --config "min.cleanable.dirty.ratio=0.01"
```

`kaf -c production topic create --compact tp.klit-fetchers-raw-data`
`kaf -c production topic set-config tp.klit-fetchers-raw-data "delete.retention.ms=2592000000"`
`kaf -c production topic set-config tp.klit-fetchers-raw-data "cleanup.policy=compact"`

## Links

- [https://medium.com/@sannidhi.s.t/dead-letter-queues-dlqs-in-kafka-afb4b6835309](https://medium.com/@sannidhi.s.t/dead-letter-queues-dlqs-in-kafka-afb4b6835309)
- [What is the best practice to retry messages from Dead letter Queue for Kafka](https://stackoverflow.com/questions/65747292/what-is-the-best-practice-to-retry-messages-from-dead-letter-queue-for-kafka)
- [Using a dead-letter queue](https://www.oreilly.com/library/view/serverless-design-patterns/9781788620642/c06c8b30-ffcb-474c-a8d8-a7e09ab6bb39.xhtml)
- [Overview of Service Bus dead-letter queues](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-dead-letter-queues)
- [How Uber builds reliable redeliveries and dead letter queues with Apache Kafka - Mingmin Chen](https://youtu.be/K4cmLrrIUUY?t=929)