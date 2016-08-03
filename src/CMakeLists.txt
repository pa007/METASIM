# Add current directory.
include_directories("${PROJECT_SOURCE_DIR}/include")

# Environment-dependable settings.
if(APPLE)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=c++0x")
	set(METASIM_LIB "SHARED")
	
elseif(UNIX)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=c++0x")
	set(METASIM_LIB "SHARED")
	
elseif(WIN32)
	set(METASIM_LIB "STATIC")

endif()

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)

# Create a library called "metasim" which includes the source files.
add_library(METASIM ${METASIM_LIB} basestat.cpp entity.cpp genericvar.cpp
  regvar.cpp strtoken.cpp trace.cpp debugstream.cpp event.cpp
  randomvar.cpp simul.cpp tick.cpp)
