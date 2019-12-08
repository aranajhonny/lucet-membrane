produce qjs.so build qjs.wasm with docker env

```
  source devenv_setenv.sh
```

and

```
  lucetc-wasi qjs.wasm -o qjs.so
```

to reduce file size of mmap

./target/debug/lucet-wasi qjs.so --heap-address-space="2 MiB" --max-heap-size="1 MiB"

or specific limits with

```
  let limits = Limits {
    heap_memory_size,
    heap_address_space_size,
    stack_size,
    globals_size: 0,  //calculated from module
  };
```

