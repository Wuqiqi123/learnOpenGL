cmake_minimum_required(VERSION 3.4...3.20 FATAL_ERROR)

project(learnOpenGL)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Wno-error")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -O0")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O3")



add_subdirectory(extern)

find_package(OpenGL REQUIRED)
find_package(Boost REQUIRED)
find_package(Assimp REQUIRED)


file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS src/*.cpp)

add_executable(main src/main.cpp ${SOURCES})

target_link_libraries(main
        PRIVATE
        glfw
        glad
        glm
        stb
        assimp)

target_include_directories(main PUBLIC include stb)