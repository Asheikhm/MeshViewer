cmake_minimum_required(VERSION 3.14 FATAL_ERROR)
project(MeshViewer)

add_executable(MeshViewer)

target_compile_features(MeshViewer PRIVATE cxx_std_11)

target_include_directories(MeshViewer PRIVATE 
    include
)

find_package(glfw3 REQUIRED)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

include_directories(ThirdParty)

target_sources(MeshViewer PRIVATE
    src/main.cpp
    ThirdParty/glad/glad.c
)
target_link_libraries(MeshViewer PRIVATE glfw)