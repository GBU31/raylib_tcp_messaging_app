cmake_minimum_required(VERSION 3.12)

project(raylib_tcp_messaging_app)

include(FetchContent)

set(RAYLIB_VERSION 4.5.0)

FetchContent_Declare(
    raylib
    URL https://github.com/raysan5/raylib/archive/refs/tags/${RAYLIB_VERSION}.tar.gz
)

FetchContent_MakeAvailable(raylib)

add_executable(client client.c)
target_link_libraries(client raylib m pthread dl rt X11)

add_executable(server server.c)
target_link_libraries(server raylib m pthread dl rt X11)
