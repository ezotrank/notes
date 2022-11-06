# UUID

tags: #uuid

**Version Differences**

- UUID v1 and v2 contain MAC addresses based on the host that generates them. This isn't really a security issue since 
  an L2 address won't help you much on the public internet. However, it does mean if my UUIDs are generated in Lambdas, 
  the MAC addresses have no semantic value. I can't SSH into my Lambda and look up the MAC or otherwise use that 
  information.
- UUID v3 requires a seed, and I would just be using random.randint() or the equivalent to pick my seed value. Any 
  system that requires a seed means that I have to think about what to use as a seed, how that impacts the randomness, 
  and how that might impact security or collisions.
- UUID v4 is random, but because it is entirely random, it provides no semantic overloading.


## ULID

The ULID, which stands for "Universally unique Lexicographically sortable IDentifier", is an alternative to the UUID. 

Links:
- [ULID](https://wiki.tcl-lang.org/page/ULID)
- [Leveraging ULIDs to create order in unordered datastores](https://www.trek10.com/blog/leveraging-ulids-to-create-order-in-unordered-datastores)
- [Golang ULID package](https://github.com/oklog/ulid)