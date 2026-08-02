# Tire pressure monitoring kata in C++

[![CI](https://github.com/Coding-Cuddles/tire-pressure-monitoring-cpp-kata/actions/workflows/main.yml/badge.svg)](https://github.com/Coding-Cuddles/tire-pressure-monitoring-cpp-kata/actions/workflows/main.yml)
[![C++17](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Replit](https://img.shields.io/badge/Try%20with%20Replit-black?logo=replit)](https://replit.com/new/github/Coding-Cuddles/tire-pressure-monitoring-cpp-kata)

## Overview

This kata complements [Clean Code: Advanced TDD, Ep. 21](https://cleancoders.com/episode/clean-code-episode-21-p1).

This repository contains two exercises designed to improve your skills in
test-driven development. It represents code you inherited from a legacy code
base.

As a first step, try to get some kind of test in place before you change the
class at all. If the tests are hard to write, is that because of the problems
with SOLID principles?

### Exercise 1

Write the unit tests for the `Alarm` class. The `Alarm` class is designed to
monitor tire pressure and set an alarm if the pressure falls outside of the
expected range.

The `Sensor` class provided for the exercise simulates the behaviour of a real
tire sensor, providing random but realistic values.

You can choose to use stubs, mocks, or none at all. If you do, you are free to
use the mocking tool that you prefer.

> **Note**
>
> If you decide to use mocks, we recommend using the
> [GMock](https://google.github.io/googletest/gmock_for_dummies.html)
> mock object library.

### Exercise 2

Use one of the mocking patterns: Self-Shunt, Test-Specific Subclass, or Humble
Object. If you used one of them already, use another one.

This is a C++17 kata using GoogleTest. Setup is complete when CTest reports
`100% tests passed`.

## Prerequisites

Required:

- [Git](https://git-scm.com/downloads)
- A compiler with C++17 support. Choose one:
  - [GCC](https://gcc.gnu.org/) 10+ on Linux
  - [LLVM Clang](https://llvm.org/) 14+ on Linux
  - [Apple Clang](https://developer.apple.com/xcode/) 17+ on macOS
  - [MSVC](https://visualstudio.microsoft.com/) 2022 on Windows
- [CMake 3.24 or later](https://cmake.org)

Optional:

- [GNU Make](https://www.gnu.org/software/make/), for shorter commands. Every
  required task also has direct CMake and CTest commands. Make may be
  unavailable on Windows.

You do not need to install GoogleTest separately. CMake finds an installed
copy or downloads the pinned release when needed.

## Set up the kata

The tracked Replit configuration is retained. The local setup below is the
validated development path.

1. Clone the repository:

   ```console
   git clone https://github.com/Coding-Cuddles/tire-pressure-monitoring-cpp-kata.git
   ```

2. Enter the repository directory:

   ```console
   cd tire-pressure-monitoring-cpp-kata
   ```

3. Build and run the tests. Use Make when it is installed:

   ```console
   make test
   ```

   Otherwise, use CMake and CTest directly:

   ```console
   cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
   cmake --build build --config Debug
   ctest --test-dir build --build-config Debug --output-on-failure
   ```

The first run may download and build GoogleTest. CTest should report
`100% tests passed`. If a command reports a missing compiler or CMake, install
that prerequisite and run the setup commands again. Setup is complete when
CTest reports `100% tests passed`.

## Work on the kata

Add one test at a time to `test_alarm.cpp`, then change `alarm.h` and
`sensor.h` as required by the exercises above.

After each change, use Make when it is installed:

```console
make test
```

Otherwise, use CMake and CTest directly:

```console
cmake --build build --config Debug
ctest --test-dir build --build-config Debug --output-on-failure
```

Continue when CTest reports `100% tests passed`.

## Run the example

Use Make when it is installed:

```console
make run
```

Otherwise, use the CMake run target:

```console
cmake --build build --config Debug --target run
```

The executable prints `Hello World!`.

## Make command reference

Make is optional. Run `make` or `make help` to list these commands in the
terminal.

| Command             | Result                                    |
| ------------------- | ----------------------------------------- |
| `make all`          | Build and run the test suite              |
| `make help`         | List public Make targets                  |
| `make build`        | Configure and build without running tests |
| `make run`          | Build and run the example executable      |
| `make test`         | Build and run the test suite              |
| `make format`       | Format tracked C++ and header files       |
| `make format-check` | Check formatting without changing files   |
| `make clean`        | Remove generated build artifacts          |

## Credits and references

* <https://github.com/emilybache/Racing-Car-Katas/tree/main/Cpp/TirePressureMonitoringSystem>
