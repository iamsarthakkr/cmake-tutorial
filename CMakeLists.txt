# version of cmake
cmake_minimum_required(VERSION 3.24.2)

# setup c++ version
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# specify name of the project. Can be accessed using ${PROJECT_NAME}
project(CMAKE_TUTORIAL VERSION 1.0)

# specify name of the executible file and the source files (traditional way)
# add_executable(out main.cpp src/Foo.cpp)

# specify name of the executible file and the source files (easier way)
file(GLOB_RECURSE SOURCES src/*.cpp)
add_executable(out main.cpp ${SOURCES})

# To include header file directory to the executible
target_include_directories(out PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Adding sub-directory (library)
add_subdirectory(Adder)

# linking Adder library to our executible
target_link_libraries(out PUBLIC Adder)