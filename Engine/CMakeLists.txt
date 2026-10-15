# Engine module — Voxel game engine (standalone)

# Collect source files
file(GLOB_RECURSE ENGINE_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.c"
)

file(GLOB_RECURSE ENGINE_HEADERS
    "${CMAKE_CURRENT_SOURCE_DIR}/include/**/*.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/include/**/*.hpp"
)

# Engine library
add_library(Engine STATIC
    ${ENGINE_SOURCES}
    ${ENGINE_HEADERS}
)

# Include directories
target_include_directories(Engine
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/src
)

# Third-party dependencies (add here if needed)
# target_include_directories(Engine PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/third_party/...)

# Compile definitions
target_compile_definitions(Engine
    PRIVATE
        ENGINE_BUILD
)

# Link dependencies (add if needed: OpenGL, SDL, GLFW, etc.)
# target_link_libraries(Engine PRIVATE ...)
