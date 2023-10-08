cmake_minimum_required(VERSION 3.0)

project(usehello)

find_package(helloSLAM CONFIG REQUIRED)

add_executable(usehelloapp useHello.cpp)

target_include_directories(usehelloapp PRIVATE /usr/local/include)
target_link_libraries(usehelloapp helloSLAM)