# -------------------
#  Projects Settings 
# -------------------

cmake_minimum_required(VERSION 3.8)
project(opengl)

# -------------------
#  Compilation flags 
# -------------------

set(CMAKE_CXX_FLAGS "-g -Wall")
set(CMAKE_CXX_STANDARD 11)

# -------------------
#  Load libraries 
# -------------------

#opengl
find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIR})

#glut
find_package(GLUT REQUIRED)
include_directories(${GLUT_INCLUDE_DIR})

#glew
find_package(GLEW REQUIRED)
include_directories(/usr/local/Cellar/glew/2.1.0)

#glfw
find_package(GLFW3 REQUIRED)
include_directories(/usr/local/Cellar/glfw/3.2.1)

# -------------------
#  Build executable  
# -------------------

set(SOURCE_FILES main.cpp code1.cpp code2.cpp)
add_executable(opengl ${SOURCE_FILES})
target_link_libraries(opengl ${GLUT_LIBRARY} ${OPENGL_LIBRARY} ${GLEW_LIBRARY} ${GLFW_LIBRARY})