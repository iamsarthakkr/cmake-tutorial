# version of cmake
cmake_minimum_required(VERSION 3.24.2)

# specify name of the project. Can be accessed using ${PROJECT_NAME}
project(CMAKE_TUTORIAL)

# specify name of the executible file and the main cpp file
add_executable(out main.cpp)
