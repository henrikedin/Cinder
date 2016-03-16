if (APPLE)
	add_sources(AppCocoaView.mm
		AppImplMac.mm
		AppImplMacScreenSaver.mm
		AppMac.cpp
		CinderViewMac.mm
		PlatformCocoa.cpp
		RendererImplGlMac.mm
		RendererImpl2dMacQuartz.mm)
elseif (IPHONE) 
	add_sources(AppCocoaTouch.cpp
		AppImplCocoaTouch.mm
		CinderViewCocoaTouch.mm
		RendererImpl2dCocoaTouchQuartz.mm
		RendererImplGlCocoaTouch.mm)
endif()