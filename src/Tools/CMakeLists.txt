##### 設定環境
	cmake_minimum_required(VERSION 3.2)
	project(Tools)

	add_subdirectory(Window)
	add_subdirectory(GLSL)
	add_subdirectory(Face)

	# 引入3rdparty
	include_directories(${CMAKE_SOURCE_DIR}/3rdparty)
	include_directories(${CMAKE_SOURCE_DIR}/3rdparty/eigen3)

##### 設定 flags
	set(CMAKE_CXX_FLAGS "-std=c++14 -g")
	set(SRCS ToolKit.cpp)
	set(LIBS
		Window_LIB
		GLSL_LIB
		FACE_LIB
		)


##### link相關lib
	link_libraries(${LIBS})

##### 加入自己的tools to lib
	add_library(Tools ${SRCS})

