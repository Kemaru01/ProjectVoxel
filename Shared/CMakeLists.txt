# Shared module — Common code between Server and Client

# Collect source files
file(GLOB_RECURSE SHARED_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.c"
)

file(GLOB_RECURSE SHARED_HEADERS
    "${CMAKE_CURRENT_SOURCE_DIR}/include/**/*.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/include/**/*.hpp"
)

# Shared library
add_library(Shared STATIC
    ${SHARED_SOURCES}
    ${SHARED_HEADERS}
)

# Include directories
target_include_directories(Shared
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/src
)

# Compile definitions
target_compile_definitions(Shared
    PRIVATE
        SHARED_BUILD
)
