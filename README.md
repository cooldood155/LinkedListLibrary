# LLlib — C & C++ Linked List Library

A simple, cross-platform static + shared linked-list library written in C and C++.

## Build instructions

```sh
cmake -S . -B build
cmake --build build
```
### Optionally add:
1.  Build Arch-
    - You can do this by adding the '-A' (architecture) flag to the CMake build command.
```sh
cmake -S . -B build -A x64
```

2.  Build Configuration (build/debug)
    - If you use Ninja / Unix Makefiles add the CMake build type variable to your command:
    ```sh
    cmake -S . -B  build -DCMAKE_BUILD_TYPE=Release
    cmake --build build
    ```

    - If you use Visual Studio generator or Ninja Multi-Config:
    ```sh
    cmake -S . -B build
    cmake --build build --config Release
    ```