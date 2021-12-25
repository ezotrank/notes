# Go Modules

## Tricks and Tips

**How to point go module dependency to a specific commit?**

`go get github.com/someone/some_module@af044c0995fe`

**How to use replace in go.mod?**

`replace golang.org/x/net v1.2.3 => example.com/fork/net v1.4.5`

**How use tools for code generation?**

```go
$ cat tools.go
// +build tools

package tools

import (
	_ "golang.org/x/tools/cmd/stringer"
)
```

**Create go.mod outise $GOPATH**

`go mod init github.com/ezotrank/playground/ko`

[link1](https://github.com/go-modules-by-example/index/blob/master/010_tools/README.md)
[link2](https://github.com/golang/go/wiki/Modules#how-can-i-track-tool-dependencies-for-a-module)

**GOPRIVATE**

`go env -w GOPRIVATE=github.com/company-name`