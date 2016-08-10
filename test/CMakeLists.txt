project(TESTS)

include_directories(".")

# Create the executable.
add_executable(${PROJECT_NAME}
	myentity.cpp TestEntityOrder.cpp TestEntitySameName.cpp TestParseUtil.cpp
	TestTick.cpp)

# Indicate that rtlib need metasim library.
target_link_libraries(${PROJECT_NAME} ${METASIM_LIB_NAME}_STATIC)