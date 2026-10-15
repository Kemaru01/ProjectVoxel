cmake_minimum_required(VERSION 3.22)
project(ProjectVoxel LANGUAGES C CXX)

# Global C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Default build type
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

# Modules
add_subdirectory(Engine)
add_subdirectory(Shared)

add_subdirectory(Game/Client)
add_subdirectory(Game/Server)
