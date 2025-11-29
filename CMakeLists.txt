cmake_minimum_required(VERSION 3.10)
project(lab5_1)

set(CMAKE_CXX_STANDARD 17)

add_executable(lab5_1 lab5.1.cpp)

# GoogleTest
include(FetchContent)
FetchContent_Declare(
    googletest
    URL https://github.com/google/googletest/archive/refs/tags/release-1.12.1.zip
)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(tests test.cpp)
target_link_libraries(tests gtest gtest_main)

add_test(NAME tests COMMAND tests)
