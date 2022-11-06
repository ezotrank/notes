# Code Snippets

tags: #go #leetcode

Convert a slice of integers that contains only 1 and 0 to int.

```go
func convert(vals []int) int {
	val := 0
	for i := 0; i < len(vals); i++ {
		val = val<<1 | vals[i]
	}
	return val
}
```