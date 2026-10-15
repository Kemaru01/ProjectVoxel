# ProjectVoxel

A voxel-based game project. The project is designed with a modular architecture and runs in a Client-Server structure.

## 📁 Project Structure

```
ProjectVoxel/
├── CMakeLists.txt          # Root CMake configuration
├── Engine/                 # Game engine (standalone)
│   ├── include/Engine/     # Engine header files
│   ├── src/                # Engine source code
│   ├── third_party/        # Third-party libraries
│   └── CMakeLists.txt
├── Shared/                 # Common code library
│   ├── include/            # Shared header files
│   ├── src/                # Shared source code
│   └── CMakeLists.txt
└── Game/
    ├── Client/             # Game client (Engine + Shared)
    │   └── CMakeLists.txt
    └── Server/             # Game server (Shared, headless)
        └── CMakeLists.txt
```

## 🔗 Module Dependencies

| Module | Description | Dependencies |
|--------|-------------|--------------|
| **Engine** | Voxel game engine (graphics, audio, input, physics) | None (standalone) |
| **Shared** | Common code between Server and Client (data structures, network protocols, utilities) | None (standalone) |
| **GameClient** | Game client (visual interface, user interaction) | Engine, Shared |
| **GameServer** | Game server (headless, server-side logic) | Shared |

### Dependency Diagram

```
        ┌─────────┐
        │ Engine  │
        └────┬────┘
             │
             ▼
┌──────────┐     ┌──────────┐
│GameClient│────▶│  Shared  │◀────┐
└──────────┘     └──────────┘    │
                                 │
                        ┌────────┘
                        ▼
                   ┌──────────┐
                   │GameServer│
                   └──────────┘
```

## 🛠️ Building

### Requirements

- CMake 3.22+
- A C++20-compatible compiler (GCC 10+, Clang 12+, MSVC 19.30+)
- Linux / Windows / macOS support

### Steps

```bash
# Create build directory
mkdir build && cd build

# Configure CMake
cmake .. -DCMAKE_BUILD_TYPE=Release

# Build
cmake --build . --config Release
```

### Debug Build

```bash
cmake .. -DCMAKE_BUILD_TYPE=Debug
cmake --build . --config Debug
```

## 📦 Outputs

When the build is complete, the following targets are created:

- **Engine** (static library) — `libEngine.a` / `Engine.lib`
- **Shared** (static library) — `libShared.a` / `Shared.lib`
- **GameClient** (application) — Executable file
- **GameServer** (application) — Executable file

## 🎮 Usage

### Starting the Server

```bash
./GameServer
```

### Starting the Client

```bash
./GameClient
```

## 📝 License

This project does not include a license file yet.
