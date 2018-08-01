cmake_minimum_required(VERSION 3.0)
project(engine)

set(CMAKE_CXX_FLAGS "-O3 -std=c++14 -Wall -Wextra -pedantic")

include_directories(../deps/GLFW/include)

#include_directories(${OPENGL_INCLUDE_DIRS})
#find_package(OpenGL)

find_library(GLFW3_LIB glfw3 HINTS ../deps/GLFW/lib)

add_executable(main main.cpp)

#target_link_libraries(main ${OPENGL_LIBRARIES} ${GLFW3_LIB} ${CMAKE_DL_LIBS} X11 pthread)
target_link_libraries(main GL GLU ${GLFW3_LIB} X11 Xxf86vm Xrandr pthread Xi dl Xinerama Xcursor)