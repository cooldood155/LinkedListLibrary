# LLlib — C & C++ Linked List Library

A simple, cross-platform static + shared linked-list library written in C and C++.

## Build instructions

```sh
cmake -S . -B build
cmake --build build
```
### Optionally add:
1.  Build Type-
    - You can do this by adding the '-A' flag to the CMake build command.
```sh
cmake -S . -B build -A x64
```