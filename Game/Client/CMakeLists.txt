# Game Client — Voxel game client (depends on Engine and Shared)

# Collect source files
file(GLOB_RECURSE CLIENT_SOURCES
        "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/*.c"
)

file(GLOB_RECURSE CLIENT_HEADERS
        "${CMAKE_CURRENT_SOURCE_DIR}/include/**/*.h"
        "${CMAKE_CURRENT_SOURCE_DIR}/include/**/*.hpp"
)

# Client executable
add_executable(GameClient
    ${CLIENT_SOURCES}
    ${CLIENT_HEADERS}
)

# Dependencies: Engine (graphics, audio, input) + Shared (common code)
target_link_libraries(GameClient
    PRIVATE
        Engine
        Shared
)

# Compile definitions
target_compile_definitions(GameClient
    PRIVATE
        CLIENT_BUILD
)

# Client libraries (add if needed)
# target_link_libraries(GameClient PRIVATE OpenGL GLU glfw3 SDL2)
