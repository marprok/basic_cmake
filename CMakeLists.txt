cmake_minimum_required(VERSION 2.8)

project(OpenGL_Project)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#Bring the headers
include_directories(
  # Here you put the paths
  # to the directories that
  # contain your headers
  # separated by newline
  # e.g inc/GLEW
)

set(SOURCES
  # Here you put the paths
  # to your source files
  # separated by newline
  # e.g src/Renderer.cpp
)

# The following are some examples
# of how to use an external library
# that is already installed on your system
# SDL2 and SDL2_image
# find_package(SDL2 REQUIRED)
# find_package(SDL2_image REQUIRED)
# include_directories(${SDL2_INCLUDE_DIRS})
# string(STRIP ${SDL2_LIBRARIES} SDL2_LIBRARIES) # required to fix an issue on Linux Mint/Ubuntu

# opengl
# find_package(OpenGL REQUIRED)
# include_directories(${OPENGL_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} "main.cpp" ${SOURCES})

# Without libraries
target_link_libraries(${PROJECT_NAME})
# With libraries
target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARIES} SDL2_image GLEW ${OPENGL_LIBRARIES})

