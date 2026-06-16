cmake_minimum_required(VERSION 4.1)
project(usf_interview VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(interview src/main.cpp)

add_custom_target(run
    COMMAND interview
    DEPENDS interview
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    COMMENT "Run interview executable"
)