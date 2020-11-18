cmake_minimum_required(VERSION 3.15)
project(PhilTracer CXX)

set(CMAKE_CXX_STANDARD 17)

# https://stackoverflow.com/a/9469349/5795941
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(GLEW REQUIRED)
find_package(Vulkan REQUIRED)

add_executable(PhilTracer main.cpp)
message(STATUS "GLEW_FOUND = ${GLEW_FOUND}")
message(STATUS "OpenGL_INCLUDE_DIR = ${OpenGL_INCLUDE_DIR}")
message(STATUS "OpenGL_LIBRARIES = ${OpenGL_LIBRARIES}")
message(STATUS "GLEW_LIBRARIES = ${GLEW_LIBRARIES}")
target_link_libraries(PhilTracer PRIVATE ${OpenGL_LIBRARIES} GLEW::GLEW ${GLUT_LIBRARIES} glfw)
if(${APPLE})
    # include_directories(/usr/local/include)
    target_link_options(PhilTracer PRIVATE -L /usr/local/lib)
endif()
# target_include_directories(PhilTracer PRIVATE ${OpenGL_INCLUDE_DIR} ${GLUT_INCLUDE_DIRS})
