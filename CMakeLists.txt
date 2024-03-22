# Authored by Sailanarmo
# Removes the need to upload and maintain Visual Studio Solution files.

cmake_minimum_required(VERSION 3.19)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

project(version)

add_library(version SHARED src/version.cpp)

target_link_options(version PUBLIC /DEF:${CMAKE_CURRENT_LIST_DIR}/src/version.def)