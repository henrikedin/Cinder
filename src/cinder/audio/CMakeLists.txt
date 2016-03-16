add_subdirectory(dsp)
if (MSVC)
	add_subdirectory(msw)
elseif(APPLE)
	add_subdirectory(cocoa)
endif()

add_sources(ChannelRouterNode.cpp
			Context.cpp
			DelayNode.cpp
			Device.cpp
			FileOggVorbis.cpp
			FilterNode.cpp
			GenNode.cpp
			InputNode.cpp
			MonitorNode.cpp
			Node.cpp
			NodeMath.cpp
			OutputNode.cpp
			PanNode.cpp
			Param.cpp
			SamplePlayerNode.cpp
			SampleRecorderNode.cpp
			Source.cpp
			Target.cpp
			Utilities.cpp
			Voice.cpp
			WaveTable.cpp)
			