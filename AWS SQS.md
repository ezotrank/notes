# AWS/SQS

tags: #aws #sqs

## Highlights

- Standard queues support at-least-once message delivery, and FIFO queues support exactly-once message processing.
- Enable content-based deduplication. This instructs Amazon SQS to use a SHA-256 hash to generate the message deduplication ID using the body of the message—but not the attributes of the message. For more information, see the documentation on the CreateQueue, GetQueueAttributes, and SetQueueAttributes actions in the Amazon Simple Queue Service API Reference.
-  If you retry the SendMessage action within the 5-minute deduplication interval, Amazon SQS doesn't introduce any duplicates into the queue.
- Standard queue - At-Least-Once delivery.
- FIFO queue - Exactly Once delivery.

## Links

- [What is Amazon Simple Queue Service?](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)