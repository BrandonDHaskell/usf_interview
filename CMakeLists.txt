cmake_minimum_required(VERSION 4.1)
project(usf_interview VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(interview
    src/main.cpp
)

target_include_directories(interview
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_compile_features(
    interview
    PRIVATE
        cxx_std_23
)

set_target_properties(
    interview
    PROPERTIES
        CXX_EXTENSIONS OFF
)

if(CMAKE_CXX_COMPILER_ID MATCHES "GNU|Clang")
    target_compile_options(
        interview
        PRIVATE
            -Wall
            -Wextra
            -Wpedantic
            -Werror
            -pedantic-errors
            -Wconversion
            -Wsign-conversion
            -Wshadow
            -Wformat=2
            -Wundef
            -Wcast-align
            -Wcast-qual
            -Wold-style-cast
            -Woverloaded-virtual
            -Wnon-virtual-dtor
            -Wnull-dereference
            -Wdouble-promotion
            -Wimplicit-fallthrough
    )
elseif(MSVC)
    target_compile_options(
        interview
        PRIVATE
            /W4
            /WX
            /permissive-
    )
endif()

add_custom_target(run
    COMMAND $<TARGET_FILE:interview>
    DEPENDS interview
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    COMMENT "Run interview executable"
    VERBATIM
)