cmake_minimum_required(VERSION 3.9)
project(chat_server)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_CXX_COMPILER "clang++")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -stdlib=libc++ -lc++abi")
set(CMAKE_CXX_FLAGS "-fcoroutines-ts --stdlib=libc++ -Xclang -fconcepts-ts -pthread")
SET(PLATFORM_SPECIFIC_LIBS "-lpthread")

# find_package(system)

include_directories(../include)
link_directories(../build/)

# add_library(project libasio.a)
add_executable(echo_server echo_server.cpp)
target_link_libraries(echo_server libasio.a)


