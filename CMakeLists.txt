cmake_minimum_required(VERSION 3.5)

project(hello_library VERSION 1.0.0 LANGUAGES CXX)

add_library(hello SHARED hello.cpp)

target_include_directories(hello PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Define HELLO_EXPORTS to handle symbol export/import
target_compile_definitions(hello PRIVATE HELLO_EXPORTS)

set(TARGET main_test)
add_executable(${TARGET} main.cpp)

target_link_libraries(${TARGET} hello)
