include_directories(${CMAKE_CURRENT_LIST_DIR}/include
					${CMAKE_CURRENT_LIST_DIR}/../boost
					${CMAKE_CURRENT_LIST_DIR}/include/oggvorbis
					${CMAKE_CURRENT_LIST_DIR}/src/AntTweakBar
					${CMAKE_CURRENT_LIST_DIR}/src/libtess2
					${CMAKE_CURRENT_LIST_DIR}/src/linebreak
					${CMAKE_CURRENT_LIST_DIR}/src/r8brain
					${CMAKE_CURRENT_LIST_DIR}/include/ANGLE
					${CMAKE_CURRENT_LIST_DIR}/include/tinyexr)

if (MSVC)
	include_directories(${CMAKE_CURRENT_LIST_DIR}/blocks/QuickTime/include/msw
				${CMAKE_CURRENT_LIST_DIR}/include/msw/png
				${CMAKE_CURRENT_LIST_DIR}/include/msw/zlib
				${CMAKE_CURRENT_LIST_DIR}/include/msw)

	add_definitions(-D_LIB
					-DNOMINMAX
					-D_WIN32_WINNT=0x0601
					-DCURL_STATICLIB
					-DCAIRO_WIN32_STATIC_BUILD
					-D_CRT_SECURE_NO_WARNINGS
					-D_SCL_SECURE_NO_WARNINGS)
else (APPLE)
	include_directories(${CMAKE_CURRENT_LIST_DIR}/src/oggvorbis/vorbis)
	add_definitions(-D_LIB
					-DNOMINMAX
					-DCURL_STATICLIB
					-D_CRT_SECURE_NO_WARNINGS
					-D_SCL_SECURE_NO_WARNINGS
					-D_GLIBCXX_DEBUG
					-D_GLIBCXX_DEBUG_PEDANTIC)
endif()

set_source_root()
add_subdirectory(include)
add_subdirectory(src)

commit_source_grouping()
add_library(cinder ${SRCS})

if (MSVC)
	set(CMAKE_CXX_FLAGS "/EHsc")
	set(CMAKE_CXX_FLAGS_DEBUG "/MTd /GR /RTC1 /Od /ZI")
	set(CMAKE_EXE_LINKER_FLAGS_DEBUG "$(CMAKE_EXE_LINKER_FLAGS_DEBUG) /DEBUG /SAFESEH:NO /NODEFAULTLIB:LIBCMT")
	set_target_properties(cinder PROPERTIES LINK_FLAGS "/SUBSYSTEM:WINDOWS")
	target_link_libraries(cinder Ws2_32 wldap32 shlwapi OpenGL32 zlib wmvcore Strmiids Msimg32 ${OPENGL_LIBRARIES})
elseif (APPLE)
	find_package(png)
	find_package(zlib)
	find_package(boost)
	add_sources(${CMAKE_CURRENT_LIST_DIR}/xcode/cinder_Prefix.pch)
	target_link_libraries(cinder ${OPENGL_LIBRARIES})
endif()
# Add apple thing here!