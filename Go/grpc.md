# GRPC

**Add reflection to grpc server**

```go
import "google.golang.org/grpc/reflection"

func main() {
    lis, err := net.Listen("tcp", port)
    if err != nil {
        log.Fatalf("failed to listen: %v", err)
    }
    s := grpc.NewServer()
    pb.RegisterGreeterServer(s, &server{})
    // Register reflection service on gRPC server.
    reflection.Register(s)
    if err := s.Serve(lis); err != nil {
        log.Fatalf("failed to serve: %v", err)
    }
}
```

**Special type for money**

`https://github.com/googleapis/googleapis/blob/master/google/type/money.proto`

Go package `https://pkg.go.dev/google.golang.org/genproto/googleapis/type/money`


**Install buf**

```shell
brew tap bufbuild/buf
brew install buf
```