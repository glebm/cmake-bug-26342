cmake_minimum_required(VERSION 3.28)
include(FetchContent)

project(CmakeBug26342 LANGUAGES C)

# This project depends on SDL2 via FetchContent
add_subdirectory(sdl2_dependency)

# third_party_lib also depends on SDL2 but
# simply via `find_package(SDL2 REQUIRED)`
add_subdirectory(third_party_lib)
