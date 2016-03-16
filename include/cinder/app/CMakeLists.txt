if (MSVC)
	add_subdirectory(msw)
elseif (APPLE)
	add_subdirectory(cocoa)
endif()

add_sources(App.h
			AppBase.h
			AppScreenSaver.h
			CMakeLists.txt
			Event.h
			FileDropEvent.h
			KeyEvent.h
			MouseEvent.h
			Platform.h
			Renderer.h
			RendererDx.h
			RendererGl.h
			TouchEvent.h
			Window.h
			)
