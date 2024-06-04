cmake_minimum_required(VERSION 3.21)

project(ignosi-dll-test)

include(GoogleTest)

set(CMAKE_CXX_STANDARD 20)

add_executable(${PROJECT_NAME} "main.cpp")

find_package(GTest CONFIG REQUIRED)

target_link_libraries(${PROJECT_NAME} PRIVATE GTest::gtest ignosi-dll-macros)

gtest_add_tests(TARGET ${PROJECT_NAME})

install(
  TARGETS ${PROJECT_NAME}
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib)
