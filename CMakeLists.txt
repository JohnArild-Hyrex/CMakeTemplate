cmake_minimum_required(VERSION 3.14)

project(CMakeTemplate)

# Create compile_commands.json file for use with cppcheck
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Add subdirectories
add_subdirectory(src)

# include submodules
target_include_directories(${PROJECT_NAME} PUBLIC src)

option(BUILD_TESTS "Build tests" OFF)

if(BUILD_TESTS)
    message(STATUS "Generating tests")
    enable_testing()
    add_subdirectory(tests)
endif()
