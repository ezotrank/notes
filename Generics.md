# Go/Generics

tags: #go 

**Approximation constraint element**

```go
type myNumber int

type Number interface {
	int8 | ~int
}

func sum[T Number](a, b T) T {
	return a + b
}
```