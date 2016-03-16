add_sources(gl_load.c
			gl_load_cpp.cpp)

if (MSVC)
	add_sources(wgl_load.c
			wgl_load_cpp.cpp)
endif()