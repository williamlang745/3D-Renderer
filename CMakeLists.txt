cmake_minimum_required(VERSION 3.14)

set(CMAKE_CXX_STANDARD 20)

project(3D-Renderer)

include(FetchContent)

FetchContent_Declare(
        glfw
        GIT_REPOSITORY https://github.com/glfw/glfw
)
FetchContent_MakeAvailable(glfw)

add_executable(3D-Renderer main.cpp)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )

target_link_libraries(3D-Renderer glfw ${OPENGL_LIBRARIES} ${GLUT_LIBRARY})