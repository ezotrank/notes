# WASM

tags: #wasm

## FAQ

**In which cases WASM slower that JavaScript**

When you write complex data structure in WASM memory [link](https://blog.sqreen.com/webassembly-performance/)

The cost of writing complex data structures in WASM memory is pretty high, for instance, to pass a simple string to a WASM module, you need to:

- Encode this string (for instance in UTF-16)
- Obtain a free piece of memory (equivalent to a malloc)
- Write the encoded string into it