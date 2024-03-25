cmake_minimum_required(VERSION 3.14)

project(CMakeTemplate)

set (CMAKE_CXX_FLAGS "-std=c++20")

add_library(${PROJECT_NAME}
        CMakeTemplate.h
        CMakeTemplate.cpp
)

add_executable(${PROJECT_NAME}Exec
        main.cpp
)

target_link_libraries(${PROJECT_NAME}Exec PRIVATE ${PROJECT_NAME})
