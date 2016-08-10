project(QUEUE)

# Create the executable.
add_executable(${PROJECT_NAME} queue.cpp queue.hpp)

# Indicate that the executable needs metasim library.
target_link_libraries(${PROJECT_NAME} ${METASIM_LIB_NAME}_STATIC)
