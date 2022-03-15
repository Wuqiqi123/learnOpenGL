cmake_minimum_required(VERSION 3.4...3.20 FATAL_ERROR)

project(learnOpenGL)

add_subdirectory(extern)

find_package(OpenGL REQUIRED)

add_executable(main main.cpp)
target_link_libraries(main
        PRIVATE
        glfw
        glad)