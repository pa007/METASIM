cmake_minimum_required (VERSION 3.0)
project (METASIM)

# Include dirs.
add_subdirectory (src)
add_subdirectory (examples)
add_subdirectory (test)

# Export.
export(TARGETS METASIM FILE "./METASIMConfig.cmake")
export(PACKAGE METASIM)
