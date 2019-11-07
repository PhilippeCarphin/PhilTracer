cmake_minimum_required(VERSION 3.15)
project(PhilTracer)

set(CMAKE_CXX_STANDARD 17)

# https://stackoverflow.com/a/9469349/5795941
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

add_executable(PhilTracer main.cpp)

target_link_libraries(PhilTracer PRIVATE OpenGL::GL GLUT::GLUT)