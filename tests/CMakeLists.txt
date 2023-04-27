cmake_minimum_required (VERSION 3.16)
project (CppBaseUtilTests)

if (NOT TARGET CppBaseUtilLib)
    add_subdirectory("../src" CppBaseUtilLib)
endif()

find_package(GTest CONFIG REQUIRED)

set(SOURCE_FILES
	main.cpp
	StringUtilTests.cpp
	)

# Add source to this project's executable.
add_executable(cppbaseutiltest ${SOURCE_FILES} )

target_include_directories(cppbaseutiltest PUBLIC ".")

target_link_libraries(cppbaseutiltest PRIVATE CppBaseUtilLib GTest::gtest_main)

# CTest on top of googletest, with test discovery
include(GoogleTest)
enable_testing()
gtest_discover_tests(cppbaseutiltest)
