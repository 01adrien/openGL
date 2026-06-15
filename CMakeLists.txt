cmake_minimum_required(VERSION 3.20)

project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_C_STANDARD 11)

add_subdirectory(external/glfw)

add_executable(LearnOpenGL
    src/main.cpp
    external/glad/src/gl.c
)

target_include_directories(LearnOpenGL PRIVATE
    include
    external/glad/include
)

target_link_libraries(LearnOpenGL PRIVATE
    glfw
)


find_package(OpenGL REQUIRED)
target_link_libraries(LearnOpenGL PRIVATE OpenGL::GL dl)