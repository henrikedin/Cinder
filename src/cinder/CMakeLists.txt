add_subdirectory(app)
add_subdirectory(audio)
if (APPLE)
	add_subdirectory(cocoa)
endif()
add_subdirectory(gl)
add_subdirectory(ip)
if (MSVC)
	add_subdirectory(msw)
endif()
add_subdirectory(params)
add_subdirectory(qtime)
add_subdirectory(svg)

add_sources(Area.cpp
			BandedMatrix.cpp
			Base64.cpp
			BSpline.cpp
			BSplineFit.cpp
			Buffer.cpp
			Camera.cpp
			CameraUi.cpp
			Capture.cpp
			Channel.cpp
			CinderAssert.cpp
			CinderMath.cpp
			Clipboard.cpp
			Color.cpp
			ConvexHull.cpp
			DataSource.cpp
			DataTarget.cpp
			Display.cpp
			Exception.cpp
			Font.cpp
			Frustum.cpp
			GeomIo.cpp
			ImageFileTinyExr.cpp
			ImageIo.cpp
			ImageSourceFileRadiance.cpp
			ImageSourcePng.cpp
			Json.cpp
			Log.cpp
			Matrix.cpp
			ObjLoader.cpp
			Path2d.cpp
			Perlin.cpp
			Plane.cpp
			PolyLine.cpp
			Rand.cpp
			Ray.cpp
			Rect.cpp
			Serial.cpp
			Shape2d.cpp
			Signals.cpp
			Sphere.cpp
			Stream.cpp
			Surface.cpp
			System.cpp
			Text.cpp
			Timeline.cpp
			TimelineItem.cpp
			Timer.cpp
			Triangulate.cpp
			TriMesh.cpp
			Tween.cpp
			Unicode.cpp
			Url.cpp
			Utilities.cpp
			Xml.cpp
)

if (MSVC)
	add_sources(CaptureImplDirectShow.cpp
			ImageSourceFileWic.cpp
			ImageTargetFileWic.cpp
			UrlImplWinInet.cpp)
elseif (APPLE)
	add_sources(ImageSourceFileQuartz.cpp
			ImageTargetFileQuartz.cpp
			CaptureImplAvFoundation.mm
			UrlImplCocoa.mm)
elseif (IPHONE)
	add_sources()
elseif (IPHONE_SIM)
	add_sources(CaptureImplCocoaDummy.mm)
endif()
