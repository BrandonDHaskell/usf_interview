# USF Coding Interview

This repo is a light C++/CMake scaffold for live coding in VS Code.

## Purpose

To write small C++ programs and compile and run them quickly while live video streaming.

## Workflow

1. Update the code in `src/main.cpp`.
1. Type `CTRL + F5` to launch the compile and run tasks in VS Code

## Quick commands

`CTRL + F5` to compile + run

```bash
cmake -S . -B build -G Ninja
cmake --build build
cmake --build build --target run
```

## Notes

### Dev Environment

| Component | Version |
|---|---|
| Operating System | Debian GNU/Linux 13 |
| IDE | Visual Studio Code |
| CMake | 4.1.2 |
| Ninja | 1.13.1 |
| GNU C++ Compiler | 14.2.0 |

