cmake_minimum_required(VERSION 3.16)
project(herculez_pool LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(PkgConfig REQUIRED)
pkg_check_modules(SDL2 REQUIRED sdl2)

add_executable(herculez_pool i.cpp)
target_include_directories(herculez_pool PRIVATE ${SDL2_INCLUDE_DIRS})
target_link_directories(herculez_pool PRIVATE ${SDL2_LIBRARY_DIRS})
target_link_libraries(herculez_pool PRIVATE ${SDL2_LIBRARIES})
target_compile_options(herculez_pool PRIVATE ${SDL2_CFLAGS_OTHER} -O2 -Wall -Wextra -Wpedantic)
