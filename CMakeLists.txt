cmake_minimum_required( VERSION 2.8 FATAL_ERROR )
project (tinyxml)

#add_library(tinyxml SHARED ${srcs})
add_library(tinyxml STATIC ./tinystr.cpp  ./tinyxml.cpp  ./tinyxmlerror.cpp  ./tinyxmlparser.cpp)
install(TARGETS tinyxml
	LIBRARY DESTINATION lib
        RUNTIME DESTINATION bin
        PUBLIC_HEADER DESTINATION include  
)


option (TIXML_USE_STL "Use libi stl " ON)
file(GLOB header_files "*.h")
install(FILES ${header_files}     DESTINATION include)

