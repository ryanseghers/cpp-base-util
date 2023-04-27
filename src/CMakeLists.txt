cmake_minimum_required (VERSION 3.16)
project(CppBaseUtilLib LANGUAGES CXX VERSION 0.0.0)

set (CMAKE_CXX_STANDARD 20)
set (CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(fmt CONFIG REQUIRED)

set(SOURCE_FILES
	MathUtil.h
	MathUtil.cpp
	MiscUtil.h
	MiscUtil.cpp
	StringUtil.h
	StringUtil.cpp
	VectorUtil.h
	VectorUtil.cpp

	ThirdParty/debugbreak.h
)

add_library(CppBaseUtilLib STATIC ${SOURCE_FILES})
target_link_libraries(CppBaseUtilLib PUBLIC fmt::fmt)
target_include_directories(CppBaseUtilLib PUBLIC ".")
