# Alignments and paddings

For x86-32 machine word length is 4 bytes and for x86-64 is 8 bytes.
In Go required alignment is equal to the size of the memory required for the largest field in the structure but not more than machine word bytes.

**Examples:**

```
// Sizeoff is 2 bytes.
type Foo struct {
    aaa bool    // 1 byte
	bbb bool    // 1 byte
}

```

```
// Sizeof is 12 bytes.
type Foo struct {
	aaa bool   // 1 byte, but with padding - 4.
	bbb int32  // 4 bytes.
	ccc bool   // 1 byte, but with padding - 4.
}
```

```
// Sizeoff is 8 bytes.
type Foo struct {
	bbb int32  // 4 bytes.
	aaa bool   // 1 byte.
	ccc bool   // 1 byte, but with padding - 2.
}
```

```
// Sizeoff is 8 bytes.
type Foo struct {
	aaa int32     // 4 bytes
	_   struct{}  // 0 bytes, but with padding - 4.
}
```

```
// Sizeoff is 24 bytes.
type Foo struct {
	aaa complex128 // 16 bytes
	bbb bool       // 1 byte, but with padding - 8.
}

```

Check size of structure `unsafe.Sizeof(Foo)`

**Purpose of memory alignment**

- Speed
  The CPU always reads at its word size (4 bytes on a 32-bit processor), so when you do an unaligned address access — on a processor that supports it — the processor is going to read multiple words. 

- Range
  -

- Atomicity
  The CPU can operate on an aligned word of memory atomically, meaning that no other instruction can interrupt that operation.

- Caches
  Another alignment-for-performance that I alluded to previously is alignment on cache lines which are (for example, on some CPUs) 64B.

Links:

- [Padding is hard](https://dave.cheney.net/2015/10/09/padding-is-hard)
- [Structure size optimization in Golang (alignment/padding). More effective memory layout (linters).](https://itnext.io/structure-size-optimization-in-golang-alignment-padding-more-effective-memory-layout-linters-fffdcba27c61)
- [fieldalignment linter](https://pkg.go.dev/golang.org/x/tools/go/analysis/passes/fieldalignment)
- [Purpose of memory alignment](https://stackoverflow.com/questions/381244/purpose-of-memory-alignment)
