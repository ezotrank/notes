# Tips and Tricks

**Send SIGQUIT to quit process and perform a core dump**

`kill -SIGQUIT 8518`

**Build with escape an analysis**

`go build -gcflgas="-m"`

**A function can be a type**

For instance, HandlerFunc is a function and a type, which implements http.Handler interface.

```go
type HandlerFunc func (ResponseWriter, *Request)

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

**Dump to asm**

```bash
go build -o main main.go
objdump -d main > main.asm
```

**Using interfaces for testing**

```go
type DataPersistence interface {
    SaveData(string, string) error
    GetData(string) (string, error)
}

type MockDataPersistence struct {
    SaveDataFunc func (string, string) error
    GetDataFunc func (string) (string, error)
}

func (m MockDataPersistence) SaveData(key, value string) error {
    return m.SaveDataFunc(key, value)
}

func (m MockDataPersistence) GetData(key string) (string, error) {
    return m.GetDataFunc(key)
}

func TestMyStuff(t *testing.T) {
    mockPersistor := MockDataPersistence{}
    mockPersistor.SaveDataFunc = func (key, value string) error {
        return fmt.Errorf("error to check how your code handles an error")
    }
	
    err := thingToTest(mockPersistor)
    assert.Nil(t, err)
}
```