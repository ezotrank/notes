# Types Interservice Communication

tags: #protocol

## Request-Reply (direct call)

**Pros:**

- Simplicity.
- Obvious correlation between a request and a failure.

**Cons:**

- Retries are client's responsibility and are difficult to do for a remote client.
- Partial failures are difficult to handle.

## Persistent Queues (async call)

**Pros:**

- Separation of systems in space and time.
- Automatic retries.
- Simple when no responses are expected.


**Cons:**

- Additional dependency of the queueing technology.
- Extra work to correlate responses.
- Queues may clog.
- Special handling of "poison messages".


## Workflow (Temporal)


**Pros:**

- Partial separation of systems in time and space.
- Robust handling of partial failures.
- Support for long-running operation.
-Retries are "automatic".

**Cons:**

- Additional dependency on a workflow system or complexity of in-house implementation.
- Extra work to correlate responses.
- Special handling of "poison messages".

## Links
- [Dealing with failure](https://docs.temporal.io/blog/dealing-with-failure/)