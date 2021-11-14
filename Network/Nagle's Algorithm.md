# TCP_NODELAY. Nagle's Algorithm. Delayed ACK. TCP_QUICKACK.

- Nagle's algorithm is enabled by default in all popular operating systems.
- The TCP_NODELAY socket option is disabled Nagle's algorithm.
- Used for low latency applications with many small packets.
- An empty TCP packet has a size of 40-byte.
- Delayed ACK is an algorithm for reducing congestion.
- Delayed ACK is the destination retaining the ACK segment for the value of the delayed ACK timer, about 200 - 500 ms. Delayed ACK means TCP doesn't immediately acknowledge every single received TCP segment. Several ACK responses may be combined together into a single response, reducing protocol overhead. Delayed ACK is basically a bet taken by the destination betting 200 - 500 ms, that a new packet will arrive before the delayed ACK timer expires. Though in some circumstances, the technique can cause a reduction in the application performance.
- Never us Nagle's and Delayed ACK together.
- TCP_QUICKACK is disabled Delayed ACK's.

**Nagle's algorithm**

```
IF the window size >= MSS and the available data is >= MSS
  --> send complete MSS segment now
ELSE IF there is <b>unconfirmed data still in the pipe
  --> enqueue data in the buffer **until an ACK is received**
```

**Delayed ACK algorithm**

```
IF you are ready to send an ACK:
  --> wait (usually 200ms, can be up to 500ms) for data to piggyback.
ELSE IF (the delayed_ack timer fires) OR (I get another inbound segment to ACK):
  --> send the packet
```

**Enable TCP_NODELAY cases:**
- Highly interactive applications that communicate with a central server (Citrix, networked video games, etc).
- Telnet-connected devices Applications using chatty protocols (Telnet, SSL).

**Not to enable TCP_NODELAY cases:**
- If you are dealing with non-interactive type traffic or bulk transfers such as SOAP, XMLRPC, HTTP/web traffic.

**Links:**

- [Control packet flow with TCP_NODELAY in Go](https://blog.gopheracademy.com/advent-2019/control-packetflow-tcp-nodelay/)
- [Best Practices for TCP Optimization in 2019](https://www.extrahop.com/company/blog/2016/tcp-nodelay-nagle-quickack-best-practices/)
- [The ExtraHop Nagle Counter](https://forums.extrahop.com/t/nagle-delays-explained/249)
