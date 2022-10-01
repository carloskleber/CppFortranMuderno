cmake_minimum_required(VERSION 3.14...3.22)

project(
  CppFortranMuderno
  VERSION 0.1
  DESCRIPTION "Example project"
  LANGUAGES CXX Fortran)

# Only do these if this is the main project, and not if it is included through add_subdirectory
if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
  set(CMAKE_CXX_EXTENSIONS OFF)
  set_property(GLOBAL PROPERTY USE_FOLDERS ON)
endif()

# FetchContent added in CMake 3.11, downloads during the configure step
include(FetchContent)

find_package(Boost REQUIRED)

# Teste de biblioteca externa - Eigen
# Na pratica nao sei se sera utilizada (os calculos pesados serao em Fortran)
FetchContent_Declare(
  eigen
  GIT_REPOSITORY https://gitlab.com/libeigen/eigen.git
  GIT_TAG 3.4.0)
FetchContent_MakeAvailable(eigen)

add_subdirectory(src)
add_subdirectory(app)

