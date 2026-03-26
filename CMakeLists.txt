cmake_minimum_required(VERSION 3.10)
project(Uxarba VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include directories
include_directories(src)
include_directories(components)
include_directories(design)

# Source files
file(GLOB_RECURSE SOURCES "src/*.cpp")
file(GLOB_RECURSE COMPONENT_SOURCES "components/*.cpp")

# Create library
add_library(uxarba STATIC \${SOURCES} \${COMPONENT_SOURCES})

# Examples
add_subdirectory(examples)
add_subdirectory(tests)

# Installation
install(TARGETS uxarba DESTINATION lib)
install(DIRECTORY components DESTINATION include/uxarba)
