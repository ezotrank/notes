# Proto

## Best Practices

- (MUST) Use Google.Protobuf.WellKnownTypes.
- Use google.protobuf.Empty for empty response.
- (SHOULD) Standard Methods like ListBooks, GetBook, CreateBook, UpdateBook, DeleteBook.
- The request and response message of an RPC should be named <RPC Name>Request/Response, except if they return a single entity (e.g., Book), in which case that message should be returned or for the Empty.
- (MUST) Enum Default Value: <ENUM_NAME>_UNSPECIFIED.
- (MUST) Not use unsigned Integer Types.
- Commit and keep all our generated source code within the repository along with the definitions.

## Links

- [Best Practices for Writing Protobuf](https://dev.vseth.ethz.ch/reference/grpc-protobuf/best-practices-for-writing-protobuf)
- [https://dev.to/davidsbond/golang-structuring-repositories-with-protocol-buffers-3012](https://dev.to/davidsbond/golang-structuring-repositories-with-protocol-buffers-3012)
- [Don't Do It All Yourself: Exploiting gRPC Well Known Types in .NET Core](https://visualstudiomagazine.com/articles/2020/01/16/grpc-well-known-types.aspx)

## Tricks & Tips

**CLI to encode and decode message**

```
cat msg
user_id: "bad user tree"
email: "email"
status: USER_STATUS_UNSPECIFIED
bank_reject_reason: ""

protoc --encode=wallet.v1.User wallet.proto < msg|kaf produce wallet.users  
```