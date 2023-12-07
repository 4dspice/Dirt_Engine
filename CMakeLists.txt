cmake_minimum_required(VERSION 3.10)
project(Dirt_Engine)

set(CMAKE_CXX_STANDARD 20)

set(CMAKE_PREFIX_PATH "/usr/lib/cmake/glfw3" ${CMAKE_PREFIX_PATH})

find_package(Vulkan REQUIRED)
find_package(glfw3 3.3 REQUIRED)

include_directories(${Vulkan_INCLUDE_DIRS})
include_directories(${GLFW_INCLUDE_DIRS})

link_libraries(${Vulkan_LIBRARIES})
link_libraries(${GLFW_LIBRARIES})

set(SOURCES
    src/main.cpp
)

add_executable(Dirt_Engine ${SOURCES})

target_link_libraries(Dirt_Engine ${Vulkan_LIBRARIES} glfw)