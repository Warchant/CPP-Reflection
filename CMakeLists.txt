cmake_minimum_required(VERSION 3.4)

project(CPP-Reflection)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/Source/CMake")

include(MetaParser)
include(Precompiled)


if(NOT LLVM_ROOT)
    set(LLVM_ROOT $ENV{LLVM4_ROOT})
endif()
if(NOT BOOST_ROOT)
    set(BOOST_ROOT $ENV{BOOST1_65_ROOT})
endif()
message(STATUS LLVM_ROOT: ${LLVM_ROOT})
message(STATUS BOOST_ROOT: ${BOOST_ROOT})

add_definitions(
    -std=c++14
    -fdiagnostics-color
)

add_subdirectory(Source/Runtime)
add_subdirectory(Source/Parser)
add_subdirectory(Examples)
