cmake_minimum_required(VERSION 3.13.1)
project(
  Cxx11Sharp
  VERSION 0.0.1
  LANGUAGES CXX C)

# only export limited set of symbols
set(CMAKE_C_VISIBILITY_PRESET hidden)
set(CMAKE_CXX_VISIBILITY_PRESET hidden)
set(CMAKE_VISIBILITY_INLINES_HIDDEN 1)

# require c++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include(GNUInstallDirs)
set(Cxx11Sharp_LIBRARY_INSTALL_DIR "${CMAKE_INSTALL_LIBDIR}")

add_library(cxx11sharp MODULE src/managed_streambuf.cxx)

install(
  TARGETS cxx11sharp
  DESTINATION ${Cxx11Sharp_LIBRARY_INSTALL_DIR}
  COMPONENT libraries)
