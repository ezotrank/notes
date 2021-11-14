# Tips and Tricks

**Compaction**

[link](https://towardsdatascience.com/log-compacted-topics-in-apache-kafka-b1aa1e4665a7)

```
kafka-topics --create --zookeeper zookeeper:2181 --topic latest-product-price --replication-factor 1 --partitions 1 --config "cleanup.policy=compact" --config "delete.retention.ms=100"  --config "segment.ms=100" --config "min.cleanable.dirty.ratio=0.01"
```

`kaf -c production topic create --compact tp.klit-fetchers-raw-data`
`kaf -c production topic set-config tp.klit-fetchers-raw-data "delete.retention.ms=2592000000"`
`kaf -c production topic set-config tp.klit-fetchers-raw-data "cleanup.policy=compact"`