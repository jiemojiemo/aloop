cmake_minimum_required(VERSION 3.10.0)

project(ALoop)

option(ALOOP_BUILD_TESTS "Build tests" ON)
option(ALOOP_BUILD_EXAMPLE "Build example" ON)

add_library(aloop src/aloop.cpp)
target_include_directories(aloop PUBLIC src)
target_compile_features(aloop PUBLIC cxx_std_11)

if(ALOOP_BUILD_EXAMPLE)
    add_subdirectory(example)
endif ()

if (CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME AND ALOOP_BUILD_TESTS)
    enable_testing()
    add_subdirectory(test)
endif ()
