cmake_minimum_required(VERSION 3.0)

# Project Description
# ------------------------------
project(METASIM)

set(VERSION_MAJOR "1")
set(VERSION_MINOR "0")
set(VERSION_PATCH "0")
set(VERSION "${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_PATCH}")


# Set environment
# ------------------------------
include_directories(${PROJECT_SOURCE_DIR}/src)
set(METASIM_LIB_NAME ${PROJECT_NAME})


# Environment-dependable settings.
# ------------------------------
if(APPLE OR UNIX)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=c++0x")
endif()


# Add subdirectories
# ------------------------------
add_subdirectory(src)
add_subdirectory(examples)
add_subdirectory(test)


# Export configuration
# ------------------------------
#export(TARGETS METASIM FILE "METASIMConfig.cmake")
#export(PACKAGE METASIM)