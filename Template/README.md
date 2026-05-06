# Template

A ready-to-copy starting point for each new exercise in this repo.

## How to use

1. **Copy this directory** into a new folder named after your exercise, e.g.:

   ```bash
   cp -r Template/ Exercise01_HelloOpenGL/
   ```

2. **Enter your new directory** and start coding:

   ```bash
   cd Exercise01_HelloOpenGL/
   ```

3. **Build and run** with a single command (Zig 0.16+):

   ```bash
   zig build run
   ```

## Directory layout

```
Template/
├── build.zig          # Build system – no changes needed for most exercises
└── src/
    ├── main.zig       # Zig entry point; add your Zig logic here
    ├── c/
    │   └── greetFromC.c      # Drop any *.c files here; auto-compiled with -std=c23
    └── cpp/
        └── greetFromCpp.cpp  # Drop any *.cpp files here; auto-compiled with -std=c++23
```

## Adding new source files

| Language | Where to put it          | Automatically picked up? |
|----------|--------------------------|--------------------------|
| Zig      | `src/` (edit `main.zig`) | Yes, via `root_source_file` |
| C        | `src/c/` (any depth)     | Yes – `build.zig` walks the tree |
| C++      | `src/cpp/` (any depth)   | Yes – `build.zig` walks the tree |

To call a new C/C++ function from Zig, declare it in `main.zig` with
`extern fn myFunction() void;`. For C++ functions, wrap the definition in
`extern "C"` to prevent name-mangling.

## Requirements

- [Zig](https://ziglang.org/download/) **0.16 or newer**

No separate C or C++ toolchain is required — Zig provides everything.
