# Go/Style Guide

tags: #go  #style-guide

**Errors** 

Fixed error variables, usually named _Err_…

```go
var (
    ErrSomethingBad = errors.New("some string")
    ErrKindFoo      = errors.New("foo happened")
)
```

Error types, usually named …_Error_
```go
type SomeError struct {
    ExtraInfo int
}
func (e SomeError) Error() string { /* … */ }
```
