# buf.build

**Remote generating proto files**

```yaml
version: v1
managed:
  enabled: true
  go_package_prefix:
    default: github.com/ezotrank/playground/saga-choreography/bank/proto/gen/go

plugins:
  - remote: buf.build/protocolbuffers/plugins/go:v1.27.1-1
    out: gen/go
    opt:
      - paths=source_relative
  - remote: buf.build/grpc/plugins/go:v1.2.0-1
    out: gen/go
    opt:
      - paths=source_relative
      - require_unimplemented_servers=false
```