set(CMAKE_BUILD_TYPE "Debug")

cmake_minimum_required(VERSION 3.21)
project(simple-triangle-opengl-sdl3-mingw-c)

# Set the C standard
set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED ON)

set(SDL3_DIR "C:/libs/SDL3-devel-3.4.12-mingw/lib/cmake/SDL3")
find_package(SDL3 REQUIRED)

add_executable(app)

target_include_directories(app PRIVATE "C:/libs/glad-0.1.36/opengl-3.3/include")

target_sources(app
PRIVATE
    "C:/libs/glad-0.1.36/opengl-3.3/src/glad.c"
    src/main.c
)

target_link_libraries(app PRIVATE SDL3::SDL3)
target_link_options(app PRIVATE -mconsole)
