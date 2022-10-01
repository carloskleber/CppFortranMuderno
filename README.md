# CppFortranMuderno
Testing a modern way to do C++, Fortran, CMake etc.

I'm trying to emulate a large multi-file project, with external dependencies, to learn how CMake put all together.

The main purpose is scientific applications, so I'll use some matrix operations, complex algebra, and externalize these is some smart way, like JSON.

Some external libraries to test are LAPACK, Boost and Eigen.

## Basic configuration

1. Configure the Cmake file, considering 
1. Clone the project and enter the project folder
1. `mkdir build`
1. `cd build`
1. `cmake ..`
1. `cmake --make .`

## Cross-compile test

1. Follow the recommendation in https://cmake.org/cmake/help/book/mastering-cmake/chapter/Cross%20Compiling%20With%20CMake.html
1. After `cd build`, configure with `cmake -DCMAKE_TOOLCHAIN_FILE=~/TC-mingw.cmake ..`

