# Go Modules

## Tricks and Tips

**How to point go module dependency to a specific commit?**

`go get github.com/someone/some_module@af044c0995fe`


**How to use replace in go.mod?**

`replace golang.org/x/net v1.2.3 => example.com/fork/net v1.4.5`

