project(${METASIM_LIB_NAME})

# Define all the source and header files
# ------------------------------
set(${PROJECT_NAME}_headers 
	baseexc.hpp basestat.hpp basetype.hpp debugstream.hpp entity.hpp
	event.hpp factory.hpp genericvar.hpp gevent.hpp history.hpp 
	metasim.hpp particle.hpp plist.hpp randomvar.hpp regvar.hpp
	simul.hpp strtoken.hpp tick.hpp trace.hpp)
set(${PROJECT_NAME}_sources
	basestat.cpp debugstream.cpp entity.cpp event.cpp genericvar.cpp
	randomvar.cpp regvar.cpp simul.cpp strtoken.cpp tick.cpp trace.cpp)


# Create static and shared libraries for METASIM
# ------------------------------
add_library(${PROJECT_NAME} SHARED
	${${PROJECT_NAME}_headers}
	${${PROJECT_NAME}_sources})
	
add_library(${PROJECT_NAME}_STATIC STATIC
	${${PROJECT_NAME}_headers}
	${${PROJECT_NAME}_sources})


# Install options
# ------------------------------
install(TARGETS ${PROJECT_NAME} ${PROJECT_NAME}_STATIC
	EXPORT "${PROJECT_NAME}-targets"
	RUNTIME DESTINATION bin
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib/static)
	
install(EXPORT ${PROJECT_NAME}-targets
	DESTINATION lib)

install(FILES ${${PROJECT_NAME}_headers}
	DESTINATION include)