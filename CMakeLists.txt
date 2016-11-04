PROJECT(conanpoco)
cmake_minimum_required(VERSION 2.8)
include(${CMAKE_CURRENT_SOURCE_DIR}/../conanbuildinfo.cmake)
CONAN_BASIC_SETUP()

if(CXX_14)
    MESSAGE("Activating CXX_STANDARD 14")
    set(CMAKE_CXX_STANDARD 14)
else()
    MESSAGE("Not activating CXX_STANDARD 14")
endif()

if(CMAKE_CXX_COMPILER MATCHES ".*clang")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -stdlib=libc++")
endif()


include("CMakeListsOriginal.cmake.with-pic")
