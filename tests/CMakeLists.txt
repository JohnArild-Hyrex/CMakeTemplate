cmake_minimum_required(VERSION 3.14)

project(CMakeTemplateTests)

# Add gtest
find_package(GTest CONFIG REQUIRED)

# Add the source files for the tests
add_executable(${PROJECT_NAME}
        TestCMakeTemplate.cpp
)

# Link external libraries to your executable
target_link_libraries(${PROJECT_NAME} PRIVATE GTest::gtest GTest::gtest_main)

# Add the test executable
add_test(
  NAME ${PROJECT_NAME}
  COMMAND ${PROJECT_NAME}
)