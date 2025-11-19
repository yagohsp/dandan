cmake_minimum_required(VERSION 3.10)
project(gl-empty CXX)
set(CMAKE_CXX_STANDARD 17)

find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm CONFIG REQUIRED) # optional, glm is header-only

add_executable(app src/main.cpp)
target_include_directories(app PRIVATE ${OPENGL_INCLUDE_DIR})
target_link_libraries(app PRIVATE ${OPENGL_gl_LIBRARY} GLEW::GLEW glfw glm)
