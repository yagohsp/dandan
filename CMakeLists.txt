cmake_minimum_required(VERSION 3.10)
project(dandan VERSION 0.1 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(OpenGL REQUIRED)           
find_package(glfw3 REQUIRED)           
find_package(glm CONFIG REQUIRED)     

add_library(glad STATIC src/glad.c)
target_include_directories(glad PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(app src/main.cpp)

target_include_directories(app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

target_link_libraries(app PRIVATE glad OpenGL::GL glfw glm::glm)
