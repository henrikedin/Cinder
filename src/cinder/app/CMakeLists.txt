if (MSVC)
	add_subdirectory(msw)
endif()

add_sources(AppBase.cpp
			AppScreenSaver.cpp
			CMakeLists.txt
			KeyEvent.cpp
			Platform.cpp
			Renderer.cpp
			RendererGl.cpp
			Window.cpp)
