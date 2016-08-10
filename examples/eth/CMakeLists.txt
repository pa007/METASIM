project(ETHERNET)

# Create the executable.
add_executable(${PROJECT_NAME}
	example.cpp link.cpp link.hpp message.cpp message.hpp netinterface.cpp
	netinterface.hpp node.cpp node.hpp)

# Indicate that the executable needs metasim library.
target_link_libraries(${PROJECT_NAME} ${METASIM_LIB_NAME}_STATIC)
