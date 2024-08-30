# CMake Custom Commands

This file shows how to write custom `make` commands, such as `make run` and what not.

Below is the CMakeLists.txt that we are working with.

```cmake
cmake_minimum_required(VERSION 3.10)

set(PROJECT_NAME TestProject)
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SRC_FILES ${PROJECT_SOURCE_DIR}/src/main.cpp)
```

## Adding Custom Target

To add a custom target, such as `make run` we will be using the
function from CMake called `add_custom_target()`; what this 
function does is creates a custom target, with whatever name 
we chose to give it. A custom target is a target that is not 
associated with building a specific output file, but instead,
it's used to run a set of commands. Let's see an example.

```cmake
add_custom_target(
    run                                 # command name
    COMMAND ${PROJECT_NAME}             #./main
    DEPENDS ${PROJECT_NAME}             # dependencies of project.
    WORKING_DIRECTORY ${CMAKE_PROJECT_DIR}
    COMMENT "Running ${PROJECT_NAME}..."
)
```

## Adding Another Custom Target

Now, let's say you want a test file, but this test file has
it's own main file and needs to be ran separate from the main 
application. This is where we will show you how to add another 
custom target that is different from the `${PROJECT}`s.

```cmake
# include source files.
set(TEST_SRC_FILES ${PROJECT_SOURCE_DIR}/test/test_main.cpp)

# add the executable.
add_executable(TestMain, ${TEST_SRC_FILES})

add_target(
    make test
    COMMAND TestMain # don't need $ because
                     # this is a target, not a cmake variable.
    DEPENDS TestMain
    WORKING_DIRECTORY ${CMAKE_PROJECT_DIR}
    COMMENT "Running tests..."
)
```