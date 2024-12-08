cmake_minimum_required(VERSION 3.16)
project(JZ_MusicPlayer)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include Directories
include_directories(include libs/imgui)

# Source Files
file(GLOB SOURCES src/*.cpp libs/imgui/*.cpp libs/imgui/backends/*.cpp)

# Link GLFW and OpenAL
find_package(OpenAL REQUIRED)
find_package(glfw3 REQUIRED)

add_executable(JZ_MusicPlayer ${SOURCES})
target_link_libraries(JZ_MusicPlayer PRIVATE glfw OpenAL::OpenAL)
