# Game Server — Voxel game server (headless, independent of Engine)

# Collect source files
file(GLOB_RECURSE SERVER_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/*.c"
)

file(GLOB_RECURSE SERVER_HEADERS
    "${CMAKE_CURRENT_SOURCE_DIR}/*.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/*.hpp"
)

# Server executable
add_executable(GameServer
    ${SERVER_SOURCES}
    ${SERVER_HEADERS}
)

# Dependencies: Shared only (headless — no Engine required)
target_link_libraries(GameServer
    PRIVATE
        Shared
)

# Compile definitions
target_compile_definitions(GameServer
    PRIVATE
        SERVER_BUILD
)

# Server libraries (add if needed: networking, threading, etc.)
# target_link_libraries(GameServer PRIVATE pthread)
