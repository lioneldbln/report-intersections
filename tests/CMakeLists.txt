cmake_minimum_required(VERSION 3.2.2)

project(repintTests)

find_package(Threads REQUIRED)

include_directories(./ ../inc)

file(GLOB SOURCES "*.cpp" "../src/*.cpp")

add_executable(repintTests ${SOURCES})

target_link_libraries(repintTests
												  gmock
                          gmock_main
												  ${CMAKE_THREAD_LIBS_INIT})

add_test(NAME repintTests COMMAND $<TARGET_FILE:repintTests>)

