# Tips and Tricks

**Send SIGQUIT to quit process and perform a core dump**

`kill -SIGQUIT 8518`

**Build with escape an analysis**

`go build -gcflgas="-m"`

**A function can be a type**

For instance, HandlerFunc is a function and a type, which implements http.Handler interface.

```go
type HandlerFunc func(ResponseWriter, *Request)

func (f HandlerFunc) ServeHTTP(w ResponseWriter, r *Request) {
	f(w, r)
}
```

**Build a staticaly-linked binary**

`CGO_ENABLED=0 go build`

**Install the latest version of(included beta)**

```go
go install golang.org/dl/gotip@latest
gotip download
gotip version
```