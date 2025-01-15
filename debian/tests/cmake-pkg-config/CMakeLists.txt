# Copyright 2019 Collabora Ltd.
# SPDX-License-Identifier: Zlib

# Test use of SDL2_mixer in a CMake project by using pkg-config, as
# wesnoth-1.16 does.
cmake_minimum_required(VERSION 3.12)
project(test LANGUAGES C)
find_package(PkgConfig REQUIRED)
pkg_check_modules(SDL2MIXER REQUIRED SDL2_mixer>=2.0.0)
include_directories(SYSTEM ${SDL2MIXER_INCLUDE_DIRS})
add_executable(main main.c)
target_link_libraries(main ${SDL2MIXER_LIBRARIES})
