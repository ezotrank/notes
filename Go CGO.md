# Go/CGO

tags: #go 

CGO lets Go packages call C code.

```go
package rand

/*
#include <stdlib.h>
*/
import "C"
import "unsafe"

func Random() int {
	return int(C.random())
}

func Seed(i int) {
	C.srandom(C.uint(i))
}

func Print(s string) {
	cs := C.CString(s)
	// Go GC doesn't know about C allocations, so we must explicitly free.
	defer C.free(unsafe.Pointer(cs))
	C.fputs(cs,  (*C.FILE)(C.stdout))
}
```

