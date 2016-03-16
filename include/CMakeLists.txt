add_subdirectory(cinder)
add_subdirectory(jsoncpp)
add_subdirectory(oggvorbis)
add_subdirectory(rapidxml)

if (MSVC)
	add_subdirectory(msw)
endif()

add_sources()