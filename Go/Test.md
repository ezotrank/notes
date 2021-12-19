# Test

**Stub time.Now()**

```go
package example

var now = time.Now

func calcExpire(d time.Duration) time.Time {
    return now() + d
}
```

```go
package example

func TestExpire(t *testing.T) {
	oldnow = now
	defer func() { now = oldnow }()
    now = func() time.Time {
        return time.Date(2019, time.January, 1, 0, 0, 0, 0, time.UTC)
    }
    ...
}
```
