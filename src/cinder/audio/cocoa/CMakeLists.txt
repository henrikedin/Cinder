add_sources(CinderCoreAudio.cpp
			FileCoreAudio.cpp
			ContextAudioUnit.cpp)
if (APPLE)
	add_sources(DeviceManagerCoreAudio.cpp)
elseif (IPHONE)
	add_sources(DeviceManagerAudioSession.mm)
elseif (IPHONE_SIM)
	add_sources(DeviceManagerAudioSession.mm)
endif()